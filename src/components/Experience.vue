<template>
  <div ref="experienceObserverElement" id="experience" class="experience" :class="{ 'animation-experience': isAnimation }">
    <div class="experience__content">
      <TitleBlock title="Experience">
        <img src="./../icons/Case.svg" alt="" />
      </TitleBlock>
    </div>
    <div class="experience-block">
      <div v-for="project in projects" :key="project.id" class="project-item">
        <img
          :style="project.isImgLeft ? { order: 1 } : { order: 3 }"
          class="project-img"
          :src="project.image"
          alt=""
        />
        <CustomVerticalLine style="order: 2" :is-experience-block="true" />
        <div
          :style="!project.isImgLeft ? { order: 1 } : { order: 3 }"
          class="project-description-block"
        >
          <h3 class="project-name">{{ project.name }}</h3>
          <h4 class="project-title">{{ project.title }}</h4>
          <h5 class="project-period">{{ project.period }}</h5>
          <p class="project-description">{{ project.description }}</p>
          <p class="project-technologies">{{ project.technologies }}</p>
          <div class="project-links">
            <div class="project-link">
              <a :href="project.linkClient" target="_blank">
                <img
                  class="project-link-img"
                  :src="project.githubIcon"
                  alt=""
                />
              </a>
              <h4 class="project-link-name">
                {{ project.id === 4 ? "Repository" : "Client" }}
              </h4>
            </div>
            <div v-if="project.hasServer" class="project-link">
              <a :href="project.linkServer" target="_blank">
                <img
                  class="project-link-img"
                  :src="project.githubIcon"
                  alt=""
                />
              </a>
              <h4 class="project-link-name">Server</h4>
            </div>
            <div class="project-link">
              <a :href="project.linkPreview" target="_blank">
                <img
                  class="project-link-img"
                  :src="project.previewIcon"
                  alt=""
                />
              </a>
              <h4 class="project-link-name">Preview</h4>
            </div>
          </div>
        </div>
      </div>
      <div class="work-item">
        <div class="work-description-block">
          <h3 class="work-name" style="margin-bottom: 12px">
            “Техносток” / Zaporizhzhia
          </h3>

          <h4 class="work-position-title">Retail Trade Manager</h4>
          <h5 class="work-period">Febr 2022 - Dec 2023</h5>
          <p class="work-position-description">
            Sales analysis, evaluation of equipment, distribution of equipment
            between stores, work in 1C.
          </p>

          <h4 class="work-position-title">Non-food seller</h4>
          <h5 class="work-period">2020 - Feb 2022</h5>
          <p class="work-position-description">
            Selling equipment, consulting customers, working with the cash
            register.
          </p>
        </div>
        <CustomVerticalLine :is-experience-block="true" />

        <img class="work-img" :src="seller" alt="" />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import CustomVerticalLine from "./CustomVerticalLine.vue";
import TitleBlock from "./TitleBlock.vue";
import wallet from "./../icons/images/wallet.png";
import orchestr8 from "./../icons/images/orchestr8.png";
import snacksprint from "./../icons/images/snacksprint.png";
import toastify from "./../icons/images/toastify.png";
import bookshelf from "./../icons/images/bookshelf.png";
import github from "./../icons/images/Github.svg";
import preview from "./../icons/images/Play.svg";
import seller from "./../icons/images/seller.png";
import { onBeforeUnmount, onMounted, ref } from "vue";

