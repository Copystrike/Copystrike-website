<template>
  <nav class="navbar" role="navigation" aria-label="main navigation">
    <a @click="hamburger()" role="button" class="navbar-burger" aria-label="menu" aria-expanded="false"
       data-target="navMenu">
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
    </a>

    <div id="navbar-menu" class="navbar-menu" style="justify-content: center;">
      <div class="navbar-start is-marginless">
        <a class="navbar-item has-text-white nav-bar-button">
          Home
        </a>
        <a class="navbar-item has-text-white nav-bar-button">
          Weeb 🤪
        </a>

      </div>
    </div>
  </nav>
</template>

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";

@Component({
  name: 'navbar'
})
export default class navbar extends Vue {

  hamburger() {
    const navMenu = document.getElementsByClassName("navbar-menu")[0];
    const navBurger = document.getElementsByClassName("navbar-burger")[0];
    if (navBurger && navMenu) {
      navBurger.classList.toggle('is-active');
      navMenu.classList.toggle('is-active');
    }
  }
}
</script>

<style scoped>

.navbar {
  background: transparent;
}

.navbar-item {
  border-radius: 5px;
}

.navbar-item:hover {
  opacity: 0.5;
}

.nav-bar-button {
  border-style: solid;
  border-color: #fdfdfd10;
}

</style>
