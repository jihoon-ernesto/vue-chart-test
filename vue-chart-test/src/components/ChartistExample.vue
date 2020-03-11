<template>
  <div id='container'>
    <!-- TODO: handle the css properly -->
    <link rel="stylesheet" href="//cdn.jsdelivr.net/chartist.js/latest/chartist.min.css">
    <vue-chartist
      :type="this.type"
      :data="this.chartData.data"
      :options="this.chartData.options"
      ></vue-chartist>
  </div>
</template>

<script>
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
