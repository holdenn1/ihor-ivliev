<template>
  <div class="contact-me">
    <div class="button-wrapper">

      <MyButtons />
    </div>
  </div>
</template>

<script setup lang="ts">
import MyButtons from "./MyButtons.vue";
</script>

<style lang="scss" scoped>
.contact-me{
  display: flex;
  justify-content: center;
  margin: 160px auto 94px;
  .button-wrapper{
    width: 462px;
  }
}
</style>
