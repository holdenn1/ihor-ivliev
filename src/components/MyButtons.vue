<template>
  <div class="my-buttons">
    <button type="button" @click="openEmail" class="contact-me">
      <span>CONTACT ME</span>
    </button>
    <button type="button" @click="downloadCV" class="download-cv">
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

const url = 'https://drive.google.com/uc?id=1ix8TFD-_RMbo0Bc2pCGBnClB3iwTSbqp&export=download'

const downloadCV = () => {
  const a = document.createElement('a')
  a.href = url
  a.download = 'CV_Ihor_Ivliev_Full-stack_developer'
  a.click()
  window.URL.revokeObjectURL(url)
}

</script>

<style lang="scss" scoped>
.my-buttons {
  width: 100%;
  display: flex;
  justify-content: space-between;
  .contact-me {
    display: flex;
    width: 200px;
    height: 58px;
    padding: 18px 24px;
    justify-content: center;
    align-items: center;
    border-radius: 6px;
    background: #9d1837;
    transition: 0.5s;
    &:hover {
      background: #dd1853;
    }
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
    width: 200px;
    height: 58px;
    padding: 18px 24px;
    justify-content: center;
    align-items: center;
    gap: 12px;
    border-radius: 6px;
    border: 3px solid #9d1837;
    transition: 0.5s;
    &:hover {
      border: 3px solid #f2064d;
    }
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
