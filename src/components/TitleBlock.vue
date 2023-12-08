<template>
  <div class="title-wrapper">
    <div class="title-content">
      <slot />
      <h3 class="clock-title">{{ title }}</h3>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{ title: string }>();
</script>

<style scoped>
.title-wrapper {
  width: 100%;
  height: 56px;
  margin-bottom: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  .title-content {
    display: flex;
    align-items: center;
    .clock-title {
      margin-left: 20px;
      color: #fff;
      text-align: center;
      font-size: 40px;
      font-weight: 700;
      line-height: 56px;
      letter-spacing: 1px;
    }
  }
}
</style>
