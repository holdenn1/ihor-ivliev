<template>
  <div class="custom-vertical-line">
    <div
      class="ellipse"
      :class="{ 'experience-block': isExperienceBlock }"
    ></div>
    <div class="line"></div>
  </div>
</template>

<script setup lang="ts">
defineProps<{ isExperienceBlock?: boolean }>();
</script>

<style lang="scss" scoped>
.custom-vertical-line {
  position: relative;
  .ellipse {
    width: 21px;
    height: 21px;
    border-radius: 100%;
    border: 4px solid #a52140;
    position: absolute;
    left: 50%;
    top: -30px;
    transform: translate(-50%, -50%);

  }

  .experience-block{
    top: -40px;
  }

  .line {
    height: 100%;
    width: 3px;
    background-color: #a52140;
    transform: rotate(180deg);
  }
}
</style>
