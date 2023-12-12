<template>
  <div class="education-item">
    <h4 class="education-title">{{ title }}</h4>
    <p class="education-description">{{ description }}</p>
    <span class="education-years">{{ years }}</span>
  </div>
</template>

<script setup lang="ts">
defineProps<{ title: string; description: string; years: string }>();
</script>

<style lang="scss" scoped>
.education-item {
  max-width: 436px;
  height: 152px;
  margin-bottom: 40px;
  &:last-child {
    margin: 0;
  }
  .education-title {
    color: #a52140;
    font-size: 24px;
    font-weight: 600;
    line-height: 32px;
    text-transform: capitalize;
  }
  .education-description {
    color: var(--colors-theme-white, #fff);
    font-size: 18px;
    line-height: 24px;
    letter-spacing: 1px;
    margin: 20px 0;
    margin-left: 20px;
    position: relative;
    &::before {
      content: "";
      position: absolute;
      top: 9px;
      left: -20px;
      width: 5px;
      height: 5px;
      border-radius: 100%;
      background-color: #fff;
    }
  }
  .education-years {
    color: var(--colors-theme-white, #fff);
    font-size: 18px;
    line-height: 24px;
    letter-spacing: 1px;
    padding-left: 20px;
  }
}
</style>
