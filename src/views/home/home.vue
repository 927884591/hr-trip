<template>
  <home-nav></home-nav>
  <div class="banner">
    <img class="bannerImg" src="@/assets/img/home/banner.webp" alt="" />
  </div>
</template>
<script setup>
import homeNav from "./cpns/home-nav.vue";
</script>
<style lang="less" scoped>
.banner .bannerImg {
  width: 100%;
}
</style>
