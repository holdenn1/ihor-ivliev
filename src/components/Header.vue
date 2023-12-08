<template>
  <header class="header">
    <img class="header__logo" src="./../icons/LOGO.svg" alt="" />
    <nav class="header__nav">
      <ul class="header-nav-list">
        <li class="header-nav-list__item" @click="scrollTop()">About</li>
        <li class="header-nav-list__item" @click="scrollToElement('skills')">
          Skills
        </li>
        <li class="header-nav-list__item" @click="scrollToElement('education')">
          Education
        </li>
        <li
          class="header-nav-list__item"
          @click="scrollToElement('experience')"
        >
          Experience
        </li>
        <li class="header-nav-list__item">
          <img src="./../icons/language.svg" alt="" />
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup lang="ts">
function scrollToElement(elementId: string) {
  const element = document.getElementById(elementId);
  if (element) element.scrollIntoView({ behavior: "smooth", block: "start" });
}

function scrollTop() {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  });
}
</script>

<style lang="scss" scoped>
.header {
  width: 100%;
  height: 106px;
  padding: 0 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;

  &__logo {
    margin-right: 60px;
  }
  &__nav {
    max-width: 606px;
    width: 100%;
    .header-nav-list {
      display: flex;
      justify-content: space-between;
      align-items: center;
      &__item {
        color: var(--colors-theme-white, #fff);
        font-size: 20px;
        font-weight: 700;
        line-height: 24px;
        letter-spacing: 1px;
        cursor: pointer;
        padding: 0 4px;
      }
    }
  }
}
</style>
