<template>
  <div id="app">
    <MainApp></MainApp>
  </div>
</template>

<script>
import MainApp from './templates/MainApp.vue'

  export default {
    components: { MainApp },
    data () {
      return {
      }
    }
  }
</script>

<style>
html body {
  height: 100%;
  margin: 0;
}
</style>