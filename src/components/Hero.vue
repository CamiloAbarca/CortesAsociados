<script setup lang="ts">
import Button from 'primevue/button'

const scrollToContact = () => {
  const element = document.getElementById('contacto')
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<template>
  <section id="inicio" class="hero">
    <div class="hero-content">
      <div class="hero-text">
        <h1 class="hero-title">
          Defendemos Tus <span class="highlight">Derechos</span> con Excelencia
        </h1>
        <p class="hero-subtitle">
          Más de 25 años de experiencia brindando asesoría legal integral.
          Comprometidos con la justicia y los mejores resultados para nuestros clientes.
        </p>
        <div class="hero-actions">
          <Button class="agendar-btn" label="Agendar Consulta" icon="pi pi-calendar" size="large" @click="scrollToContact" />
        </div>
        <div class="hero-stats">
          <div class="stat">
            <div class="stat-number">25+</div>
            <div class="stat-label">Años de Experiencia</div>
          </div>
          <div class="stat">
            <div class="stat-number">1500+</div>
            <div class="stat-label">Casos Exitosos</div>
          </div>
          <div class="stat">
            <div class="stat-number">98%</div>
            <div class="stat-label">Satisfacción</div>
          </div>
        </div>
      </div>
      <div class="hero-image">
        <img src="../assets/logo Orange.png" alt="Estudio de abogados profesional" />
        <div class="image-overlay"></div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 8rem 2rem 4rem;
  background: linear-gradient(135deg, #f8f8f8 0%, #ffffff 100%);
}

.hero-content {
  max-width: 1400px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.hero-text {
  animation: fadeInLeft 1s ease-out;
}

.hero-title {
  font-size: 3.5rem;
  line-height: 1.1;
  margin-bottom: 1.5rem;
  color: var(--color-primary);
}

.highlight {
  color: var(--color-secondary);
  position: relative;
}

.hero-subtitle {
  font-size: 1.2rem;
  line-height: 1.8;
  color: var(--color-text-light);
  margin-bottom: 2.5rem;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  margin-bottom: 3rem;
  flex-wrap: wrap;
}

.hero-stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  padding-top: 2rem;
  border-top: 2px solid #e0e0e0;
}

.stat {
  text-align: left;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--color-secondary);
  font-family: var(--font-heading);
}

.stat-label {
  font-size: 0.9rem;
  color: var(--color-text-light);
  margin-top: 0.25rem;
}

.hero-image {
  position: relative;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
  animation: fadeInRight 1s ease-out;
}

.hero-image img {
  width: 100%;
  height: 600px;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.hero-image:hover img {
  transform: scale(1.05);
}

.image-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(201, 169, 98, 0.1) 0%, rgba(26, 26, 26, 0.1) 100%);
}

:deep(.agendar-btn.p-button) {
  background-color: #2f455c !important;
  border-color: #2f455c !important;
  color: #fff !important;
}

:deep(.agendar-btn.p-button:hover) {
  background-color: #be792b !important; /* un tono más oscuro para hover */
  border-color: #be792b !important;
  color: #fff !important;
}

@keyframes fadeInLeft {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInRight {
  from {
    opacity: 0;
    transform: translateX(50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@media (max-width: 968px) {
  .hero {
    padding: 6rem 1.5rem 3rem;
  }

  .hero-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .hero-title {
    font-size: 2.5rem;
  }

  .hero-subtitle {
    font-size: 1.1rem;
  }

  .hero-stats {
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
  }

  .stat-number {
    font-size: 2rem;
  }

  .hero-image img {
    height: 400px;
  }
}
</style>
