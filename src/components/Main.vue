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
                        <polygon points="180,100 100,140 100,100"
                                 class="svg-figure-color"
                                 stroke-width="2"></polygon>
                        <polygon points="100,20 180,20 180,100 100,100"
                                 class="svg-figure-color"
                                 stroke-width="2"></polygon>
                        <path d="M100,100 v-80 a80,80 0 0,0-80,80z"
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
                        <tr>
                          <th id="real-time" class="result-style">Текущее время</th>
                          <th id="time" class="result-style">Время исполнения</th>
                          <th id="X" class="result-style">X</th>
                          <th id="Y" class="result-style">Y</th>
                          <th id="R" class="result-style">R</th>
                          <th id="flag" class="result-style">Результат</th>
                        </tr>
                        <tr>
                          <td>
                          </td>
                          <td>
                          </td>
                          <td>
                          </td>
                          <td>
                          </td>
                          <td>
                          </td>
                          <td>
                          </td>
                        </tr>
                      </table>
                    </div>
                  </td>
                </tr>
                <tr>
                  <td colspan="2">
                    <table id="numbers-table" class="background">
                      <tr>
                        <td>X:</td>
                        <td>
                          <div class="special-checkbox">
                            <CheckboxRadio name="xCheckBox"></CheckboxRadio>
                          </div>
                        </td>
                      </tr>
                      <tr>
                        <td>Y:</td>
                        <td>
                          <input type="text" id="inputY" maxlength="17" autocomplete="off"
                                 placeholder="Введите число: (-3; 3)" value="">
                        </td>
                      </tr>
                      <tr class="numbers">
                        <td>R:</td>
                        <td>
                          <table id="r-table">
                            <tr>
                              <div class="special-checkbox">
                                <CheckboxRadio name="rCheckBox"></CheckboxRadio>
                              </div>
                              <td colspan="2">
                                <button class="button" id="submit" @click="submit">
                                  результат
                                </button>
                              </td>
                              <td colspan="3">
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
      </td>
    </tr>
  </table>
</template>

<script>
import Header from "@/components/Header";
import CheckboxRadio from './CheckboxRadio'

export default {
  components: {
    CheckboxRadio,
    Header
  },
  name: 'Main',
  data() {
    return {
      param_x: "",
      param_y: "",
      param_r: "5",
      dots: new Array(0)
    }
  },
  methods: {
    clickOnSVG() {
      if (this.checkR()) {
        this.param_x = (event.offsetX - 100) / 80 * this.param_r;
        this.param_y = (100 - event.offsetY) / 80 * this.param_r;
        this.sendRequestWithArgs();
      } else {
        alert('Не выбран радиус R!');
      }
    },
    sendRequestWithArgs() {
      /*const requestOptions = {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ x: this.param_x, y: this.param_y, r: this.param_r })
      };
      /*fetch("/api/user/post", requestOptions)
          .then(() => (this.loadData()));*/
    },
    checkR() {
      let boxes = document.querySelectorAll('CheckboxRadio');
      for (let elem in boxes) {
        if (boxes[elem].checked)
          this.param_r = boxes[elem].value;
      }
      return true;
    },
    clear() {
      document.getElementById('result-table').getElementsByTagName("tbody")[0].innerHTML = document.getElementById("result-table").rows[0].innerHTML;
      document.getElementById("inputY").value = "";
      document.querySelector("#inputY").classList.remove('errorY');
      document.querySelectorAll('input[name="rCheckBox"]').forEach(r => r.checked = false);
      document.querySelectorAll('input[name="xCheckBox"]').forEach(x => x.checked = false);
      document.querySelectorAll('.defaultBox').checked = true;
    },
    submit() {
      function checkX() {
        let boxes = document.querySelectorAll('input[name="xCheckBox"]');
        for (let elem in boxes) {
          if (boxes[elem].checked)
            this.param_x = boxes[elem].value;
        }
        return true;
      }

      function checkY() {
        let line = document.querySelector("#inputY").value;
        line = line.replace(",", ".");
        let regex = /^[-]?[0-9]{1,17}([.][0-9]{1,17}|[0-9]{0,17})$/;
        let OK = regex.exec(line);
        let y = parseFloat(line);
        const MAX = 3;
        const MIN = -3;
        if (!isNaN(y) && y > MIN && y < MAX && OK) {
          this.param_y = y;
          document.querySelector('#inputY').classList.remove('errorY');
          return true;
        } else {
          return false;
        }
      }

      if (checkY() && checkX() && this.checkR()) {
        this.sendRequestWithArgs();
      } else {
        document.querySelector('#inputY').classList.add('errorY');
      }
    }
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

#imagine {
  width: 210px;
  height: 210px;
}

input[type='radio'] {
  padding: 7%;
  margin: 7%;
}

input[type='text'] {
  font-family: cursive;
  display: inline-block;
}

#name-table {
  width: 100%;
  border-spacing: 7px;
}

.name-table {
  background-color: #dab6ea;
}

.variant-table {
  background-color: #f1d2ff;
}

#head-table {
  width: 100%;
  border-spacing: 0;
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
}

#variant-table {
  width: 90%;
  font-size: 20px;
  margin: auto;
  border-spacing: 5px;
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

#r-table {
  padding: 0;
  margin: 0;
  table-layout: fixed;
}

#selectY {
  font-family: cursive;
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

.coord {
  stroke: rgb(122, 3, 171);
  fill: rgb(122, 3, 171);
}

.old-coord {
  stroke: rgba(206, 73, 229, 0.7);
  fill: rgba(206, 73, 229, 0.7);
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