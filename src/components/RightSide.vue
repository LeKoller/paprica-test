<template>
  <div id="slider_container">
    <div id="burger_pic">
      <div id="control_buttons">
        <button id="left_button" @click="slideLeft">
          <span id="left_arrow" class="material-icons">
            arrow_back_ios
          </span>
        </button>
        <button id="right_button" @click="slideRight">
          <span id="right_arrow" class="material-icons">
            arrow_forward_ios
          </span>
        </button>
      </div>
      <img
        src="@/assets/burger.png"
        alt="Burguer photo"
        v-if="state.slideIndex === 0"
        :class="{
          fade: state.slideFromLeft,
          fadeOpposite: !state.slideFromLeft,
        }"
      />
      <img
        src="@/assets/krusty_krab.png"
        alt="Burguer photo"
        v-if="state.slideIndex === 1"
        :class="{
          fade: state.slideFromLeft,
          fadeOpposite: !state.slideFromLeft,
        }"
      />
      <img
        src="@/assets/big_kahuna.png"
        alt="Burguer photo"
        v-if="state.slideIndex === 2"
        :class="{
          fade: state.slideFromLeft,
          fadeOpposite: !state.slideFromLeft,
        }"
      />
    </div>
    <div id="burger_case">
      <span id="bur">BUR</span>
      <span id="ger">GER</span>
      <span id="flavor">
        {{ slidesData[state.slideIndex] }}
        <span class="yellow_chars">Burger</span>
      </span>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, reactive } from "vue";

export default defineComponent({
  name: "RightSide",
  setup() {
    const state = reactive({
      slideIndex: 0,
      rollSlide: true,
      slideFromLeft: true,
    });

    const slidesData = ["Spicy Beef", "Krusty Krab", "Big Kahuna"];
    const maxSlidesNum = 3;

    function rollSlideOn() {
      if (state.slideIndex < maxSlidesNum - 1)
        state.slideIndex = state.slideIndex + 1;
      else state.slideIndex = 0;
    }

    function slideLeft() {
      state.rollSlide = false;
      state.slideFromLeft = false;
      if (state.slideIndex !== 0) state.slideIndex = state.slideIndex - 1;
      else state.slideIndex = maxSlidesNum - 1;
    }

    function slideRight() {
      state.rollSlide = false;
      state.slideFromLeft = true;
      rollSlideOn();
    }

    onMounted(() => {
      setInterval(() => {
        if (state.rollSlide) {
          rollSlideOn();
        }
      }, 4000);
    });

    return {
      state,
      slidesData,
      slideLeft,
      slideRight,
    };
  },
});
</script>

<style lang="scss" scoped>
#slider_container {
  z-index: 2;
  width: 100%;
  position: relative;

  #burger_case {
    width: 532px;
    height: 666px;
    position: absolute;
    right: 12vw;
    top: 5vh;
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
      color: #0e0d2a;
    }
  }

  #burger_pic {
    z-index: 4;
    top: 14vh;
    right: 7.74vw;
    -webkit-filter: drop-shadow(0px 6px 10px rgba(#000, 0.4));
    filter: drop-shadow(0px 6px 10px rgba(#000, 0.4));
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 695px;

    #control_buttons {
      z-index: 9;
      position: absolute;
      width: 640px;
      display: flex;
      justify-content: space-between;
      opacity: 0;
      transition: all 0.25s ease;

      button {
        padding: 8px;
        margin: 0;
        border-radius: 999px;
        display: flex;
        justify-content: center;
        align-items: center;

        span {
          font-size: 48px;
          color: #9b9aa6;
          transition: all 0.25s ease;
          position: relative;
        }

        #left_arrow {
          left: 6px;
        }

        #right_arrow {
          left: 2px;
        }

        &:hover {
          span {
            color: #e39b00;
          }
        }

        &:active {
          transform: scale(0.8, 0.8);
        }
      }
    }

    &:hover {
      #control_buttons {
        opacity: 1;
      }
    }

    img {
      background-size: cover;
      background-repeat: no-repeat;
      height: 391px;
    }
  }

  .fade {
    -webkit-animation-name: fade;
    -webkit-animation-duration: 1.5s;
    animation-name: fade;
    animation-duration: 1.5s;
    position: relative;
  }

  .fadeOpposite {
    -webkit-animation-name: fadeOpposite;
    -webkit-animation-duration: 1.5s;
    animation-name: fadeOpposite;
    animation-duration: 1.5s;
    position: relative;
  }

  @-webkit-keyframes fade {
    from {
      opacity: 0.4;
      left: -160px;
    }
    to {
      opacity: 1;
      left: 0;
    }
  }

  @keyframes fade {
    from {
      opacity: 0.4;
      left: -160px;
    }
    to {
      opacity: 1;
      left: 0;
    }
  }

  @-webkit-keyframes fadeOpposite {
    from {
      opacity: 0.4;
      right: -160px;
    }
    to {
      opacity: 1;
      right: 0;
    }
  }

  @keyframes fadeOpposite {
    from {
      opacity: 0.4;
      right: -160px;
    }
    to {
      opacity: 1;
      right: 0;
    }
  }
}
</style>
