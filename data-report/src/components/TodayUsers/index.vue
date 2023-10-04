<template>
  <div class="today-users">
    <common-card
      title="今日交易数"
      value="2,157,420"
    >
      <template>
        <div class="today-users-chart" ref="todayUsersChart"></div>
      </template>
      <template v-slot:footer>
        <span>退货率</span>
        <span class="emphasis">0.5%</span>
      </template>
    </common-card>
  </div>
</template>

<script>
import commonCardMixin from '@/mixins/commonCardMixin'

export default {
  mixins: [commonCardMixin],
  mounted () {
    const chartDom = this.$refs.todayUsersChart
    const chart = this.$echarts.init(chartDom)

    /** @type EChartsOption */
    chart.setOption({
      color: ['#3398DB'],
      tooltip: {
        show: true,
        trigger: 'item',
        axisPointer: {
          type: 'cross'
        }
      },
      series: [
        {
          type: 'bar',
          data: [410, 82, 200, 334, 390, 330, 220],
          barWidth: '60%'
        }
      ],
      xAxis: {
        type: 'category',
        show: false,
        data: ['00:00', '01:00', '02:00', '03:00', '04:00', '05:00', '06:00']
      },
      yAxis: {
        show: false
      },
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
  .today-users {
    .today-users-chart {
      width: 100%;
      height: 100%;
    }
  }
</style>
