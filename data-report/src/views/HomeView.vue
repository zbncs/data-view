<template>
  <div class="home">
    <top-view />
    <sales-view />
    <map-view />
    <bottom-view />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import TopView from '@/components/TopView'
import BottomView from '@/components/BottomView'
import SalesView from '@/components/SalesView'
import MapView from '@/components/MapView'

export default {
  name: 'HomeView',
  components: {
    TopView,
    BottomView,
    SalesView,
    MapView
  }
}
</script>
<style lang="scss" scoped>
  .home {
    width: 100%;
    height: 100%;
    padding: 20px;
    background: #eee;
    box-sizing: border-box;
  }
</style>
