<template>
  <div
    ref="skillsObserveElement"
    id="skills"
    class="skills"
    :class="{ 'animation-skills': isAnimation }"
  >
    <div class="skills__content">
      <TitleBlock style="margin-bottom: 80px" title="Skills">
        <img src="./../icons/Shield.svg" alt="" />
      </TitleBlock>
      <div class="skills-list">
        <div v-for="{ id, icon, skill } in skills" class="skill" :key="id">
          <img class="skill-image" :src="icon" alt="" />
          <h5 class="skill-title">{{ skill }}</h5>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import TitleBlock from "./TitleBlock.vue";
import sass from "./../icons/skills/sass.svg";
import react from "./../icons/skills/react.svg";
import redux from "./../icons/skills/redux.svg";
import vue from "./../icons/skills/Vue.svg";
import pinia from "./../icons/skills/Pinia.svg";
import ts from "./../icons/skills/typescript.svg";
import node from "./../icons/skills/nodejs.svg";
import nest from "./../icons/skills/NestJS.svg";
import postgres from "./../icons/skills/Postgresql.svg";
import firebase from "./../icons/skills/firebase.svg";
import { onBeforeUnmount, onMounted, ref } from "vue";

const skills = [
  { id: 1, skill: "Sass", icon: sass },
  { id: 2, skill: "React", icon: react },
  { id: 3, skill: "Redux", icon: redux },
  { id: 4, skill: "Vue", icon: vue },
  { id: 5, skill: "Pinia", icon: pinia },
  { id: 6, skill: "TypeScript", icon: ts },
  { id: 7, skill: "NodeJS", icon: node },
  { id: 8, skill: "NestJS", icon: nest },
  { id: 9, skill: "PostgreSQL", icon: postgres },
  { id: 10, skill: "Firebase", icon: firebase },
];

const observer = new IntersectionObserver(([entry]) => {
  if (entry.isIntersecting) {
    console.log(1);
    isAnimation.value = true;
    observer.disconnect();
  }
});

const skillsObserveElement = ref();

const isAnimation = ref(false);

onMounted(() => {
  observer.observe(skillsObserveElement.value);
});

onBeforeUnmount(() => observer.disconnect());
</script>

<style lang="scss" scoped>
.skills {
  margin: 0px 0 74px;
  padding-top: 110px;
  width: 100%;
  .skills__content {
    width: 100%;
    .skills-list {
      width: 100%;
      height: 552px;
      display: grid;
      grid-template-columns: repeat(5, 160px);
      grid-template-rows: repeat(2, 206px);
      justify-items: center;
      align-items: center;
      justify-content: space-between;
      align-content: space-between;
      padding-bottom: 20px;
      .skill {
        .skill-image {
          height: 150px;
          width: 160px;
        }
        .skill-title {
          margin-top: 24px;
          color: var(--colors-theme-white, #fff);
          text-align: center;
          font-feature-settings: "clig" off, "liga" off;
          font-size: 24px;
          line-height: 32px;
          letter-spacing: 1px;
        }
      }
    }
  }
}

.animation-skills {
  animation-name: skills;
  animation-duration: 1.2s;
  animation-delay: 0.5s;
  animation-timing-function: ease;
  opacity: 0;
  transform: translate(0, 250px);
  animation-fill-mode: forwards;

  @keyframes skills {
    100% {
      opacity: 1;
      transform: translate(0, 0px);
    }
  }
}
</style>
