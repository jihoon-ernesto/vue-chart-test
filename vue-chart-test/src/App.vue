<template>
  <div id="app">
    <ChartistExample title="my chartist example" />
  </div>
</template>

<script>
import ChartistExample from './components/ChartistExample.vue'

export default {
  name: 'App',
  components: {
    ChartistExample,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
