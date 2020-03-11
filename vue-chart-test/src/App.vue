<template>
  <div id="app">
    <ChartistExample title="my chartist example" />
    <ChartJsExample title="my chart.js example" />
    <ToastChartExample title="my toast-chart example" />
  </div>
</template>

<script>
import ChartistExample from './components/ChartistExample.vue'
import ChartJsExample from './components/ChartJsExample.vue'
import ToastChartExample from './components/ToastChartExample.vue'

export default {
  name: 'App',
  components: {
    ChartistExample,
    ChartJsExample,
    ToastChartExample,
  },
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
