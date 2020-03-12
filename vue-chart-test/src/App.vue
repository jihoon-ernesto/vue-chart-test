<template>
  <div id="app" class="container">
    <p>my chartist example</p>
    <ChartistExample class="chart"
      type="Line"
      :chartData="dataForChartist"
    />

    <p>my chart.js example</p>
    <ChartJsExample class="chart"
      :chartData="dataForChartJS"
      :width="srcData.width"
      :height="srcData.height"
    />

    <p>my toast-chart example</p>
    <ToastChartExample class="chart"
      :chartData="dataForToastChart"
    />
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
    dataForChartist() {
      return {
        data: {
          labels: this.srcData.labels,
          series: [ this.srcData.series[0].data ],
        },
        options: {
          width: this.srcData.width,
          height: this.srcData.height,
        },
      };
    },

    dataForChartJS() {
      return {
        data: {
          labels: this.srcData.labels,
          datasets: [
            {
              label: this.srcData.series[0].name,
              data: this.srcData.series[0].data,
            }
          ],
        },
        options: {
          responsive: false,
          elements: {
            line: {
              tension: 0,
            }
          },
        }
      };
    },

    dataForToastChart() {
      return {
        data: {
          categories: this.srcData.labels,
          series: this.srcData.series,
        },
        options: {
          chart: {
            width: this.srcData.width,
            height: this.srcData.height,
          },
        },
      };
    },
  },

  data() {
    return {
      srcData: {
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
          {
            name: 'user count',
            data: [ 23452, 25262, 30760, 28960, 31234, 34503, 27689 ],
          }
        ],
        width: 800,
        height: 600,
      },
    };
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
