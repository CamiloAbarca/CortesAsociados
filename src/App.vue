<script setup lang="ts">
import Navigation from './components/Navigation.vue'
import Hero from './components/Hero.vue'
import Services from './components/Services.vue'
import Team from './components/Team.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="app">
    <Navigation />
    <Hero />
    <Services />
    <Team />
    <Contact />
    <Footer />
  </div>
</template>

<style scoped>
.app {
  width: 100%;
  overflow-x: hidden;
}
</style>
