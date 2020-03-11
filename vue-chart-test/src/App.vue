<template>
  <div id="app" class="container">
    <p>my chartist example</p>
    <ChartistExample class="chart" />

    <p>my chart.js example</p>
    <ChartJsExample class="chart"
      :width="chartWidth"
      :height="chartHeight"
    />

    <p>my toast-chart example</p>
    <ToastChartExample class="chart" />
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
  computed: {
    chartWidth: () => { return 800; },
    chartHeight: () => { return 600; },
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

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.chart {
  margin: 50px;
}
</style>
