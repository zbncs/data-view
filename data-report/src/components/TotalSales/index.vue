<template>
  <div class="total-sales">
    <common-card
      title="累计销售额"
      value="￥ 32,232,678"
    >
      <template>
        <div class="compare">
          <span>日同比</span>
          <span class="emphasis">7.33%</span>
          <div class="increase"></div>
        </div>
        <div class="compare">
          <span>月同比</span>
          <span class="emphasis">7.33%</span>
          <div class="decrease"></div>
        </div>
      </template>
      <template v-slot:footer>
        <span>昨日销售额</span>
        <span class="emphasis">$ 30,000,000</span>
      </template>
    </common-card>
  </div>
</template>

<script>
import commonCardMixin from '@/mixins/commonCardMixin'

export default {
  mixins: [commonCardMixin]
}
</script>

<style lang="scss" scoped>
.total-sales {
  display: flex;
  justify-content: center;
  flex-direction: column;
  .compare {
    display: flex;
    margin-top: 3px;
    font-size: 12px;
    align-items: center;
    color: #666;
    // .increase {
    //   width: 0;
    //   height: 0;
    //   border-width: 3px;
    //   border-style: solid;
    //   border-color: transparent;
    //   border-bottom-color: black;
    //   margin: 0 0 3px 5px;
    // }
    // .decrease {
    //   width: 0;
    //   height: 0;
    //   border-width: 3px;
    //   border-style: solid;
    //   border-color: transparent;
    //   border-top-color: black;
    //   margin: 3px 0 0 5px;
    // }
  }
}
</style>
