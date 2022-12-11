<template>
  <header>
    <!-- <Navbar /> -->
  </header>
  <main>
    <transition name="zoom" mode="default">
      <router-view />
    </transition>
  </main>
   <!-- <footer>
    <p>Made by garrett-adamss
      <a class="" href="https://github.com/garrett-adamss/graveyard" alt="GitHub source link">
        &lt;source code/&gt;
      </a>
    </p>
  </footer> -->
</template>

<script>
import { computed } from 'vue'
import { AppState } from './AppState'
import Navbar from './components/Navbar.vue'

export default {
  setup() {
    return {
      appState: computed(() => AppState)
    }
  },
  components: { Navbar }
}
</script>
<style lang="scss">
@import "./assets/scss/main.scss";

:root{
  --main-height: calc(100vh - 32px - 64px);
}

//Fade transition
// .fade-enter-active, .fade-leave-active {
//     transition: opacity 0.5s ease-out;
//   }
// .fade-enter-from, .fade-leave-to {
//     opacity: 0;
//   }

//Zoom 
.zoom-enter-active, .zoom-leave-active {
  transition: all .25s;
  opacity: 0;
}
.zoom-enter, .zoom-leave-to {
  transform: scale(1);
}

// FOOTER

footer {
  display: grid;
  place-content: center;
  height: 32px;
}

footer p{
  font-size: 18px;
}

footer a{
  text-decoration: none;
  color: black;
  transition: transform 250ms;
}

footer a:hover{
  background-color: rgb(90, 90, 90);
  color: whitesmoke;
  transform: translateY(-10px);
  cursor: pointer;
}

</style>
