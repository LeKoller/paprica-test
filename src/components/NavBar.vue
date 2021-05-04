<template>
  <div id="nav">
    <div id="logo">
      <img src="@/assets/logo.png" alt="Logo" />
      <span class="logo_name">BURGER<span class="yellow_chars">IAZ</span></span>
    </div>

    <div id="link_case">
      <router-link to="/"> <span>Home</span> </router-link>
      <router-link to="/#"> <span>New Menu</span> </router-link>
      <router-link to="/#"> <span>About Us</span> </router-link>
      <router-link to="/#"> <span>Main Course</span> </router-link>
    </div>

    <div id="search_bar">
      <input type="text" name="search" id="search_input" placeholder="Search" />
      <button id="search_button">
        <span class="material-icons" id="search_icon">
          search
        </span>
      </button>
    </div>

    <button id="buger_button">
      <img src="@/assets/burger_button.png" alt="Button icon" />
    </button>
  </div>
  <router-view />
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "NavBar",
  setup() {},
});
</script>

<style lang="scss" scoped>
#nav {
  z-index: 2;
  width: 83%;
  height: 59px;
  margin: 38px auto;
  position: relative;
  display: flex;
  justify-content: flex-end;
  align-items: center;

  #buger_button {
    margin-left: 2.53vw;
  }

  #logo {
    position: absolute;
    left: -5px;
    top: 13px;
    display: flex;
    align-items: center;

    .logo_name {
      font-family: "Roboto", sans-serif;
      font-weight: 800;
      font-size: 18px;
      color: #101010;
      margin-left: 6px;
    }
  }

  #search_bar {
    background-color: #f8f8f8;
    color: #707070;
    width: 19.6vw;
    height: 57px;
    border-radius: 999px;
    margin-left: 1.55vw;
    padding: 0 12px;

    display: flex;
    justify-content: space-between;
    align-items: center;

    #search_input {
      background-color: transparent;
      outline: none;
      border: none;
      font-size: 18px;
      padding: 0 12px;
      opacity: 70%;
      width: 80%;
    }

    #search_button {
      width: 38px;
      height: 38px;
      padding: 0;
      margin: 0;

      #search_icon {
        font-size: 38px;
        color: #bfbfbf;
      }
    }
  }

  #link_case {
    margin-left: 16.36vw;
    display: flex;

    a {
      text-decoration: none;

      span {
        padding: 6px 1.55vw;
        color: #000;
        opacity: 38%;
        font-weight: 100;
        font-size: 18px;
        transition: all 0.25s ease;

        &:hover {
          background-color: #101010;
          color: #fff;
        }
      }
    }

    a.router-link-exact-active {
      color: #101010;
      opacity: 100%;
    }
  }
}
</style>
