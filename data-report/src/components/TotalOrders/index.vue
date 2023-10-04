<template>
  <div class="total-orders">
    <common-card
      title="累计订单"
      value="2,157,420"
    >
      <template>
        <div id="total-orders-chart" ref="totalOredersChart"></div>
      </template>
      <template v-slot:footer>
        <span>昨日订单量</span>
        <span class="emphasis">30,000,000</span>
      </template>
    </common-card>
  </div>
</template>

<script>
import commonCardMixin from '@/mixins/commonCardMixin'

export default {
  mixins: [commonCardMixin],
  mounted () {
    const chartDom = this.$refs.totalOredersChart
    const chart = this.$echarts.init(chartDom)
    /** @type EChartsOption */
    chart.setOption({
      xAxis: {
        type: 'category',
        show: false,
        boundaryGap: false
      },
      yAxis: {
        show: false
      },
      series: [
        {
          type: 'line',
          data: [620, 432, 220, 534, 790, 430, 289, 899],
          smooth: true,
          areaStyle: {
            color: 'purple'
          },
          lineStyle: {
            color: 'purple',
            width: 0
          },
          itemStyle: {
            opacity: 0
          }
        }
      ],
      grid: {
        top: 0,
        right: 0,
        bottom: 0,
        left: 0
      }
    })
  }
}
</script>

<style lang="scss" scoped>
.total-orders {
  #total-orders-chart {
    width: 100%;
    height: 100%;
  }
}
</style>
