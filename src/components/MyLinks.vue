<template>
  <div class="my-links">
    <a class="my-links__item" target="_blank" href="https://github.com/holdenn1"
      ><img class="my-link-image" src="./../icons/Github.svg" alt="github"
    /></a>
    <div class="my-links__item">
      <img
        class="my-link-image"
        @click="openEmail"
        src="./../icons/Mega.svg"
        alt="gmail"
      />
    </div>

    <a
      class="my-links__item"
      target="_blank"
      href="https://www.linkedin.com/in/ihor-ivliev-59ab381b4/"
      ><img class="my-link-image" src="./../icons/LinkedIn.svg" alt="linkedin"
    /></a>
    <a class="my-links__item" target="_blank" href="https://t.me/ihor_ivlievv"
      ><img class="my-link-image" src="./../icons/Telegram.svg" alt="telegram"
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
    .my-link-image{
      transition: 0.3s;
      &:hover{
        transform: scale(1.15,1.15);
      }
    }
  }
}
</style>
