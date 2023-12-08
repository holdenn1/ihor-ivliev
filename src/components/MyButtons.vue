<template>
  <div class="my-buttons">
    <button type="button" @click="openEmail" class="contact-me">
      <span>CONTACT ME</span>
    </button>
    <button class="download-cv">
      <span>DOWNLOAD CV</span>
      <img src="./../icons/download.svg" alt="download" />
    </button>
  </div>
</template>

<script setup lang="ts">
const openEmail = () => {
  const email = "ihor.ivlievv@gmail.com";
  window.location.href = `mailto:${email}`;
};
</script>

<style lang="scss" scoped>
.my-buttons {
  width: 100%;
  display: flex;
  justify-content: space-between;
  .contact-me {
    display: flex;
    width: 206px;
    height: 58px;
    padding: 18px 24px;
    justify-content: center;
    align-items: center;
    border-radius: 6px;
    background: #9d1837;
    span {
      color: var(--colors-theme-white, #fff);
      font-style: normal;
      font-weight: 600;
      line-height: 12px;
      letter-spacing: 0.5px;
      text-transform: uppercase;
    }
  }
  .download-cv {
    display: flex;
    width: 206px;
    height: 58px;
    padding: 18px 24px;
    justify-content: center;
    align-items: center;
    gap: 12px;
    border-radius: 6px;
    border: 3px solid #9d1837;
    span {
      color: var(--colors-theme-white, #fff);
      font-style: normal;
      font-weight: 600;
      line-height: 12px;
      letter-spacing: 0.5px;
      text-transform: uppercase;
    }
  }
}
</style>
