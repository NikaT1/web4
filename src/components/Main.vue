<template>
  <table id="main-table">
    <tr>
      <td>
        <table id="head-table">
          <Header/>
        </table>
      </td>
    </tr>
    <tr>
      <td>
        <table id="body-table" class="body-table">
          <tr class="background-with-shadow" id="background-tr">
            <td>
              <table class="background" id="background-table">
                <tr>
                  <td>
                    <div id="svg-picture">
                      <svg id="svg" width="210" height="210" xmlns="http://www.w3.org/2000/svg" @click="clickOnSVG">
                        <polygon points="100,100 100,20 180,100"
                                 class="svg-figure-color"
                                 stroke-width="2"></polygon>
                        <polygon points="100,140 20,140 20,100 100,100"
                                 class="svg-figure-color"
                                 stroke-width="2"></polygon>
                        <path d="M100,100 v+40 a40,40 0 0,0 40,-40z"
                              class="svg-figure-color"
                              stroke-width="2"></path>
                        <line x1="100" y1="0" x2="100" y2="200" stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="0" y1="100" x2="200" y2="100" stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="97" y1="60" x2="103" y2="60" stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="97" y1="20" x2="103" y2="20" stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="97" y1="140" x2="103" y2="140" stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="97" y1="180" x2="103" y2="180" stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="60" y1="97" x2="60" y2="103" stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="20" y1="97" x2="20" y2="103" stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="140" y1="97" x2="140" y2="103" stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="180" y1="97" x2="180" y2="103" stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="100" y1="0" x2="95" y2=10 stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="100" y1="0" x2="105" y2=10 stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="200" y1="100" x2="190" y2=105 stroke-width="2"
                              class="svg-line-color"></line>
                        <line x1="200" y1="100" x2="190" y2=95 stroke-width="2"
                              class="svg-line-color"></line>
                        <text x="30" y="92" font-size="15" class="svg-text">-R/2</text>
                        <text x="6" y="92" font-size="15" class="svg-text">-R</text>
                        <text x="107" y="30" font-size="15" class="svg-text">R</text>
                        <text x="107" y="70" font-size="15" class="svg-text">R/2</text>
                        <text x="110" y="10" font-size="15" class="svg-text">y</text>
                        <text x="130" y="92" font-size="15" class="svg-text">R/2</text>
                        <text x="170" y="92" font-size="15" class="svg-text">R</text>
                        <text x="190" y="92" font-size="15" class="svg-text">x</text>
                        <text x="107" y="140" font-size="15" class="svg-text">-R/2</text>
                        <text x="107" y="180" font-size="15" class="svg-text">-R</text>
                      </svg>
                    </div>
                  </td>
                  <td>
                    <img id="imagine3" class="imagine3" src="../images/pic3.png" alt="Милый хомячок"/>
                  </td>
                  <td rowspan="2" class="background" id="result-td">
                    <div id="result-div">
                      <table id="result-table" class="result-style">
                        <thead>
                        <tr>
                          <th id="real-time" class="result-style">Текущее время</th>
                          <th id="X" class="result-style">X</th>
                          <th id="Y" class="result-style">Y</th>
                          <th id="R" class="result-style">R</th>
                          <th id="flag" class="result-style">Результат</th>
                        </tr>
                        </thead>
                        <tbody>
                        <tr v-for="point in data" :key="point">
                          <td>{{ point.time }}</td>
                          <td>{{ point.x }}</td>
                          <td>{{ point.y }}</td>
                          <td>{{ point.r }}</td>
                          <td>{{ point.answer }}</td>
                        </tr>
                        </tbody>
                      </table>
                    </div>
                  </td>
                </tr>
                <tr>
                  <td colspan="2">
                    <table id="numbers-table" class="background">
                      <tr class="numbers">
                        <td>X:</td>
                        <td>
                          <table id="x-table">
                            <tr>
                              <td>
                                <label> <input name="xCheckbox" v-model="param_x" class="defaultBox"
                                               type="checkbox" value="-5" checked :disabled="hasAdditionalX">
                                  <p>
                                    -5
                                  </p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="xCheckbox" v-model="param_x" type="checkbox"
                                         value="-4" :disabled="hasAdditionalX">
                                  <p>
                                    -4
                                  </p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="xCheckbox" v-model="param_x" type="checkbox"
                                         value="-3" :disabled="hasAdditionalX">
                                  <p>
                                    -3
                                  </p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="xCheckbox" v-model="param_x" type="checkbox"
                                         value="-2" :disabled="hasAdditionalX">
                                  <p>
                                    -2
                                  </p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="xCheckbox" v-model="param_x" type="checkbox"
                                         value="-1" :disabled="hasAdditionalX">
                                  <p>
                                    -1
                                  </p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="xCheckbox" v-model="param_x" type="checkbox"
                                         value="0" :disabled="hasAdditionalX">
                                  <p>
                                    0
                                  </p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="xCheckbox" v-model="param_x" type="checkbox"
                                         value="1" :disabled="hasAdditionalX">
                                  <p>1
                                  </p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="xCheckbox" v-model="param_x" type="checkbox"
                                         value="2" :disabled="hasAdditionalX">
                                  <p>2
                                  </p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="xCheckbox" v-model="param_x" type="checkbox"
                                         value="3" :disabled="hasAdditionalX">
                                  <p>3
                                  </p>
                                </label>
                              </td>
                              <td colspan = "2">
                                <button class="button" @click="undoX">
                                  снять выделение
                                </button>
                              </td>
                            </tr>
                          </table>
                        </td>
                      </tr>
                      <tr>
                        <td>Y:</td>
                        <td>
                          <input type="text" id="inputY" name="y" maxlength="17" autocomplete="off"
                                 placeholder="Введите число: (-3; 3)" v-model="param_y">
                        </td>
                      </tr>
                      <tr class="numbers">
                        <td>R:</td>
                        <td>
                          <table id="r-table">
                            <tr>
                              <td>
                                <label> <input name="rCheckbox" v-model="param_r" type="checkbox"
                                               value="-5" :disabled="hasAdditionalR">
                                  <p>-5</p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="rCheckbox" v-model="param_r" type="checkbox"
                                         value="-4" :disabled="hasAdditionalR">
                                  <p>-4</p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="rCheckbox" v-model="param_r" type="checkbox"
                                         value="-3" :disabled="hasAdditionalR">
                                  <p>-3</p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="rCheckbox" v-model="param_r" type="checkbox"
                                         value="-2" :disabled="hasAdditionalR">
                                  <p>-2</p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="rCheckbox" v-model="param_r" type="checkbox"
                                         value="-1" :disabled="hasAdditionalR">
                                  <p>-1</p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="rCheckbox" v-model="param_r" type="checkbox"
                                         value="0" :disabled="hasAdditionalR">
                                  <p>0</p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="rCheckbox" v-model="param_r" type="checkbox" class="defaultBox"
                                         value="1" :disabled="hasAdditionalR">
                                  <p>1</p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="rCheckbox" v-model="param_r" type="checkbox"
                                         value="2" :disabled="hasAdditionalR">
                                  <p>2</p>
                                </label>
                              </td>
                              <td>
                                <label>
                                  <input name="rCheckbox" v-model="param_r" type="checkbox"
                                         value="3" :disabled="hasAdditionalR">
                                  <p>3</p>
                                </label>
                              </td>
                              <td colspan = "3" class="tr-for-buttons">
                                <button class="button" @click="undoR">
                                  снять выделение
                                </button>
                              </td>
                            </tr>
                          </table>
                        </td>
                      </tr>
                      <tr class="tr-for-buttons">
                        <td colspan="2">
                          <button class="button" @click="goBack">
                            выйти
                          </button>
                        </td>
                        <td colspan="2">
                          <button class="button" id="submit" @click="submit">
                            результат
                          </button>
                        </td>
                        <td colspan="2">
                          <button class="button" id="reset" @click="clear">
                            очистить
                          </button>
                        </td>
                      </tr>
                    </table>
                  </td>
                </tr>
              </table>
            </td>
          </tr>
        </table>
      </td>
    </tr>
  </table>
