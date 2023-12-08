<template>
  <div id="education" class="education">
    <div class="education__content">
      <TitleBlock title="Education">
        <img src="./../icons/Edit.svg" alt="" />
      </TitleBlock>
      <div class="education-block">
        <div class="main-education">
          <EducationItem
            v-for="{ id, title, description, years } in mainEducationA"
            :key="id"
            :title="title"
            :description="description"
            :years="years"
          />
        </div>
        <CustomVerticalLine />
        <div class="additional-education">
          <EducationItem
            v-for="{ id, title, description, years } in additionalEducationA"
            :key="id"
            :title="title"
            :description="description"
            :years="years"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import CustomVerticalLine from "./CustomVerticalLine.vue";
import EducationItem from "./EducationItem.vue";
import TitleBlock from "./TitleBlock.vue";

const mainEducationA = [
  {
    id: 1,
    title: "“Zaporizhzhia Polytechnic” National university",
    description: "Bachelor's diploma ",
    years: "2018-2021 y.",
  },
  {
    id: 2,
    title: "“Zaporizhzhia Polytechnic” National university",
    description: "Master's diploma",
    years: "2021-2023 y.",
  },
  {
    id: 3,
    title: "Zaporizhzhia Electrotechnical College of “ZNTU”",
    description: "Junior specialist's diploma",
    years: "2014-2018 y.",
  },
];

const additionalEducationA = [
  {
    id: 1,
    title: "American English Center Course",
    description: "English courses with native speakers ",
    years: "2023 - Present",
  },
  {
    id: 2,
    title: "Full-stack web development course",
    description: "Self-guided learning under the mentorship of a web developer",
    years: "2022 - Present",
  },
  {
    id: 3,
    title: "Full stack web development course”",
    description: "Course from “Freshcode” IT company ",
    years: "2019-2020 y.",
  },
];
</script>

<style lang="scss" scoped>
.education {
  margin: 0px 0 74px;
  padding-top: 106px;
  width: 100%;
  &__content {
    width: 100%;
    .education-block {
      display: flex;
      justify-content: space-between;
      .main-education {
      }

      .additional-education {
      }
    }
  }
}
</style>