const projects = [
  {
    id: 1,
    name: "Wallet",
    title: "Financial Management App",
    period: "Aug 2023 - Nov 2023",
    description:
      "The app allows for managing financial operations(income, expenses, transactions) and encompasses numerous categories (groceries, rent, transportation,etc.), that facilitate keeping transaction histories comfortably. Through graphical representation, it offers a convenient way to track the percentage of expenses allocated to each category.",
    technologies:
      "Vue, Pinia, TypeScript, NestJS, PostgreSQL, TypeORM, Firebase, JSON Web Token (JWT), Passport.js, Sass.",
    image: wallet,
    isImgLeft: true,
    githubIcon: github,
    previewIcon: preview,
    hasServer: true,
    linkClient: "https://github.com/holdenn1/wallet-client",
    linkServer: "https://github.com/holdenn1/wallet-server",
    linkPreview: "https://holdenn1.github.io/wallet-client/#/",
  },
  {
    id: 2,
    name: "Orchestr8",
    title: "Project Management App",
    period: "Jul 2023 - Aug 2023",
    description:
      "The app provides the ability to create projects, add tasks and participants to them. It also implements a system of permissions with project owners, managers, and participants. Users can manage the status of projects (active, completed, and suspended), and project updates occur in real-time for all participants.",
    technologies:
      "React, Redux, TypeScript, NestJS, PostgreSQL, TypeORM, Firebase, JSON Web Token (JWT), Websocket, Passport.js , Sass.",
    image: orchestr8,
    isImgLeft: false,
    githubIcon: github,
    previewIcon: preview,
    hasServer: true,
    linkClient: "https://github.com/holdenn1/orchestr8-client",
    linkServer: "https://github.com/holdenn1/orchestr8-server",
    linkPreview: "https://holdenn1.github.io/orchestr8-client/",
  },
  {
    id: 3,
    name: "SnackSprint",
    title: "Food Ordering App",
    period: "Apr 2023 - Jul 2023",
    description:
      "The app features food ordering capabilities with a functional shopping cart. Additionally, there's an admin page allowing administrators to add new items and edit existing ones.",
    technologies: "Vue, Pinia, TypeScript, Firebase,  Sass.",
    image: snacksprint,
    isImgLeft: true,
    githubIcon: github,
    previewIcon: preview,
    hasServer: false,
    linkClient: "https://github.com/holdenn1/snackSprint",
    linkPreview: "https://holdenn1.github.io/snackSprint/#/",
  },
  {
    id: 4,
    name: "Vue-toastify",
    title: "NPM Plugin",
    period: "Apr 2023 - May 2023",
    description:
      "The plugin I've developed allows for quick and flexible configuration of notifications (toastify) in Vue applications.",
    technologies: "Vue, Pinia, TypeScript, Firebase,  Sass.",
    image: toastify,
    isImgLeft: false,
    githubIcon: github,
    previewIcon: preview,
    hasServer: false,
    linkClient: "https://github.com/holdenn1/vue-toastify",
    linkPreview:
      "https://www.npmjs.com/package/vue-toastify-3?activeTab=readme",
  },
  {
    id: 5,
    name: "BookShelf",
    title: "Personal Library",
    period: "Mar 2023 - Apr 2023",
    description:
      "The app is designed for adding and sharing thoughts about read books. Each user can add their read books to a personal library and, if desired, share reviews in a public space where others can read them and even message the author. The app also features real-time chat functionality using Firebase.",
    technologies: "React, Redux, TypeScript, Firebase, Sass.",
    image: bookshelf,
    isImgLeft: true,
    githubIcon: github,
    previewIcon: preview,
    hasServer: false,
    linkClient: "https://github.com/holdenn1/bookShelf",
    linkPreview: "https://holdenn1.github.io/bookShelf/#",
  },
];

const observer = new IntersectionObserver(([entry]) => {
  if (entry.isIntersecting) {
    isAnimation.value = true;
    observer.disconnect();
  }
});

const experienceObserverElement = ref();

const isAnimation = ref(false);

onMounted(() => {
  observer.observe(experienceObserverElement.value);
});

onBeforeUnmount(() => observer.disconnect());
</script>

<style lang="scss" scoped>
.experience {
  width: 100%;
  padding-top: 106px;
  opacity: 0;
  &__content {
    width: 100%;
  }
  .experience-block {
    width: 100%;
    .project-item,
    .work-item {
      display: flex;
      justify-content: space-between;
      margin-bottom: 80px;

      .project-img,
      .work-img {
        object-fit: cover;
        max-width: 474px;
        max-height: 432px;
        width: 100%;
      }

      .project-description-block,
      .work-description-block {
        max-width: 474px;
        width: 100%;

        .project-name,
        .work-name {
          color: #a52140;
          font-feature-settings: "clig" off, "liga" off;
          font-size: 32px;
          font-weight: 700;
          line-height: 40px;
          text-transform: uppercase;
        }
        .project-title,
        .work-position-title {
          color: #a52140;
          font-feature-settings: "clig" off, "liga" off;
          font-size: 24px;
          font-weight: 600;
          line-height: 32px;
          margin: 4px 0;
        }
        .project-period,
        .work-period {
          color: #a52140;
          font-feature-settings: "clig" off, "liga" off;
          font-size: 20px;
          font-weight: 600;
          line-height: 30px;
        }

        .project-description,
        .work-position-description {
          color: #fff;
          font-size: 16px;
          font-weight: 400;
          line-height: 24px;
          letter-spacing: 0.8px;
          margin: 20px 0;
        }

        .project-technologies {
          color: #a52140;
          font-size: 16px;
          font-weight: 500;
          line-height: 26px;
          letter-spacing: 0.8px;
          margin-bottom: 34px;
        }
        .project-links {
          width: 100%;
          display: flex;
        }
        .project-link {
          margin-right: 36px;
          display: flex;
          flex-direction: column;
          align-items: center;

          .project-link-img {
            margin-bottom: 10px;
          }
          .project-link-name {
            color: #a52140;
            text-align: center;
          }
        }
      }
    }
  }
}

.animation-experience {
  animation-name: experience;
  animation-duration: 1.2s;
  animation-delay: 0.5s;
  animation-timing-function: ease;
  opacity: 0;
  transform: translate(0, 250px);
  animation-fill-mode: forwards;

  @keyframes experience {
    100% {
      opacity: 1;
      transform: translate(0, 0px);
    }
  }
}
</style>
