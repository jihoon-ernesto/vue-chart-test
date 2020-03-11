
<script>
import { Line } from 'vue-chartjs'

export default {
  name: 'chart-js-example',
  extends: Line,
  props: {
  },
  data() {
    return {
      chartData: {
        labels: [
          '2019 September',
          '2019 October',
          '2019 November',
          '2019 December',
          '2020 January',
          '2020 February',
          '2020 March'
        ],
        datasets: [
          {
            label: 'user count',
            data: [ 23452, 25262, 30760, 28960, 31234, 34503, 27689 ],
          }
        ],
      },
      chartOptions: {
        responsive: false,
        elements: {
          line: {
            tension: 0,
          }
        },
      },
    };
  },
  mounted() {
    console.log(this.$options.name + " mounted.");

    this.renderChart(this.chartData, this.chartOptions);
  },
}
</script>

<style scoped>
</style>