</template>

<script>
import Header from "@/components/Header";

export default {
  components: {
    Header
  },
  name: 'Main',
  data() {
    return {
      param_x: [-5],
      param_y: "",
      param_r: [1],
      data: new Array(0)
    }
  },
  watch: {
    param_r(val) {
      if (val.length > 0 && !isNaN(val[0]) && parseFloat(val[0]) > 0 && parseFloat(val[0]) <= 3) {
        this.drawAll();
      }
    }
  },
  methods: {
    undoR(){
      this.param_r = [];
    },
    undoX(){
      this.param_x = [];
    },
    goBack(){
      localStorage.removeItem("par");
      this.$router.push({name: 'auth-page'});
    },
    clickOnSVG() {
      if (this.checkR(this.param_r)) {
        this.param_x[0] = (event.offsetX - 100) / 80 * this.param_r[0];
        this.param_y = (100 - event.offsetY) / 80 * this.param_r[0];
        this.sendRequestWithArgs();
      } else {
        alert('Не выбран радиус R!');
      }
    },
    sendRequestWithArgs() {
      const requestOptions = {
        method: "POST",
        headers: {"Content-Type": "application/json", "Authorization": "Bearer " + localStorage.getItem("par")},
        body: JSON.stringify({"x": this.param_x[0], "y": this.param_y, "r": this.param_r[0]})
      };
      fetch("/api/data/add-data", requestOptions)
      .then(response => {
        if (response.ok) return response;
        else {
          let error = new Error(response.statusText);
          error.response = response;
          throw error
        }
      }).then(() => (this.loadData())).catch((e) => {
            this.showError(e.response);
          });
    },
    loadData() {
      const requestOptions = {
        method: "GET",
        headers: {"Authorization": "Bearer " + localStorage.getItem("par")},
      };
      fetch("/api/data/get-data", requestOptions)
          .then(response => {
            if (response.ok) return response.json();
            else {
              let error = new Error(response.statusText);
              error.response = response;
              throw error
            }
          }).then(data => {
        this.data = data;
        this.drawAll();
      }).catch((e) => {
        this.showError(e.response);
      });
    },
    drawAll() {
      this.deletePointsFromSVG();
      if (this.data.length !== 0) {
        for (let i = 0; i < this.data.length; i++) {
          let point = this.data[i];
          const x = point.x;
          const y = point.y;
          const r = point.r;
          const ans = point.answer;
          let flagForR;
          let flagForColor;
          if (!isNaN(x) && !isNaN(y)) {
            flagForColor = ans.includes("да");
            if (this.param_r.length > 0) {
              flagForR = (this.param_r[0] == r);
              this.drawPoint(x, y, this.param_r[0], flagForColor, flagForR);
            } else {
              flagForR = (1 == r);
              this.drawPoint(x, y, 1, flagForColor, flagForR);
            }
          }
        }
      }
    },
    drawPoint(x, y, r, flagForColor, flagForR) {
      let point = document.createElementNS("http://www.w3.org/2000/svg", 'circle');
      point.setAttribute('cx', (80 * x / r + 100).toString());
      point.setAttribute('cy', (-80 * y / r + 100).toString());
      point.setAttribute('r', (3).toString());
      point.setAttribute('data-x', x);
      point.setAttribute('data-y', y);
      if (!flagForR) point.classList.add("old-coord");
      else if (flagForColor)
        point.classList.add("good-coord");
      else point.classList.add("bad-coord");
      document.getElementById("svg").appendChild(point);
    },
    deletePointsFromSVG() {
      document.querySelectorAll(".good-coord").forEach(x => x.remove());
      document.querySelectorAll(".bad-coord").forEach(x => x.remove());
      document.querySelectorAll(".old-coord").forEach(x => x.remove());
    },
    clear() {
      const requestOptions = {
        method: "DELETE",
        headers: {"Authorization": "Bearer " + localStorage.getItem("par")},
      };
      fetch("/api/data/delete", requestOptions)
          .then(() => {
            //document.getElementById('result-table').getElementsByTagName("tbody")[0].remove();
            this.data = [];
            document.getElementById("inputY").value = "";
            document.querySelector("#inputY").classList.remove('errorY');
            document.querySelectorAll('input[name="rCheckbox"]').forEach(r => r.checked = false);
            document.querySelectorAll('input[name="xCheckbox"]').forEach(x => x.checked = false);
            document.querySelectorAll('.defaultBox').forEach(x => x.checked = true);
            this.deletePointsFromSVG();
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
      if (r.length > 0 && !isNaN(r[0]) && parseFloat(r[0]) > MIN && parseFloat(r[0]) <= MAX)
        return true;
      else {
        this.showError("R должен быть выбран и находиться в пределах (0;3]")
        return false;
      }
    },
    checkX(x) {
      const MAX = 3;
      const MIN = -5;
      if (x.length > 0 && !isNaN(x[0]) && parseFloat(x[0]) >= MIN && parseFloat(x[0]) <= MAX)
        return true;
      else {
        this.showError("X должен быть выбран и находиться в пределах [-5;3]")
        return false;
      }
    },
    submit() {
      if (this.checkX(this.param_x) && this.checkY(this.param_y) && this.checkR(this.param_r)) this.sendRequestWithArgs();
    },
    showError(text){
      this.$notify({
        group: "error",
        title: 'Error',
        text: text,
        type: 'error'
      });
    }
  },
  computed: {
    hasAdditionalR() {
      return this.param_r.length > 0
    },
    hasAdditionalX() {
      return this.param_x.length > 0
    }
  },
  mounted() {
    document.querySelectorAll('.defaultBox').forEach(x => {
      x.checked = true;
    });
    this.loadData();
  }
}
</script>
<style>
.body {
  color: #6d747f;
  font-size: 26px;
  font-family: "Open Sans", cursive;
  background-color: #FFEBCD;
}

table {
  color: #6d747f;
  font-size: 26px;
  font-family: "Open Sans", cursive;
  margin: auto;
  padding: 10px;
  border-radius: 10px;
  border-spacing: 10px;
  table-layout: auto;
}

#body-table {
  table-layout: fixed;
  height: 80%;
}

input[type='radio'] {
  padding: 7%;
  margin: 7%;
}

.good-coord {
  stroke: rgb(98, 236, 151);
  fill: rgb(98, 236, 151);
}

.bad-coord {
  stroke: rgb(221, 76, 122);
  fill: rgb(221, 76, 122);
}

.old-coord {
  stroke: rgba(206, 73, 229, 0.7);
  fill: rgba(206, 73, 229, 0.7);
}

input[type='text'] {
  font-family: cursive;
  display: inline-block;
}

.tr-for-buttons{
  text-align: left;
}

#head-table {
  width: 100%;
  border-spacing: 0;
  padding-top: 0;
}

