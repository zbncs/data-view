<template>
  <div class="total-users">
    <common-card
      title="累计用户数"
      value="1,232,434"
    >
      <template>
        <div class="total-users-chart" ref="totalUsersChart"></div>
      </template>
      <template v-slot:footer>
        <div class="total-users-footer">
          <span>日同比</span>
          <span class="emphasis">0.5%</span>
          <div class="increase"></div>
          <span class="month">月同比</span>
          <span class="emphasis">0.5%</span>
          <div class="decrease"></div>
        </div>
      </template>
    </common-card>
  </div>
</template>

<script>
import commonCardMixin from '@/mixins/commonCardMixin'

export default {
  mixins: [commonCardMixin],
  mounted () {
    const chartDom = this.$refs.totalUsersChart
    const chart = this.$echarts.init(chartDom)

    /** @type EChartsOption */
    chart.setOption({
      color: ['green'],
      grid: {
        top: 0,
        right: 0,
        bottom: 0,
        left: 0
      },
      xAxis: {
        type: 'value',
        show: false
      },
      yAxis: {
        type: 'category',
        show: false
      },
      series: [
        {
          type: 'bar',
          data: [200],
          barWidth: 10,
          stack: '总量'
        },
        // {
        //   type: 'bar',
        //   data: [200],
        //   stack: '总量'
        // },
        {
          type: 'custom',
          data: [200],
          stack: '总量',
          renderItem: (params, api) => {
            const value = api.value(0)
            const endPiont = api.coord([value, 0])

            return {
              type: 'group',
              position: endPiont,
              children: [
                {
                  type: 'path',
                  shape: {
                    d: 'M1024 255.996 511.971 767.909 0 255.996 1024 255.996z',
                    x: -5,
                    y: -20,
                    width: 10,
                    height: 10,
                    layout: 'cover'
                  },
                  style: {
                    fill: '#45c946'
                  }
                },
                {
                  type: 'path',
                  shape: {
                    d: 'M0 767.909l512.029-511.913L1024 767.909 0 767.909z',
                    x: -5,
                    y: 10,
                    width: 10,
                    height: 10,
                    layout: 'cover'
                  },
                  style: {
                    fill: '#45c946'
                  }
                }
              ]
            }
          }
        }
      ]
    })
  }
}
</script>

<style lang="scss" scoped>
  .total-users {
    .total-users-footer {
      display: flex;
      margin-top: 3px;
      font-size: 12px;
      align-items: center;
      color: #666;
      .month {
        margin-left: 10px;
      }
    }
    .total-users-chart {
      width: 100%;
      height: 100%;
    }
  }
</style>
