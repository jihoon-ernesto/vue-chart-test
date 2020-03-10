<template>
  <div id='chart-user-count'>
    <!-- TODO: handle the css properly -->
    <link rel="stylesheet" href="//cdn.jsdelivr.net/chartist.js/latest/chartist.min.css">
    <p>{{ title }}</p>
  </div>
</template>

<script>
import Chartist from 'chartist';

export default {
  name: 'chartist-example',
  props: {
    title: String
  },
  mounted() {
    console.log(this.title + " mounted.");

    new Chartist.Line('#chart-user-count',
      // data
      {
        labels: [
          '2019 September',
          '2019 October',
          '2019 November',
          '2019 December',
          '2020 January',
          '2020 February',
          '2020 March'
        ],
        series: [[ 23452, 25262, 30760, 28960, 31234, 34503, 27689 ]]
      },
      // options
      {
        width: 800,
        height: 600,
        lineSmooth: Chartist.Interpolation.none({
          fillHoles: false
        }),
      });
  }
}
</script>

<style scoped>

</style>