#body-table {
  font-size: 20px;
  margin: auto;
  height: 550px;
}

.body-table {
  background-color: #f1d2ff;
}

#numbers-table {
  padding: 0;
  margin: 0;
  width: 80%;
  font-size: 20px;
}

.background-with-shadow {
  background-image: url("../images/picture1.jpg");
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  box-shadow: 0 0 8px 8px #f1d2ff inset;
}

.background {
  background: rgba(255, 240, 245, 0.45);
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  border-radius: 10px;
}

select {
  width: 165px;
}

.numbers {
  text-align: center;
  vertical-align: middle;
}

.button {
  font-family: cursive;
  font-weight: 700;
  text-decoration: none;
  padding: .8em 1em calc(.8em + 3px);
  border-radius: 3px;
  background: rgba(217, 182, 252, 0.76);
  box-shadow: 0 -3px rgba(217, 182, 252, 0.76) inset;
  transition: 0.2s;
}

.button:hover {
  background: rgba(163, 113, 196, 0.73);
}

.button:active {
  outline: none;
  background: rgba(163, 113, 196, 0.73);
  box-shadow: 0 3px rgba(163, 113, 196, 0.73) inset;
}

.result-style tbody td {
  border-collapse: collapse;
  border: 4px solid rgba(217, 185, 230, 0.6);
  font-size: 20px;
}

