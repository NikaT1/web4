<template>
  <header>
    <div id="title"><h1>Калькулятор попадания в область</h1></div>
    <div class="name-div">
      Тройникова Вероника Дмитриевна
    </div>
    <div class="variant-div">
      Группа Р3233, вариант 3387
    </div>
    <nav>
      <a href="https://vk.com/akino_rev">ВКонтакте</a>
      <a href="https://vk.com/some_link">Telegram</a>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>
header {
  font-size: medium;
  display: table;
  padding: 2em 5% 2% 5%;
  background: #55555d;
  color: #cac8c8;
  width: 100%;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  alignment: left;
}

header nav {
  display: table-cell;
  vertical-align: middle;
  text-align: right;
  color: #ababab;
}

header nav a {
  margin: 0 0 5% 5%;
  font-size: larger;
}

.name-div, .variant-div {
  font-size: medium;
  color: #ababab;
}

#title {
  background: #413f47;
  margin: 0 0 1% 0;
  width: fit-content;
  padding: 2em 2em 2em 2em;
  border-radius: 2px;
}

@media (max-width: 1228px) {
  div {
    font-size: 20px;
    padding: 6px;
    border-radius: 6px;
    border-spacing: 6px;
  }

  .variant-div {
    font-size: 15px;
    border-spacing: 4px;
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
