<template>
  <div>
    <h1>Smartphones under RS.20000 in 2023 {{barName}}</h1>
    <Chart :type="bar" :data="barData" />
  </div>

</template>

<script>

import Chart from './components/chart.vue';
import data from './assets/smartphones_2023.json';


export default {
  name: 'App',
  components: {
    Chart,
  },
  data() {
  return {
    barName: 'Bar Chart',
    bar: 'bar',
    barData: {
      labels: data.map(item => item.Model),
      datasets: [{
        label: 'Price Range (INR)',
        data: data.map(item => item['Price Range (INR)']),
        backgroundColor: [
          'rgba(17, 50, 64, 0.4)',
          'rgba(94, 72, 0, 0.4)',
          'rgba(171, 122, 232, 0.4)',
          'rgba(27, 25, 169, 0.4)',
          'rgba(141, 47, 108, 0.4)'
        ],
        borderColor: [
          'rgba(17, 50, 64, 1)',
          'rgba(94, 72, 0, 1)',
          'rgba(171, 122, 232, 1)',
          'rgba(27, 25, 169, 1)',
          'rgba(141, 47, 108, 1)'
        ],
        borderWidth: 2
      }]
    },
  }
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
</style>
