<template>
  <div class="root">
    <img class="background" ref="background" src="https://images.unsplash.com/photo-1640437118448-95fabc032a68?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"/>
    <img class="foreground img-1" ref="foreground1" src="https://static.vecteezy.com/system/resources/previews/013/392/025/original/tombstones-for-halloween-objects-graveyard-hand-drawn-silhouettes-png.png" />
    <img class="foreground img-2" ref="foreground2" src="https://static.vecteezy.com/system/resources/previews/013/392/025/original/tombstones-for-halloween-objects-graveyard-hand-drawn-silhouettes-png.png" />
    <div class="section section-1" ref="first">
      <div>
        <img class="main-text" src="http://www.thelimitrecords.com/store/graphics/logos/Graveyard-logo.png"/>
      </div>
    </div>
    <div class="section section-2" ref="second">
      <div class="section-2-text-box">
        <p>Continue to Store</p>
      </div>
    </div>

  </div>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue'
export default {
  setup() {
    onMounted(() => {
      document.addEventListener('scroll', handleScroll)
    })

    onUnmounted(() => {
      document.addEventListener('scroll', handleScroll)
    })

    const handleScroll = (evt) => {
      const scrollY = window.scrollY

      first.value.style.opacity = (100 - (scrollY + window.innerHeight - first.value.offsetHeight)) / 100

      second.value.style.opacity = (scrollY + window.innerHeight - second.value.offsetTop) / 100

      const maxBackgroundSize = 120;
      const backgroundSize = scrollY / (maxBackgroundSize - 100)

      background.value.style.transform = 
      'scale(' + (100 + backgroundSize * 0.4) / 100 + ')'
      // foreground1.value.style.transform = 'scale(' + (100 + backgroundSize) / 100 + ')' 
      // foreground2.value.style.transform = 'scale(' + (100 + backgroundSize) / 100 + ')'
      foreground1.value.style.transform = 'translateY(' + (100 + backgroundSize) / 100  + ')'



      
    }

    const foreground1 = ref(null)
    const foreground2 = ref(null)
    const background = ref(null)
    const first = ref(null)
    const second = ref(null)

    return {
      foreground1,
      foreground2,
      background,
      first,
      second,
    }
  }
}
</script>

<style scoped lang="scss">
img.background{
  position: fixed;
  top: 0;
  left: 0;
  min-height: 100%;
  min-width: 1024px;
  width: 100%;
  height: auto;
}

.img-1{
  position: absolute;
  height: 70vh;
  top: 50vh;
}

.img-2{  
  position: absolute;
  height: 70vh;
  top: 50vh;
  right: 0;
}

.section{
  min-height: 100vh;
  position: relative;
}

.main-text{
  position: fixed;
  color: white;
  left: 50%;
  right: 50%;
  bottom: 0;
  transform: translate(-50%, -50%);
}

.section-1{
  margin-bottom: 500px;
  font-size: 4em;
}

.section-2{
  opacity: 0;
}

.section-2-text-box {
  background-color: rgba(255, 255, 255, 0.7);
  color: black;
  text-align: center;
  padding: 50px;
  max-width: 300px;
}

</style>
