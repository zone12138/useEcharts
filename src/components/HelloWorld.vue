<template>
  <div class="hello" ref="chart">
    
  </div>
</template>

<script setup>
import { ref, inject, onMounted } from 'vue'

const echarts = inject('$echarts')
const chart = ref(null)


onMounted(() => {
  const myChart = echarts.init(chart.value)
  /** @type EChartsOption */
  myChart.setOption({
    title: {
      text: 'ECharts 入门示例',
      subtext: '纯属虚构',
      left: 'center'
    },
    tooltip: {},
    xAxis: {
      data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
    },
    yAxis: {},
    series: [{
      name: '销量',
      type: 'bar',
      data: [5, 20, 36, 10, 10, 20]
    }]
  })
})
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  height: 500px;
  width: 1000px;
}
</style>
