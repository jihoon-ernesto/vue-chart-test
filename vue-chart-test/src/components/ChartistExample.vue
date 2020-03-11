<template>
  <div id='container'>
    <!-- TODO: handle the css properly -->
    <link rel="stylesheet" href="//cdn.jsdelivr.net/chartist.js/latest/chartist.min.css">
    <vue-chartist
      type="Line"
      :data="chartData"
      :options="chartOptions"
      ></vue-chartist>
  </div>
</template>

<script>
import VueChartist from 'v-chartist';

export default {
  name: 'chartist-example',
  props: {
  },
  components: {
    'vue-chartist': VueChartist,
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
        series: [
          [ 23452, 25262, 30760, 28960, 31234, 34503, 27689 ]
        ]
      },
      chartOptions: {
        width: 800,
        height: 600,
        // lineSmooth: Chartist.Interpolation.none({
        //   fillHoles: false
        // }),
      },
    };
  },
  mounted() {
    console.log(this.$options.name + " mounted.");
  }
}
</script>

<style scoped>

</style>
