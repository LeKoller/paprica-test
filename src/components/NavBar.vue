<template>
  <div id="nav">
    <div id="logo">
      <img src="@/assets/logo.png" alt="Logo" />
      <span class="logo_name">BURGER<span class="yellow_chars">IAZ</span></span>
    </div>

    <div id="nav">
      <router-link to="/"
        ><div><span class="bar_menu">Home</span></div></router-link
      >
      <router-link to="/new_menu"
        ><div><span class="bar_menu">New Menu</span></div></router-link
      >
      <router-link to="/about"
        ><div><span class="bar_menu">About Us</span></div></router-link
      >
      <router-link to="/main_course"
        ><div><span class="bar_menu">Main Course</span></div></router-link
      >
    </div>

    <form id="search_bar" @submit.prevent="() => {}">
      <input
        type="text"
        name="search"
        id="search_input"
        placeholder="Search"
        @keydown.enter.prevent="() => {}"
      />
      <button id="search_button">
        <span class="material-icons" id="search_icon">
          search
        </span>
      </button>
    </form>

    <div id="menu_button_case">
      <button
        id="menu_button"
        @click="() => (state.showMenu = !state.showMenu)"
      >
        <img src="@/assets/burger_button.png" alt="Button icon" />
      </button>
      <ul id="menu" v-if="state.showMenu">
        <li
          class="first_level"
          @mouseenter="arrowDown('login')"
          @mouseleave="arrowRight('login')"
        >
          <a href="#">Login</a>
          <span class="material-icons arrow">
            {{ state.arrow["login"] }}
          </span>
          <ul class="sub_menu">
            <li><a href="#">Customer</a></li>
            <li><a href="#">Collaborator</a></li>
          </ul>
        </li>
        <li
          class="first_level"
          @mouseenter="arrowDown('signUp')"
          @mouseleave="arrowRight('signUp')"
        >
          <a href="#">Sign Up</a>
          <span class="material-icons arrow">
            {{ state.arrow["signUp"] }}
          </span>

          <ul class="sub_menu">
            <li><a href="#">Customer</a></li>
            <li><a href="#">Collaborator</a></li>
          </ul>
        </li>
        <li class="first_level"><a href="#">Partners</a></li>
        <li class="first_level"><a href="#">News</a></li>
      </ul>
    </div>
  </div>
  <router-view />
</template>

<script lang="ts">
import { defineComponent, reactive } from "vue";

export default defineComponent({
  name: "NavBar",
  setup() {
    const state = reactive({
      showMenu: false,
      arrow: {
        login: "chevron_right",
        signUp: "chevron_right",
      },
    });

    function arrowDown(segment) {
      state.arrow[segment] = "expand_more";
    }

    function arrowRight(segment) {
      state.arrow[segment] = "chevron_right";
    }

    return {
      state,
      arrowDown,
      arrowRight,
    };
  },
});
</script>

<style lang="scss" scoped>
#nav {
  z-index: 10;
  width: 83%;
  height: 59px;
  margin: 38px auto;
  position: relative;
  display: flex;
  justify-content: flex-end;
  align-items: center;

  #menu_button_case {
    position: relative;

    #menu_button {
      margin-left: 2.53vw;
      padding: 8px;
      border-radius: 6px;

      &:hover {
        background-color: #f0f0f0;
      }
    }

    #menu {
      position: absolute;
      list-style-type: none;
      list-style: none;
      right: 0;

      .first_level {
        transition: all 0.25s ease;
      }

      li {
        text-align: start;
        color: #fff;
        background-color: #e39b00;
        font-family: "Roboto", sans-serif;
        font-size: 18px;
        padding: 8px;
        border-bottom: 1px solid rgba($color: #fff, $alpha: 0.4);
        width: 160px;
        position: relative;
        transition: all 0.25s ease;

        .arrow {
          position: absolute;
          right: 8px;
          cursor: default;
        }

        .sub_menu {
          z-index: 11;
          position: absolute;
          visibility: hidden;
          list-style: none;
          padding: 0;
          margin: 0;

          li {
            margin: 0;
            right: 8px;
            top: 8px;
            background-color: #ffba2a;

            &:hover {
              background-color: #ffca58;
            }
          }
        }

        &:hover {
          background-color: #ffba2a;

          .sub_menu {
            z-index: 11;
            visibility: visible;
            position: relative;
          }
        }
      }
    }
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
    transition: all 0.25s ease;

    &:hover {
      background-color: #f0f0f0;
    }

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
        color: #bbb;
        transition: all 0.25s ease;

        &:hover {
          color: #fff;
        }
      }
    }
  }

  #nav {
    margin-left: 16.36vw;
    display: flex;

    a {
      text-decoration: none;
      outline: none;

      div {
        padding: 6px 1.55vw;
        /* opacity: 0.38; */
        font-weight: 100;
        font-size: 18px;
        transition: all 0.25s ease;

        span {
          color: #9c9b9b;
        }

        &:hover {
          background-color: #9c9b9b;

          span {
            color: #fff;
          }
        }
      }
    }

    a.router-link-exact-active {
      .bar_menu {
        color: #101010;
        font-weight: bold;
      }

      &:hover {
        span {
          color: #fff;
        }
      }
    }
  }
}
</style>
