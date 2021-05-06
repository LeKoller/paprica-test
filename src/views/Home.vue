<template>
  <div id="container">
    <div id="main_content">
      <LeftSide />
      <div id="slider_container">
        <img src="@/assets/burger.png" alt="Hamburguer" id="burger_pic" />
        <div id="burger_case">
          <span id="bur">BUR</span>
          <span id="ger">GER</span>
          <span id="flavor">
            Spicy Beef <span class="yellow_chars">Burger</span>
          </span>
        </div>
        <div id="social_media">
          <span id="dont_miss">Don’t Miss Our Promo On</span>
        </div>
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

export default defineComponent({
  name: "Home",
  components: {
    UpperLeft,
    DownerLeft,
    Right,
    LeftSide,
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

    #slider_container {
      z-index: 2;
      width: 100%;
      position: relative;

      #burger_case {
        width: 532px;
        height: 666px;
        position: absolute;
        right: 12vw;
        top: 7.2vh;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: flex-start;

        #bur,
        #ger {
          z-index: 3;
          font-family: "Archivo Black", sans-serif;
          font-size: 230px;
          color: transparent;
          -webkit-text-stroke: 2px #b9b9b9;
          opacity: 0.4;
          margin: 0;
          padding: 0;
        }

        #flavor {
          z-index: 5;
          position: absolute;
          font-size: 49px;
          font-family: "Modak", cursive;
          left: 70px;
          bottom: 56px;
        }
      }

      #burger_pic {
        z-index: 4;
        top: 16.5vh;
        right: 7.74vw;
        -webkit-filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.1));
        filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.1));
        position: absolute;
      }
    }

    #social_media {
      position: absolute;
      top: calc(90vh - 135px);
      left: 264px;

      #dont_miss {
        font-size: 19px;
        opacity: 0.7019607843137254;
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
