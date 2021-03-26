<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :banners="banners" class="home-swiper" />
    <recommend-view :recommends="recommends" />
    <feature-view />
  </div>
</template>

<script>
import NavBar from "@/components/common/navbar/NavBar";
import { getHomeMultidata } from "@/network/home";
import HomeSwiper from "@/views/home/childComps/HomeSwiper";
import RecommendView from "@/views/home/childComps/RecommendView";
import FeatureView from "@/views/home/childComps/FeatureView";

export default {
  name: "Home",
  data() {
    return {
      banners: [],
      recommends: []
    };
  },
  components: {
    NavBar,
    HomeSwiper,
    RecommendView,
    FeatureView
  },

  created() {
    getHomeMultidata().then(res => {
      console.log(res);
      this.banners = res.data.banner.list;
      this.recommends = res.data.recommend.list;
    });
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
</style>
