<template>
  <div>
    <tab-bar>
      <tab-bar-item path='/home' activeColor='blue'>
        <img src="@/assets/img/tabbar/home.png" alt="" slot="item-icon">
        <img src="@/assets/img/tabbar/home-active.png" alt="" slot="item-icon-active">
        <div slot="item-text">首页</div>
      </tab-bar-item>

      <tab-bar-item path='/category' activeColor='blue'>
        <img src="@/assets/img/tabbar/fenlei.png" alt="" slot="item-icon">
        <img src="@/assets/img/tabbar/fenlei-active.png" alt="" slot="item-icon-active">
        <div slot="item-text">分类</div>
      </tab-bar-item>

      <tab-bar-item path='/cart' activeColor='blue'>
        <img src="@/assets/img/tabbar/gwc.png" alt="" slot="item-icon">
        <img src="@/assets/img/tabbar/gwc-active.png" alt="" slot="item-icon-active">
        <div slot="item-text">购物车</div>
      </tab-bar-item>

      <tab-bar-item path='/me'>
        <img src="@/assets/img/tabbar/me.png" alt="" slot="item-icon">
        <img src="@/assets/img/tabbar/me-active.png" alt="" slot="item-icon-active">
        <div slot="item-text">我的</div>
      </tab-bar-item>
    </tab-bar>
  </div>
</template>

<script>
import TabBar from '@/components/common/tabbar/TabBar'
import TabBarItem from '../../common/tabbar/TabBarItem'
  export default {
    name:'MainTabBar',
    components:{
      TabBar,
      TabBarItem
    } 
  }
</script>

<style scoped>

</style>