<template>
  <nav class="navbar" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <a class="navbar-item" href="https://bulma.io">
        <img src="http://localhost:3000/logo.png" height="28">
      </a>

      <a role="button" 
         class="navbar-burger" 
         aria-label="menu" 
         aria-expanded="false" 
         data-target="navbarBasicExample"
         @click="showMenu"
      >
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div id="navbarBasicExample" :class="{'navbar-menu': !mobileMenu}">
      <div class="navbar-start">
        <NuxtLink to="/home" class="navbar-item">
          Strona domowa
        </NuxtLink>

        <NuxtLink to="/about" class="navbar-item">
          O nas
        </NuxtLink>

        <a href="/about" class="navbar-item">
          O nas (nie spa)
        </a>

        <div class="navbar-item has-dropdown is-hoverable">
          <a class="navbar-link">
            More
          </a>

          <div class="navbar-dropdown">
            <a class="navbar-item">
              About
            </a>
            <a class="navbar-item">
              Jobs
            </a>
            <a class="navbar-item">
              Contact
            </a>
            <hr class="navbar-divider">
            <a class="navbar-item">
              Report an issue
            </a>
          </div>
        </div>
      </div>

      <div class="navbar-end">
        <div class="navbar-item">
          <div class="buttons">
            <NuxtLink to="/Cart"><img class="account" src="http://localhost:3000/koszyk.png"></NuxtLink>
            <img class="account" src="http://localhost:3000/uzytkownik.png">
            <img class="notifications" src="http://localhost:3000/dzwonek_ikona.png">
            <a class="button is-primary">
              <strong>Sign up</strong>
            </a>
            <a class="button is-light">
              Log in
            </a>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const mobileMenu = ref(false)

    const showMenu = () => {
      mobileMenu.value = !mobileMenu.value
      console.log(mobileMenu.value)
    }

    return { mobileMenu, showMenu }
  }
}
</script>

<style scoped>
.notifications {
  margin-right: 20px;
}
.account {
  margin-right: 20px;
}
</style>
