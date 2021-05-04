<template>
  <div id="container">
    <UpperLeft id="upper_left" class="shape" />
    <DownerLeft id="downer_left" class="shape" />
    <Right id="right" class="shape" />
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
  /* justify-content: center; */
  width: 100%;
  height: calc(100% - 135px);

  .shape {
    -webkit-filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.12));
    filter: drop-shadow(0px 0px 16px rgba(0, 0, 0, 0.12));
  }

  #upper_left {
    z-index: 1;
    position: fixed;
    top: -660px;
    left: -190px;
  }

  #downer_left {
    z-index: 1;
    position: fixed;
    bottom: -540px;
    left: -380px;
  }

  #right {
    z-index: 1;
    position: fixed;
    top: -130px;
    right: -270px;
  }
}
</style>
