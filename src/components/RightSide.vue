<template>
  <div id="slider_container">
    <img src="@/assets/burger.png" alt="Hamburguer" id="burger_pic" />
    <div id="burger_case">
      <span id="bur">BUR</span>
      <span id="ger">GER</span>
      <span id="flavor">
        Spicy Beef <span class="yellow_chars">Burger</span>
      </span>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "RightSide",
  setup() {},
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
  }
}
</style>
