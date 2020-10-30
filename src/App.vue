<template>
  <div id="app">
    <div id="nav">
      <NavBar />
    </div>
    <Introduction />
    <Skills />
    <router-view />
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import Introduction from '@/components/Introduction.vue'
import Skills from '@/components/Skills.vue'

export default {
  components: {
    NavBar,
    Introduction,
    Skills
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
