<script setup lang="ts">
import Card from 'primevue/card'

const services = [
  {
    icon: 'pi-briefcase',
    title: 'Derecho Corporativo',
    description: 'Asesoramiento integral en constitución de empresas, contratos comerciales y fusiones.'
  },
  {
    icon: 'pi-home',
    title: 'Derecho Civil',
    description: 'Gestión de sucesiones, contratos, derecho de familia y resolución de conflictos civiles.'
  },
  {
    icon: 'pi-building',
    title: 'Derecho Inmobiliario',
    description: 'Compraventa, arrendamientos, urbanismo y toda asesoría relacionada con propiedades.'
  },
  {
    icon: 'pi-users',
    title: 'Derecho Laboral',
    description: 'Defensa en conflictos laborales, despidos, negociación colectiva y compliance laboral.'
  },
  {
    icon: 'pi-shield',
    title: 'Derecho Penal',
    description: 'Defensa penal en todas las instancias, desde investigaciones hasta juicios orales.'
  },
  {
    icon: 'pi-dollar',
    title: 'Derecho Tributario',
    description: 'Planificación fiscal, defensa ante el SII y resolución de contingencias tributarias.'
  }
]
</script>

<template>
  <section id="servicios" class="services">
    <div class="services-container">
      <div class="section-header">
        <h2 class="section-title">Nuestros Servicios</h2>
        <p class="section-subtitle">
          Ofrecemos asesoría legal especializada en diversas áreas del derecho,
          adaptándonos a las necesidades específicas de cada cliente.
        </p>
      </div>

      <div class="services-grid">
        <Card v-for="(service, index) in services" :key="index" class="service-card">
          <template #header>
            <div class="service-icon">
              <i class="pi" :class="service.icon"></i>
            </div>
          </template>
          <template #title>
            {{ service.title }}
          </template>
          <template #content>
            <p class="service-description">{{ service.description }}</p>
          </template>
        </Card>
      </div>
    </div>
  </section>
</template>

<style scoped>
.pi{
  font-size: 2.5rem;
}

.services {
  padding: 6rem 2rem;
  background: white;
}

.services-container {
  max-width: 1400px;
  margin: 0 auto;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 3rem;
  color: var(--color-primary);
  margin-bottom: 1rem;
}

.section-subtitle {
  font-size: 1.2rem;
  color: var(--color-text-light);
  max-width: 700px;
  margin: 0 auto;
  line-height: 1.8;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.service-card {
  transition: all 0.3s ease;
  border: 1px solid #e0e0e0;
  height: 100%;
}

.service-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
}

.service-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 80px;
  height: 80px;
  margin: 2rem auto 1rem;
  background: linear-gradient(135deg, var(--color-secondary) 0%, #dbb876 100%);
  border-radius: 20px;
  font-size: 2rem;
  color: white;
  transition: all 0.3s ease;
}

.service-card:hover .service-icon {
  transform: scale(1.1) rotate(5deg);
}

.service-description {
  color: var(--color-text-light);
  line-height: 1.8;
}

:deep(.p-card-title) {
  font-family: var(--font-heading);
  font-size: 1.5rem;
  color: var(--color-primary);
  text-align: center;
  margin-bottom: 1rem;
}

:deep(.p-card-body) {
  padding: 1.5rem;
}

@media (max-width: 768px) {
  .services {
    padding: 4rem 1.5rem;
  }

  .section-title {
    font-size: 2.2rem;
  }

  .services-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
}
</style>
