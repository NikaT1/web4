<template>
  <div>
    <Header/>
    <div class="main-background div-block">
      <div class="div-block" id="div-inline">
        <div class="div-inline">
          <PictureGraph v-bind:data="data" v-bind:param_r="param_r" v-on:clickOnSVG="clickOnSVG($event)"/>
        </div>
        <ArgsBlock class="div-inline" v-model:param_x="param_x" v-model:param_r="param_r" v-model:param_y="param_y"/>
      </div>
      <div class="div-block" id="div-buttons">
        <ButtonsBlock v-bind:buttons="buttons" v-on:goBack="goBack" v-on:submit="submit" v-on:clear="clear"/>
      </div>
    </div>
    <div class="div-block" id="result-table">
      <ResultTable v-model:data="data"/>
    </div>
  </div>
  <Footer/>
</template>

<script>
import Header from "@/components/pcomponents/Header";
import PictureGraph from "@/components/pcomponents/PictureGraph";
import ButtonsBlock from "@/components/pcomponents/ButtonsBlock";
import ResultTable from "@/components/pcomponents/ResultTable"
import ArgsBlock from "@/components/pcomponents/ArgsBlock";
import Footer from "@/components/pcomponents/Footer";

export default {
  components: {
    Footer,
    Header,
    PictureGraph,
    ButtonsBlock,
    ResultTable,
    ArgsBlock,
  },
  name: 'Main',
  data() {
    return {
      param_x: -5,
      param_y: "",
      param_r: 1,
      data: new Array(0),
      buttons: [
        {msg: 'выйти', command: 'goBack'},
        {msg: 'результат', command: 'submit'},
        {msg: 'очистить', command: 'clear'}
      ],
    }
  },
  created: function () {
    document.addEventListener('beforeunload', this.handlerClose);
  },
  watch: {
    param_r(val) {
      this.checkR(val);
    },
  },
  methods: {
    handleClose() {
      localStorage.removeItem("par");
    },
    goBack() {
      localStorage.removeItem("par");
      this.$router.push({name: 'auth-page'});
    },
    clickOnSVG() {
      if (this.checkR(this.param_r)) {
        this.param_x = (event.offsetX - 100) / 80 * this.param_r;
        this.param_y = (100 - event.offsetY) / 80 * this.param_r;
        this.sendRequestWithArgs();
      } else {
        alert('Не выбран радиус R!');
      }
    },
    sendRequestWithArgs() {
      const requestOptions = {
        method: "POST",
        headers: {"Content-Type": "application/json", "Authorization": "Bearer " + localStorage.getItem("par")},
        body: JSON.stringify({"x": this.param_x, "y": this.param_y, "r": this.param_r})
      };
      const address = "/api/data/add-data";
      this.sendRequest(address, requestOptions);
    },
    loadData() {
      const requestOptions = {
        method: "GET",
        headers: {"Authorization": "Bearer " + localStorage.getItem("par")},
      };
      const address = "/api/data/get-data";
      this.sendRequestWithData(address, requestOptions);
    },
    clear() {
      const requestOptions = {
        method: "DELETE",
        headers: {"Authorization": "Bearer " + localStorage.getItem("par")},
      };
      const address = "/api/data/delete";
      this.sendRequest(address, requestOptions);
      this.data = [];
      this.param_x = -5;
      this.param_r = 1;
      document.getElementById("inputY").value = "";
      document.querySelector("#inputY").classList.remove('errorY');
    },
    sendRequestWithData(address, requestOptions) {
      fetch(address, requestOptions)
          .then(response => {
            if (response.ok) return response.json();
            else {
              return response.text().then(text => {
                throw new Error(text)
              });
            }
          }).then(data => {
        this.data = data;
      }).catch((e) => {
        this.showError(e.message);
      });
    },
    sendRequest(address, requestOptions) {
      fetch(address, requestOptions)
          .then(response => {
            if (response.ok) return response;
            else {
              return response.text().then(text => {
                throw new Error(text)
              });
            }
          }).then(() => {
        this.loadData();
      }).catch((e) => {
        this.showError(e.message);
      });
    },
    checkY(y) {
      const MAX = 3;
      const MIN = -3;
      if (!isNaN(y) && parseFloat(y) > MIN && parseFloat(y) < MAX) {
        document.querySelector('#inputY').classList.remove('errorY');
        return true;
      } else {
        document.querySelector('#inputY').classList.add('errorY');
        this.showError("Y должен быть в пределах (-3; 3)")
        return false;
      }
    },
    checkR(r) {
      const MAX = 3;
      const MIN = 0;
      if (!isNaN(r) && parseFloat(r) > MIN && parseFloat(r) <= MAX)
        return true;
      else {
        this.showError("R должен быть выбран и находиться в пределах (0;3]")
        return false;
      }
    },
    checkX(x) {
      const MAX = 3;
      const MIN = -5;
      if (!isNaN(x) && parseFloat(x) >= MIN && parseFloat(x) <= MAX)
        return true;
      else {
        this.showError("X должен быть выбран и находиться в пределах [-5;3]")
        return false;
      }
    },
    submit() {
      if (this.checkX(this.param_x) && this.checkY(this.param_y) && this.checkR(this.param_r)) this.sendRequestWithArgs();
    },
    showError(text) {
      this.$notify({
        group: "error",
        title: 'Ошибка',
        text: text,
        type: 'error'
      });
    }
  },
  mounted() {
    this.loadData();
  }
}
</script>
<style>

select {
  width: 165px;
}

.errorY {
  border-color: red;
  background-color: rgba(234, 111, 145, 0.97);
}

#div-inline div {
  vertical-align: middle;
  margin: 20px 20px 20px;
  text-align: center;
}


.main-background > div:first-child {
  display: table;
  margin: 0 auto;
}

#result-table {
  overflow-x: auto;
  height: 300px;
  margin: 10px 20px;
}

.div-block {
  display: block;
}

.div-inline {
  display: inline-block;
}

#div-buttons {
  padding: 1.5% 1.5% 1.5% 1.5%;
}

</style>