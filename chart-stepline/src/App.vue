<template>
  <div id="chart">
    <apexchart type="line" height="350" :options="chartOptions" :series="series"></apexchart>
  </div>
</template>

<script>
import VueApexCharts from 'vue-apexcharts'

export default {
  name: 'App',
  components: {
    apexchart: VueApexCharts,
  },
  data:() => ({
    
    series: [{
      data: [{ x: '05/06/2014', y: 54 }, { x: '05/08/2014', y: 17 } , { x: '06/01/2014', y: 26 }]
    }],
    chartOptions: {
      chart: {
        type: 'line',
        height: 350
      },
      stroke: {
        curve: 'stepline',
      },
      xaxis:{
        type: 'datetime',
      },
      dataLabels: {
        enabled: false
      },
      title: {
        text: 'Stepline Chart',
        align: 'left'
      },
      markers: {
        hover: {
          sizeOffset: 4
        }
      }
    },
  }),
}
</script>

<style>
</style>
