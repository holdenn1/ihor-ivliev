<template>
  <div id="about-me" class="about-me">
    <div class="about-me__content">
      <div class="about-text-block">
        <h2 class="my-name">Ihor Ivliev</h2>
        <div class="my-position">
          <div class="position-line-wrapper">
            <div class="position-ellipse"></div>
            <div class="position-line"></div>
          </div>
          <p class="my-position-text">Full-stack JS | TS developer</p>
        </div>
        <div class="my-description">
          <p style="margin-bottom: 20px">
            Hello! I'm a Full-stack JS | TS developer with over a year of
            experience in web development. My goal is to create web applications
            that make users' lives more convenient and efficient.
          </p>
          <p style="margin-bottom: 20px">
            One of my strongest skills is self-learning. I independently learned
            React and Vue, and within three months, I mastered the server-side
            by studying NestJS and PostgreSQL, successfully completing my first
            project using these technologies. I'm adept at making independent
            decisions during project development and selecting the best methods
            for optimization because I understand the importance of
            well-optimized and scalable projects.
          </p>
          <p>
            I'm always ready for new challenges and eager to master new
            technologies. If you have any questions or proposals, I'm open to
            discussion.
          </p>
        </div>
      </div>
      <div class="about-link-block">
        <div class="links-content">
          <MyLinks style="margin-bottom: 48px" />
          <MyButtons />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import MyButtons from "./MyButtons.vue";
import MyLinks from "./MyLinks.vue";
</script>

<style lang="scss" scoped>
.about-me {
  width: 100%;
  height: 758px;
  overflow: hidden;
  &__content {
    margin: 124px 0px 116px;
    display: flex;
    justify-content: space-between;
    .about-text-block {
      max-width: 550px;
      width: 100%;
      height: 100%;
      margin-right: 20px;
      .my-name {
        color: #fff;
        font-feature-settings: "clig" off, "liga" off;
        font-size: 48px;
        font-weight: 800;
        line-height: 56px;
        letter-spacing: 3px;
        text-transform: uppercase;
      }

      .my-position {
        display: flex;
        align-items: center;
        .position-line-wrapper {
          position: relative;
          transform: rotate(270deg);
          .position-ellipse {
            width: 16px;
            height: 16px;
            border-radius: 100%;
            border: 4px solid #a52140;
            position: absolute;
            left:   50%;
            top: 60px;
            transform: translate(-50%, -50%);
          }
          .position-line {
            width:  72px;
            height:  3px;
            background-color: #a52140;
            transform: rotate(90deg);
          }
        }
        .my-position-text {
          color: #9d1837;
          margin: 30px 0;
          font-family: Karantina;
          font-size: 28px;
          font-style: normal;
          font-weight: 700;
          line-height: 24px;
          letter-spacing: 1.5px;
          padding-left: 100px;
        }
      }
      .my-description {
        color: var(--colors-theme-white, #fff);
        font-family: IBM Plex Sans Condensed;
        font-size: 18px;
        font-style: normal;
        font-weight: 400;
        line-height: 26px;
        letter-spacing: 0.8px;
      }
    }

    .about-link-block {
      max-width: 432px;
      width: 100%;
      display: flex;
      align-items: center;
      .links-content {
        width: 100%;
      }
    }
  }
}
</style>
