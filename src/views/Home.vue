<template>
  <div id="container">
    <div id="main_content">
      <main>
        <div id="main_box">
          <span id="open">OPEN TODAY FOR GREAT FOOD</span>
          <span id="slogan">
            You Can Make Your Own
            <span class="yellow_chars">Burger</span>
          </span>
          <span id="text">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore
          </span>
          <div id="get_started_button"><span>GET STARTED</span></div>
          <div id="about_box">
            <span id="about_us" class="yellow_chars">About Us</span>
            <span id="about_text">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. mpor
              incididunt utmpor
            </span>
            <div id="rod"></div>
          </div>
        </div>
      </main>
      <div id="slider_container"></div>
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

export default defineComponent({
  name: "Home",
  components: {
    UpperLeft,
    DownerLeft,
    Right,
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

    main {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;

      #main_box {
        z-index: 3;
        width: 31vw;
        height: 31.76vh;
        margin-top: 18vh;
        display: flex;
        flex-direction: column;
        align-items: flex-start;

        span {
          margin: 0;
          padding: 0;
        }

        #open {
          font-size: 22px;
          font-family: "Open Sans", sans-serif;
          letter-spacing: 5px;
          color: #bbbbbb;
          text-align: start;
        }

        #slogan {
          margin-top: 3.4vh;
          width: 600px;
          font-family: "Modak", cursive;
          font-size: 70px;
          color: #0e0d2a;
          line-height: 90%;
          text-align: start;
        }

        #text {
          width: 435px;
          font-size: 14px;
          margin-top: 2vh;
          color: #bbbbbb;
          text-align: start;
        }

        #get_started_button {
          margin-top: 3vh;
          border: 2px solid #0e0d2a;
          color: #0e0d2a;
          border-radius: 999px;
          opacity: 0.4;
          padding: 17px 30px;
          cursor: pointer;
          transition: all 0.25s ease;

          &:hover {
            background-color: #101010;
            color: #fff;
          }

          span {
            font-size: 17px;
            letter-spacing: 1px;
          }
        }

        #about_box {
          margin-top: 18vh;
          display: flex;
          flex-direction: column;
          align-items: flex-start;
          position: relative;

          #about_us {
            font-size: 19px;
            font-weight: bold;
          }

          #about_text {
            margin-top: 2.2vh;
            width: 384px;
            color: #bbbbbb;
            font-size: 14px;
            text-align: start;
          }

          #rod {
            background-color: #0e0d2a;
            width: 200px;
            height: 7px;
            position: absolute;
            right: 416px;
            top: 8px;
          }
        }
      }
    }

    #slider_container {
      width: 100%;
    }
  }

  .shape {
    z-index: 1;
    -webkit-filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.12));
    filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.12));
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
