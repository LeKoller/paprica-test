<template>
  <div id="container">
    <div id="main_content">
      <LeftSide />
      <RightSide />
    </div>

    <div id="social_media">
      <span id="dont_miss">Don’t Miss Our Promo On</span>
      <div class="external_link" @click="() => {}">
        <img
          src="@/assets/facebook.png"
          alt="Facebook icon"
          class="social_media_icon"
        />
      </div>
      <div class="external_link" @click="() => {}">
        <img
          src="@/assets/instagram.png"
          alt="Instagram icon"
          class="social_media_icon"
        />
      </div>
      <div class="external_link" @click="() => {}">
        <img
          src="@/assets/twitter.png"
          alt="Twitter icon"
          class="social_media_icon"
        />
      </div>
    </div>

    <span id="food">FOOD</span>

    <UpperLeft class="shape upper_left" />
    <DownerLeft class="shape downer_left" />
    <Right class="shape right" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import UpperLeft from "../components/shapes/UpperLeft.vue";
import DownerLeft from "../components/shapes/DownerLeft.vue";
import Right from "../components/shapes/Right.vue";
import LeftSide from "../components/LeftSide.vue";
import RightSide from "../components/RightSide.vue";

export default defineComponent({
  name: "Home",
  components: {
    UpperLeft,
    DownerLeft,
    Right,
    LeftSide,
    RightSide,
  },
  setup() {},
});
</script>

<style lang="scss" scoped>
#container {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: calc(100% - 135px);

  #food {
    z-index: 0;
    font-family: "Archivo Black", sans-serif;
    font-size: 128px;
    position: absolute;
    top: 66.6vh;
    left: 28.75vw;
    color: transparent;
    -webkit-text-stroke: 2px #b9b9b9;
    opacity: 0.4;
  }

  #main_content {
    display: flex;
    justify-content: space-between;
    width: 100%;
  }

  #social_media {
    z-index: 6;
    position: absolute;
    bottom: 8vh;
    left: 64vw;
    display: flex;
    align-items: center;

    #dont_miss {
      font-size: 19px;
      opacity: 0.7019607843137254;
      margin-right: 50px;
    }

    .external_link {
      margin-right: 25px;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 52px;
      height: 52px;
      background-color: #fff;
      border-radius: 999px;
      box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.12);
      cursor: pointer;

      .social_media_icon {
        transition: all 0.25s ease;
      }

      &:hover {
        .social_media_icon {
          opacity: 0.4;
        }
      }
    }
  }

  .shape {
    z-index: 1;
    -webkit-filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.1));
    filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.1));
  }

  .upper_left {
    position: fixed;
    top: -680px;
    left: -190px;
  }

  .downer_left {
    position: fixed;
    bottom: -500px;
    left: -320px;
  }

  .right {
    position: fixed;
    top: -130px;
    left: 45.8%;
  }
}
</style>
