<template>
  <div id='container'>
    <div class='chart-box'>
      <line-chart
        :data="chartData.data"
        :options="chartData.options"
      />
    </div>
  </div>
</template>

<script>
import 'tui-chart/dist/tui-chart.css'
import { lineChart } from '@toast-ui/vue-chart'

export default {
  name: 'toast-chart-example',
  props: {
    chartData: Object,
  },
  components: {
    'line-chart': lineChart
  },
  data() {
      return {};
  },
  mounted() {
    console.log(this.$options.name + " mounted.");
  },
}
</script>

<style scoped>
</style>
