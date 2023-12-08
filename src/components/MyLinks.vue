<template>
  <div class="my-links">
    <a class="my-links__item" target="_blank" href="https://github.com/holdenn1"
      ><img src="./../icons/Github.svg" alt="github"
    /></a>
    <img
      class="my-links__item"
      @click="openEmail"
      src="./../icons/Mega.svg"
      alt="gmail"
    />

    <a
      class="my-links__item"
      target="_blank"
      href="https://www.linkedin.com/in/ihor-ivliev-59ab381b4/"
      ><img src="./../icons/LinkedIn.svg" alt="linkedin"
    /></a>
    <a class="my-links__item" target="_blank" href="https://t.me/ihor_ivlievv"
      ><img src="./../icons/Telegram.svg" alt="telegram"
    /></a>
  </div>
</template>

<script setup lang="ts">
const openEmail = () => {
  const email = "ihor.ivlievv@gmail.com";
  window.location.href = `mailto:${email}`;
};
</script>

<style lang="scss" scoped>
.my-links {
  width: 100%;
  display: flex;
  justify-content: space-between;
  &__item {
  }
}
</style>
