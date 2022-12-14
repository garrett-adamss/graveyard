<template>
  <nav class="navbar navbar-expand-lg px-3">
    <router-link class="navbar-brand d-flex" :to="{ name: 'Shop' }">
      <div class="d-flex flex-column align-items-center">
        <img alt="logo" src="http://www.thelimitrecords.com/store/graphics/logos/Graveyard-logo.png" height="45" />
      </div>
    </router-link>
    <button
      class="navbar-toggler"
      type="button"
      data-bs-toggle="collapse"
      data-bs-target="#navbarText"
      aria-controls="navbarText"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarText">
      <ul class="navbar-nav me-auto">
        <li>
          <router-link :to="{ name: 'Contact' }" class="btn text-light lighten-30 selectable text-uppercase">
            Contact
          </router-link>
          <router-link :to="{ name: 'Reviews' }" class="btn text-light lighten-30 selectable text-uppercase">
            Reviews
          </router-link>
        </li>
      </ul>
      <!-- LOGIN COMPONENT HERE -->
      <!-- <Login /> -->
      <i class="mdi mdi-cart text-light shopping-cart"></i>
    </div>
  </nav>
</template>

<script>
import Login from './Login.vue'
export default {
  setup() {
    return {}
  },
  components: { Login }
}
</script>

<style scoped>
.navbar{
  background-color: gray;
}
a:hover {
  text-decoration: none;
}

.nav-link {
  text-transform: uppercase;
}

.navbar-nav .router-link-exact-active {
  border-bottom: 2px solid whitesmoke;
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
}
.shopping-cart{
  font-size: 25px;
}
@media screen and (min-width: 768px) {
  nav {
    height: 64px;
  }
}

</style>
