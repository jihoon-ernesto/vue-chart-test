<template>
  <div id='container'>
    <p>{{ title }}</p>
    <div class='chart-box'>
      <line-chart :data="chartData" :options="options"/>
    </div>
  </div>
</template>

<script>
import 'tui-chart/dist/tui-chart.css'
import { lineChart } from '@toast-ui/vue-chart'

export default {
  name: 'toast-chart-example',
  props: {
    title: String
  },
  components: {
    'line-chart': lineChart
  },
  data() {
      return {
        chartData: {
          categories: [
            '2019 September',
            '2019 October',
            '2019 November',
            '2019 December',
            '2020 January',
            '2020 February',
            '2020 March'
          ],
          series: [
            {
              name: 'user count',
              data: [ 23452, 25262, 30760, 28960, 31234, 34503, 27689 ]
            }
          ]
        },
        options: {
          chart: {
            width: 800,
            height: 600
          },
        },
      }
  },
  mounted() {
    console.log(this.title + " mounted.");
  },
}
</script>

<style scoped>
#container {
  margin-top: 50px;
}
.chart-box {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
