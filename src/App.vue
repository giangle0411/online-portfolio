<template>
  <div id="app">
    <div id="nav">
      <NavBar />
    </div>
    <Introduction />
    <Skills />
    <Projects />
    <Contact />
    <router-view />
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import Introduction from '@/components/Introduction.vue'
import Skills from '@/components/Skills.vue'
import Projects from '@/components/Projects.vue'
import Contact from '@/components/Contact.vue'

export default {
  components: {
    NavBar,
    Introduction,
    Skills,
    Projects,
    Contact
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

::-webkit-scrollbar {
  width: 0.5rem;
}

::-webkit-scrollbar-track {
  background: rgba(0, 49, 87, 0.7);
}

::-webkit-scrollbar-thumb {
  background: #b0b0b0;
}

::-webkit-scrollbar-thumb:hover {
  background: black;
}
</style>
