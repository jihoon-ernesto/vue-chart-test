
<script>
import { Line } from 'vue-chartjs'

export default {
  name: 'chart-js-example',
  extends: Line,
  props: {
    chartData: Object,
  },
  data() {
    return {};
  },
  mounted() {
    console.log(this.$options.name + " mounted.");

    this.renderChart(this.chartData.data, this.chartData.options);
  },
}
</script>

<style scoped>
</style>
