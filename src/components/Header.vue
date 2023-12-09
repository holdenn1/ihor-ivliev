<template>
  <header class="header">
    <div class="header-container">
      <img
        @click="scrollTop"
        class="header-logo"
        src="./../icons/LOGO.svg"
        alt=""
      />
      <nav class="header-nav">
        <ul class="header-nav-list">
          <li class="header-nav-list__item" @click="scrollTop()">About</li>
          <li class="header-nav-list__item" @click="scrollToElement('skills')">
            Skills
          </li>
          <li
            class="header-nav-list__item"
            @click="scrollToElement('education')"
          >
            Education
          </li>
          <li
            class="header-nav-list__item"
            @click="scrollToElement('experience')"
          >
            Experience
          </li>
          <li class="header-nav-list__item">
            <div
              class="header-language-wrapper"
              @mouseenter="showBlock"
              @mouseleave="hideBlock"
            >
              <svg
                class="header-language-icon"
                xmlns="http://www.w3.org/2000/svg"
                width="32"
                height="29"
                viewBox="0 0 32 29"
                fill="none"
              >
                <path
                  d="M20.4033 16.675C20.4867 15.9572 20.5492 15.2395 20.5492 14.5C20.5492 13.7605 20.4867 13.0427 20.4033 12.325H23.9259C24.0927 13.021 24.1969 13.7496 24.1969 14.5C24.1969 15.2504 24.0927 15.979 23.9259 16.675H20.4033ZM18.5586 22.7215C19.184 21.5144 19.6634 20.2094 19.9969 18.85H23.0713C22.0708 20.6444 20.4763 22.0364 18.5586 22.7215ZM18.2981 16.675H13.4207C13.3164 15.9572 13.2539 15.2395 13.2539 14.5C13.2539 13.7605 13.3164 13.0319 13.4207 12.325H18.2981C18.3919 13.0319 18.4648 13.7605 18.4648 14.5C18.4648 15.2395 18.3919 15.9572 18.2981 16.675ZM15.8594 23.1565C14.9944 21.8515 14.2961 20.4051 13.8688 18.85H17.85C17.4227 20.4051 16.7244 21.8515 15.8594 23.1565ZM11.6906 10.15H8.64744C9.63752 8.34475 11.2425 6.95275 13.1497 6.2785C12.5244 7.48563 12.0554 8.79063 11.6906 10.15ZM8.64744 18.85H11.6906C12.0554 20.2094 12.5244 21.5144 13.1497 22.7215C11.2425 22.0364 9.63752 20.6444 8.64744 18.85ZM7.79284 16.675C7.62609 15.979 7.52187 15.2504 7.52187 14.5C7.52187 13.7496 7.62609 13.021 7.79284 12.325H11.3154C11.2321 13.0427 11.1695 13.7605 11.1695 14.5C11.1695 15.2395 11.2321 15.9572 11.3154 16.675H7.79284ZM15.8594 5.83263C16.7244 7.13763 17.4227 8.59487 17.85 10.15H13.8688C14.2961 8.59487 14.9944 7.13763 15.8594 5.83263ZM23.0713 10.15H19.9969C19.6634 8.79063 19.184 7.48563 18.5586 6.2785C20.4763 6.96362 22.0708 8.34475 23.0713 10.15ZM15.8594 3.625C10.0961 3.625 5.4375 8.51875 5.4375 14.5C5.4375 17.3842 6.53552 20.1503 8.49 22.1898C9.45776 23.1996 10.6067 24.0007 11.8711 24.5472C13.1355 25.0937 14.4908 25.375 15.8594 25.375C18.6234 25.375 21.2743 24.2292 23.2288 22.1898C25.1832 20.1503 26.2812 17.3842 26.2812 14.5C26.2812 13.0719 26.0117 11.6577 25.4879 10.3383C24.9642 9.0189 24.1965 7.82005 23.2288 6.81021C22.261 5.80038 21.1121 4.99933 19.8477 4.45281C18.5832 3.90629 17.228 3.625 15.8594 3.625Z"
                  fill="white"
                />
              </svg>
              <div class="hidden-block" :class="{ show: blockVisible }">
                <span>EN</span>
                <!-- <span>UK</span> -->
              </div>
            </div>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script setup lang="ts">
import { ref } from "vue";

const blockVisible = ref<boolean>(false);

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

function showBlock() {
  blockVisible.value = true;
}
function hideBlock() {
  blockVisible.value = false;
}
</script>

<style lang="scss" scoped>
.header {
  width: 100%;
  height: 106px;
  padding: 0 10px;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;

  animation-name: header;
  animation-duration: 1s;
  animation-timing-function: ease;
  animation-delay: 0.5s;
  opacity: 0;
  animation-fill-mode: forwards;
  background-color: rebeccapurple;

  @keyframes header {
    100% {
      opacity: 1;
    }
  }
  .header-container {
    height: 100%;
    max-width: 1220px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .header-logo {
      margin-right: 60px;
      cursor: pointer;
    }
    .header-nav {
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
          transition: 0.3s;
          position: relative;
          &:hover {
            color: #dd1853;
          }

          .header-language-wrapper {
            &:hover {
              color: white;
            }
            .hidden-block {
              opacity: 0;
              transition: opacity 0.3s ease;
              position: absolute;
              top: 16px;
              left: 50%;
              transform: translate(-50%, 0%);
              pointer-events: none;
              padding-top: 20px;
            }
            .header-language-icon {
              position: relative;
              z-index: 1000;
              path {
                transition: 0.3s;
                &:hover {
                  fill: #dd1853;
                }
              }
            }

            .show {
              opacity: 1;
              transition: opacity 0.3s ease;
              position: absolute;
              top: 16px;
              left: 50%;
              transform: translate(-50%, 0%);
              pointer-events: all;
              span {
                margin-bottom: 16px;
                font-family: IBM Plex Sans;
                font-size: 20px;
                font-weight: 700;
                line-height: 24px;
                letter-spacing: 1px;
                &:hover {
                  color: #dd1853;
                }
              }
            }
          }
        }
      }
    }
  }
}
</style>
