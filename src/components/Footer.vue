<template>
  <footer class="footer">
    <div class="footer__container">
      <div class="my-location">
        <h4 class="my-location-text">
          <img
            style="margin-right: 20px"
            src="./../icons/Location.svg"
            alt=""
          />Ivano-Frankivsk
        </h4>
      </div>

      <div class="links-container">

       <my-links/>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import MyLinks from './MyLinks.vue';
</script>

<style lang="scss" scoped>
.footer {
  opacity: 0.5;
  background: #333636;
  height: 98px;
  &__container {
    height: 100%;
    max-width: 1220px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .my-location {
      .my-location-text {
        color: #a52140;
        font-feature-settings: "clig" off, "liga" off;
        font-size: 32px;
        font-weight: 600;
        line-height: 40px;
        text-transform: capitalize;
        margin-left: 20px;
      }
    }
    .links-container{
      max-width: 432px;
      width: 100%;
    }
  }
}
</style>
