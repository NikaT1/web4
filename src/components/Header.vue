<template>
  <tr>
    <td>
      <table id="head-table">
        <tr>
          <td>
            <table id="name-table" class="name-table">
              <tr>
                <td>Тройникова Вероника Дмитриевна, группа Р3233</td>
              </tr>
            </table>
          </td>
        </tr>
        <tr>
          <td>
            <table id="variant-table" class="variant-table">
              <tr>
                <td>
                  <div id = "var" >Вариант 3387</div>
                </td>
              </tr>
            </table>
          </td>
        </tr>
      </table>
    </td>
  </tr>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>
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

#variant-table {
  width: 90%;
  font-size: 20px;
  margin: auto;
  border-spacing: 5px;
}

</style>
