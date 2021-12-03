<template>
  <table id="main-table">
    <Header/>
    <Main/>
  </table>
</template>

<script>
import Main from './components/Main.vue'
import Header from "@/components/Header.vue";
export default {
  name: 'App',
  components: {
    Header,
    Main
  }
}
</script>