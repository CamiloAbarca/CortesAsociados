<script setup lang="ts">
import { ref } from 'vue'
import InputText from 'primevue/inputtext'
import Textarea from 'primevue/textarea'
import Button from 'primevue/button'

const form = ref({
  name: '',
  email: '',
  phone: '',
  message: ''
})

const submitted = ref(false)

const handleSubmit = () => {
  submitted.value = true
  setTimeout(() => {
    form.value = { name: '', email: '', phone: '', message: '' }
    submitted.value = false
  }, 3000)
}
</script>

<template>
  <section id="contacto" class="contact">
    <div class="contact-container">
      <div class="section-header">
        <h2 class="section-title">Contáctanos</h2>
        <p class="section-subtitle">
          Estamos aquí para ayudarte. Agenda una consulta gratuita y cuéntanos tu caso.
        </p>
      </div>

      <div class="contact-content">
        <div class="contact-info">
          <div class="info-card">
            <div class="info-icon">
              <i class="pi pi-map-marker"></i>
            </div>
            <div class="info-text">
              <h3>Dirección</h3>
              <p>Av. Providencia 1234, Piso 10<br>Santiago, Chile</p>
            </div>
          </div>

          <div class="info-card">
            <div class="info-icon">
              <i class="pi pi-phone"></i>
            </div>
            <div class="info-text">
              <h3>Teléfono</h3>
              <p>+56 2 2345 6789<br>+56 9 8765 4321</p>
            </div>
          </div>

          <div class="info-card">
            <div class="info-icon">
              <i class="pi pi-envelope"></i>
            </div>
            <div class="info-text">
              <h3>Email</h3>
              <p>contacto@estudiojuridico.cl<br>info@estudiojuridico.cl</p>
            </div>
          </div>

          <div class="info-card">
            <div class="info-icon">
              <i class="pi pi-clock"></i>
            </div>
            <div class="info-text">
              <h3>Horario</h3>
              <p>Lunes a Viernes: 9:00 - 18:00<br>Sábados: 10:00 - 14:00</p>
            </div>
          </div>
        </div>

        <div class="contact-form-wrapper">
          <form @submit.prevent="handleSubmit" class="contact-form">
            <div class="form-group">
              <label for="name">Nombre Completo</label>
              <InputText id="name" v-model="form.name" placeholder="Tu nombre" required />
            </div>

            <div class="form-group">
              <label for="email">Email</label>
              <InputText id="email" v-model="form.email" type="email" placeholder="tu@email.com" required />
            </div>

            <div class="form-group">
              <label for="phone">Teléfono</label>
              <InputText id="phone" v-model="form.phone" placeholder="+56 9 1234 5678" required />
            </div>

            <div class="form-group">
              <label for="message">Mensaje</label>
              <Textarea id="message" v-model="form.message" rows="5" placeholder="Cuéntanos sobre tu caso..." required />
            </div>

            <Button type="submit" label="Enviar Consulta" icon="pi pi-send" size="large" class="submit-btn" />

            <div v-if="submitted" class="success-message">
              <i class="pi pi-check-circle"></i>
              <p>¡Mensaje enviado! Te contactaremos pronto.</p>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact {
  padding: 6rem 2rem;
  background: white;
}

.contact-container {
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

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1.5fr;
  gap: 4rem;
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.info-card {
  display: flex;
  gap: 1.5rem;
  padding: 1.5rem;
  background: var(--color-bg-light);
  border-radius: 12px;
  transition: all 0.3s ease;
}

.info-card:hover {
  transform: translateX(10px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
}

.info-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, var(--color-secondary) 0%, #dbb876 100%);
  border-radius: 12px;
  font-size: 1.5rem;
  color: white;
  flex-shrink: 0;
}

.info-text h3 {
  font-family: var(--font-heading);
  font-size: 1.2rem;
  color: var(--color-primary);
  margin-bottom: 0.5rem;
}

.info-text p {
  color: var(--color-text-light);
  line-height: 1.6;
}

.contact-form-wrapper {
  background: var(--color-bg-light);
  padding: 3rem;
  border-radius: 20px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.05);
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.form-group label {
  font-weight: 600;
  color: var(--color-text);
  font-size: 0.95rem;
}

.submit-btn {
  margin-top: 1rem;
}

.success-message {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
  background: #d4edda;
  border: 1px solid #c3e6cb;
  border-radius: 8px;
  color: #155724;
}

.success-message i {
  font-size: 1.5rem;
}

:deep(.p-inputtext),
:deep(.p-textarea) {
  width: 100%;
  padding: 0.75rem 1rem;
  border: 2px solid #e0e0e0;
  border-radius: 8px;
  transition: all 0.3s ease;
}

:deep(.p-inputtext:focus),
:deep(.p-textarea:focus) {
  border-color: var(--color-secondary);
  box-shadow: 0 0 0 3px rgba(201, 169, 98, 0.1);
}

:deep(.submit-btn.p-button) {
  background-color: #2f455c !important;
  border-color: #2f455c !important;
  color: #fff !important;
}

:deep(.submit-btn.p-button:hover) {
  background-color: #be792b !important; /* un tono más oscuro para hover */
  border-color: #be792b !important;
  color: #fff !important;
}

@media (max-width: 968px) {
  .contact {
    padding: 4rem 1.5rem;
  }

  .section-title {
    font-size: 2.2rem;
  }

  .contact-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .contact-form-wrapper {
    padding: 2rem;
  }
}
</style>
