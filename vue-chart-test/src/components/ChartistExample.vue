<template>
  <div id='container'>
    <!-- TODO: handle the css properly -->
    <link rel="stylesheet" href="//cdn.jsdelivr.net/chartist.js/latest/chartist.min.css">
    <vue-chartist
      :type="type"
      :data="chartData.data"
      :options="chartOptions"
      ></vue-chartist>
  </div>
</template>

<script>
import Chartist from 'chartist'
import VueChartist from 'v-chartist';

export default {
  name: 'chartist-example',
  props: {
    type: String,
    chartData: Object,
  },
  components: {
    'vue-chartist': VueChartist,
  },
  computed: {
    chartOptions() {
      return {
        ...this.chartData.options,
        lineSmooth: Chartist.Interpolation.none({
          fillHoles: false
        }),
      }
    },
  },
  data() {
    return {};
  },
  mounted() {
    console.log(this.$options.name + " mounted.");
  }
}
</script>

<style scoped>
</style>
