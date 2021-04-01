<template>
  <div id="home">

    <!-- 顶端导航条 -->
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    
    <!-- 轮播图 -->
    <!-- <home-swiper :banners="banners" class="home-swiper" />
     -->
    
    <!-- elementUi轮播图 -->
    <home-swiper-2 :banners="banners"></home-swiper-2>

    <!-- 商品推荐 -->
    <recommend-view :recommends="recommends" />

    <!-- 特别推荐 -->
    <feature-view />

    <!-- 分类导航条 -->
    <tab-control :titles="['流行', '新款', '精选']" class="tab-control" />
    <ul>
      <li>aa</li>
      <li>aa</li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li>aa</li>
      <li></li>
      <li>aa</li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li>aa</li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li>aaaa</li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li>a</li>
    </ul>
  </div>
</template>

<script>
import NavBar from "@/components/common/navbar/NavBar";
import { getHomeMultidata, getHomeGoods } from "@/network/home";
import HomeSwiper from "@/views/home/childComps/HomeSwiper";

import RecommendView from "@/views/home/childComps/RecommendView";
import FeatureView from "@/views/home/childComps/FeatureView";
import TabControl from "@/components/content/tabControl/TabControl.vue";
import HomeSwiper2 from './childComps/HomeSwiper2.vue';

export default {
  name: "Home",

  data() {
    return {
      banners: [],
      recommends: [],
      goods: {
        pop: { page: 0, list: [] },
        new: { page: 0, list: [] },
        sell: { page: 0, list: [] }
      }
    };
  },

  components: {
    NavBar,
    HomeSwiper,
    RecommendView,
    FeatureView,
    TabControl,
    HomeSwiper2,
 
  },

  created() {
    this.getHomeMultidata();

    this.getHomeGoods("pop");
    this.getHomeGoods("new");
    this.getHomeGoods("sell");
  },

  methods: {
    getHomeMultidata() {
      getHomeMultidata().then(res => {
        console.log(res);
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommend.list;
      });
    },

    getHomeGoods(type) {
      const page = this.goods[type].page + 1;
      getHomeGoods(type, page).then(res => {
        console.log(res);
      });
    }
  }
};
</script>

<style scoped>
.home-nav {
  background-color: var(--color-tint);
  color: white;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9;
}

.home-swiper {
  margin-top: 44px;
}

.tab-control {
  position: sticky;
  top: 44px;
}

</style>
