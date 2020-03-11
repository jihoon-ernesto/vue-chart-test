<template>
  <div id='chart-user-count'>
    <p>{{ title }}</p>
    <div class='canvas-box'>
      <canvas id="chart-canvas" :width="width" :height="height"></canvas>
    </div>
  </div>
</template>

<script>
import Chart from 'chart.js';

export default {
  name: 'chart-js-example',
  props: {
    title: String,
  },
  mounted() {
    console.log(this.title + " mounted.");

    let context = document.getElementById('chart-canvas').getContext('2d');
    new Chart(context, {
      type: 'line',
      data: {
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
        ]
      },
      options: {
        responsive: false,
        elements: {
          line: {
            tension: 0,
          }
        },
      }
    });

  },
  data() {
    return {
      width: 800,
      height: 600,
    };
  },
}
</script>

<style scoped>
.canvas-box {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
