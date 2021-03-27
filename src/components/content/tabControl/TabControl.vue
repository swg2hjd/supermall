<template>
  <div class="tab-control">
    <div
      v-for="(item, index) in titles"
      :key="index"
      class="tab-control-item"
      :class="{ active: index === currentIndex }" 
    >
      <span @click="btnClick(index)">{{ item }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TabControl",
  props: {
    titles: {
      type: Array,
      default: []
    }
  },
  data() {
    return {
      currentIndex: 0
    };
  },
  methods: {
    btnClick(index) {
      this.currentIndex = index
    }
  }
}
</script>

<style scoped>
.tab-control {
  display: flex;
  height: 44px;
  line-height: 44px;
  background-color: #fff;
}

.tab-control-item {
  flex: 1;
  text-align: center;
}

.active {
  color: var(--color-high-text);
}

.active span {
  margin: 0 auto;
  text-align: center;
  display: block;
  width: 40px;
  height: 35px;
  /* line-height: 35px; */
  /* flex: 1; */
  border-bottom: 3px solid var(--color-high-text);
}
</style>
