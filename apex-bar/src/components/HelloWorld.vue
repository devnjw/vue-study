<template>
  <div id="chart">
    <apexchart
      ref="barChart"
      height="350"
      :options="chartOptions"
      :series="series"
    >
    </apexchart>
  </div>
</template>

<script>
import VueApexCharts from 'vue-apexcharts'

export default {
  components: {
    apexchart: VueApexCharts,
  },
  data: () => ({
    series: [{
        data: [400, 430, 448, 470, 540, 580, 690, 1100, 1200, 1380]
    }],

    chartOptions: {
      
      chart: {
        type: 'bar',
        background: '#141c24',
        foreColor: '#fff',
      },
      xaxis: {
        categories: ['South Korea', 'Canada', 'United Kingdom', 'Netherlands', 'Italy', 'France', 'Japan',
          'United States', 'China', 'Germany'
        ],
      },
      plotOptions: {
        bar: {
          horizontal: true,
          distributed: true,
        },
      },
      colors: ['#33b2df', '#546E7A', '#d4526e', '#13d8aa', '#A5978B', '#2b908f', '#f9a3a4', '#90ee7e',
          '#f48024', '#69d2e7'
        ],

      stroke: {
        colors: ['transparent'],
        width: 8,
      },
    },
  }),

  methods: {

  },

  created() {
    
  }
}
</script>
