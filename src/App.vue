<template>
  <router-view></router-view>
  <tab-bar></tab-bar>
</template>
<script setup>
import { RouterLink, RouterView } from "vue-router";
import TabBar from "./views/tab-bar/tab-bar.vue";
</script>
<style scoped></style>
