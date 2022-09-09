<template>
  <div class="nav">
    <slot name="left">
      <div class="nav-item"></div>
    </slot>

    <div class="nav-item middle">泓睿房源</div>
    <slot class="nav-item" name="right">
      <div class="nav-item"></div>
    </slot>
  </div>
</template>
<script setup></script>
<style lang="less" scoped>
.nav {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  height: 40px;
  font-size: 16px;
  font-weight: 700px;
}
.nav .nav-item {
  flex: 1;
}
.middle {
  color: var(--primary-color);
}
</style>
