<template>
  <div class="tabbar-main">
    <div class="tabbar" v-for="(item, index) in tabbarData">
      <div
        class="tabbar-item"
        :class="{ active: currentIdex === index }"
        @click="changeCurrentIndex(index, item.path, item.text)"
      >
        <img
          v-if="currentIdex === index"
          class="icon"
          :src="getImg(item.imageActive)"
          :alt="item.text"
        />
        <img v-else class="icon" :src="getImg(item.image)" :alt="item.text" />
        <div class="text">
          {{ item.text }}
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
//导入vue核心
import { ref } from "vue";
//导入router
import { useRouter } from "vue-router";

import tabbarData from "@/assets/data/tabbar.js";

//使用路由
const router = useRouter();

let currentIdex = ref(0);
function changeCurrentIndex(index, path, text) {
  //改变当前Index
  currentIdex.value = index;
  //编程式导航
  router.push(path);
  //改变标题
  document.title = "泓睿房源-" + text;
}

//由于vite的特点无法使用require函数,只能自己拼接图片路径
function getImg(img) {
  return new URL(`../../assets/img/${img}`, import.meta.url);
}
</script>
<style lang="less" scoped>
.active {
  color: var(--primary-color);
}
.tabbar-main {
  position: fixed;
  bottom: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60px;
  width: 100%;
  border-top: 1px solid #ccc;
}
.tabbar {
  display: flex;
  flex: 1;
  flex-direction: column;
}
.tabbar .tabbar-item {
  text-align: center;
}
.tabbar .tabbar-item .icon {
  height: 24px;
}
</style>
