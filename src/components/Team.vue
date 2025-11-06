<script setup lang="ts">
import Card from 'primevue/card'

const team = [
  {
    name: 'María González',
    role: 'Socia Fundadora',
    specialty: 'Derecho Corporativo',
    image: 'https://images.pexels.com/photos/3756679/pexels-photo-3756679.jpeg?auto=compress&cs=tinysrgb&w=400'
  },
  {
    name: 'Carlos Rodríguez',
    role: 'Socio Principal',
    specialty: 'Derecho Penal',
    image: 'https://images.pexels.com/photos/5668772/pexels-photo-5668772.jpeg?auto=compress&cs=tinysrgb&w=400'
  },
  {
    name: 'Ana Martínez',
    role: 'Asociada Senior',
    specialty: 'Derecho Civil',
    image: 'https://images.pexels.com/photos/3760607/pexels-photo-3760607.jpeg?auto=compress&cs=tinysrgb&w=400'
  },
  {
    name: 'Roberto Silva',
    role: 'Asociado Senior',
    specialty: 'Derecho Laboral',
    image: 'https://images.pexels.com/photos/5668858/pexels-photo-5668858.jpeg?auto=compress&cs=tinysrgb&w=400'
  }
]
</script>

<template>
  <section id="equipo" class="team">
    <div class="team-container">
      <div class="section-header">
        <h2 class="section-title">Nuestro Equipo</h2>
        <p class="section-subtitle">
          Profesionales altamente calificados con amplia experiencia en distintas áreas del derecho,
          comprometidos con ofrecer soluciones efectivas y personalizadas.
        </p>
      </div>

      <div class="team-grid">
        <Card v-for="(member, index) in team" :key="index" class="team-card">
          <template #header>
            <div class="member-image">
              <img :src="member.image" :alt="member.name" />
              <div class="member-overlay"></div>
            </div>
          </template>
          <template #title>
            {{ member.name }}
          </template>
          <template #subtitle>
            {{ member.role }}
          </template>
          <template #content>
            <p class="member-specialty">{{ member.specialty }}</p>
          </template>
        </Card>
      </div>
    </div>
  </section>
</template>

<style scoped>
.team {
  padding: 6rem 2rem;
  background: var(--color-bg-light);
}

.team-container {
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

.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.team-card {
  transition: all 0.3s ease;
  overflow: hidden;
  border: none;
}

.team-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.member-image {
  position: relative;
  height: 350px;
  overflow: hidden;
}

.member-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.team-card:hover .member-image img {
  transform: scale(1.1);
}

.member-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(26, 26, 26, 0.4) 0%, transparent 60%);
}

.member-specialty {
  color: var(--color-secondary);
  font-weight: 600;
  margin-top: 0.5rem;
}

:deep(.p-card-title) {
  font-family: var(--font-heading);
  font-size: 1.5rem;
  color: var(--color-primary);
  margin-bottom: 0.25rem;
}

:deep(.p-card-subtitle) {
  color: var(--color-text-light);
  font-size: 0.95rem;
}

:deep(.p-card-body) {
  padding: 1.5rem;
}

:deep(.p-card-content) {
  padding-top: 0;
}

@media (max-width: 768px) {
  .team {
    padding: 4rem 1.5rem;
  }

  .section-title {
    font-size: 2.2rem;
  }

  .team-grid {
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1.5rem;
  }

  .member-image {
    height: 300px;
  }
}
</style>
