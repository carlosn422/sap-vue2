<template>
  <div id="app">
    <Navbar />
    <router-view/>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue"

export default {
  name: "App",
  components: {
    Navbar
  }
}
</script>

<style lang="sass">
#app
  font-family: Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center
  color: #fff
  background-color: #000
</style>
