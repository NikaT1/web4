<template>
  <table>
    <thead>
    <tr>
      <th id="real-time">Текущее время</th>
      <th id="X">X</th>
      <th id="Y">Y</th>
      <th id="R">R</th>
      <th id="flag">Результат</th>
    </tr>
    </thead>
    <tbody>
    <tr v-for="point in data" :key="point">
      <td>{{ point.time }}</td>
      <td>{{ point.x }}</td>
      <td>{{ point.y }}</td>
      <td>{{ point.r }}</td>
      <td v-if="point.answer">да</td>
      <td v-else>нет</td>
    </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: "ResultTable",
  props: ['data'],
}
</script>

<style scoped>

table {
  color: #6d747f;
  font-size: 26px;
  font-family: New Century Schoolbook, TeX Gyre Schola, serif;
  margin: auto;
  padding: 10px;
  border-radius: 10px;
  border-spacing: 10px;
  table-layout: auto;
}

table {
  border-collapse: collapse;
  text-align: center;
  border: 4px solid rgba(79, 72, 91, 0.6);
  font-size: 20px;
  width: 100%;
  table-layout: fixed;
}

td {
  border-collapse: collapse;
  border: 4px solid rgba(79, 72, 91, 0.6);
  font-size: 20px;
}

th {
  border-collapse: collapse;
  border: 4px solid rgba(79, 72, 91, 0.6);
  font-size: 20px;
}

table::first-line {
  text-transform: uppercase;
  font-weight: bold;
}

@media (max-width: 1228px) {
  table {
    font-size: 26px;
    padding: 10px;
    border-radius: 10px;
    border-spacing: 10px;
  }

  th, td {
    font-size: 20px;
  }
}

@media (max-width: 892px) {
  div {
    font-size: 16px;
    padding: 4px;
    border-radius: 4px;
    border-spacing: 4px;
  }

  .variant-div {
    font-size: 12px;
    border-spacing: 3px;
  }
}
</style>