.result-style tbody th {
  border-collapse: collapse;
  border: 4px solid rgba(217, 185, 230, 0.6);
  font-size: 20px;
}

.errorY {
  border-color: red;
  background-color: rgba(234, 111, 145, 0.97);
}


.imagine3 {
  width: 210px;
  height: 210px;
}

#result-table::first-line {
  text-transform: uppercase;
  font-weight: bold;
}

#result-table {
  border-collapse: collapse;
  text-align: center;
  border: 4px solid rgba(217, 185, 230, 0.6);
  font-size: 20px;
  width: 100%;
  table-layout: fixed;
}

#r-table, #x-table {
  padding: 0;
  margin: 0;
  table-layout: fixed;
  font-size: 20px;
}

::-webkit-scrollbar {
  width: 10px;
}

::-webkit-scrollbar-track {
  box-shadow: inset 0 0 6px rgba(206, 91, 238, 0.49);
}

::-webkit-scrollbar-thumb {
  box-shadow: inset 0 0 6px rgba(206, 91, 238, 0.49);
}

#result-div {
  overflow-x: auto;
  height: 300px;
}

#result-td {
  width: 100%;
}

.svg-line-color {
  stroke: rgb(104, 90, 110);
}

.svg-figure-color {
  fill: rgb(234, 234, 234);
  stroke: rgb(161, 133, 171);
}

</style>