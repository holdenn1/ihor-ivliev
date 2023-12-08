<template>
  <div class="container">
    <Header />
    <AboutMe/>
    <Skills/>
    <Education/>
    <Experience/>
    <ContactMe/>
  </div>
  <Footer/>
</template>

<script setup lang="ts">
import Header from "./components/Header.vue";
import AboutMe from "./components/AboutMe.vue";
import Skills from "./components/Skills.vue";
import Education from "./components/Education.vue";
import Experience from "./components/Experience.vue";
import ContactMe from "./components/ContactMe.vue";
import Footer from "./components/Footer.vue";
</script>

<style lang="scss" scoped>
.container {
  max-width: 1220px;
  margin: 0 auto;
  padding: 106px 10px 0;
  position: relative;

}
</style>
