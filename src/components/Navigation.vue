<script setup lang="ts">
import { ref } from 'vue'
import Button from 'primevue/button'

const mobileMenuOpen = ref(false)

const scrollToSection = (sectionId: string) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
    mobileMenuOpen.value = false
  }
}
</script>

<template>
  <nav class="navbar">
    <div class="nav-container">
      <div class="nav-brand">
        <img class="img-nav" src="../assets/logo Orange Ico.png" alt="logo" />
      </div>

      <div class="nav-links" :class="{ 'active': mobileMenuOpen }">
        <a @click="scrollToSection('inicio')" class="nav-link">Inicio</a>
        <a @click="scrollToSection('servicios')" class="nav-link">Servicios</a>
        <a @click="scrollToSection('equipo')" class="nav-link">Equipo</a>
        <Button label="Contáctanos" severity="secondary" @click="scrollToSection('contacto')" />
      </div>

      <button class="mobile-toggle" @click="mobileMenuOpen = !mobileMenuOpen">
        <i class="pi" :class="mobileMenuOpen ? 'pi-times' : 'pi-bars'"></i>
      </button>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.98);
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.05);
  z-index: 1000;
  transition: all 0.3s ease;
}

.nav-container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 1.2rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-brand {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-family: var(--font-heading);
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--color-primary);
}

.nav-brand i {
  font-size: 1.8rem;
  color: var(--color-secondary);
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 2.5rem;
}

.nav-link {
  font-weight: 500;
  color: var(--color-text);
  cursor: pointer;
  position: relative;
  transition: color 0.3s ease;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--color-secondary);
  transition: width 0.3s ease;
}

.nav-link:hover {
  color: var(--color-secondary);
}

.nav-link:hover::after {
  width: 100%;
}

.img-nav {
  width: auto;
  height: 50px;
  border-radius: 5px;
}

.mobile-toggle {
  display: none;
  background: none;
  border: none;
  font-size: 1.5rem;
  color: var(--color-primary);
  cursor: pointer;
}

@media (max-width: 768px) {
  .nav-links {
    position: fixed;
    top: 76px;
    left: 0;
    right: 0;
    background: white;
    flex-direction: column;
    padding: 2rem;
    gap: 1.5rem;
    transform: translateY(-100%);
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  }

  .nav-links.active {
    transform: translateY(0);
    opacity: 1;
    visibility: visible;
  }

  .mobile-toggle {
    display: block;
  }
}
</style>
