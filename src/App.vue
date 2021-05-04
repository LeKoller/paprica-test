<template>
  <NavBar />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import NavBar from "./components/NavBar.vue";

export default defineComponent({
  name: "App",
  components: {
    NavBar,
  },
});
</script>

<style lang="scss">
#app {
  font-family: "Roboto", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

  button {
    background-color: transparent;
    outline: none;
    border: none;
    cursor: pointer;
  }

  .yellow_chars {
    color: #e39b00;
  }
}
</style>
