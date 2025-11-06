<script setup lang="ts">
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="footer">
    <div class="footer-container">
      <div class="footer-content">
        <div class="footer-section">
          <div class="footer-brand">
            <img class="img-nav" src="../assets/logo Orange Ico.png" alt="logo" />
          </div>
          <p class="footer-description">
            Comprometidos con la excelencia legal y la defensa de tus derechos.
            Más de 25 años de experiencia profesional.
          </p>
          <div class="social-links">
            <a href="#" class="social-link"><i class="pi pi-facebook"></i></a>
            <a href="#" class="social-link"><i class="pi pi-twitter"></i></a>
            <a href="#" class="social-link"><i class="pi pi-linkedin"></i></a>
            <a href="#" class="social-link"><i class="pi pi-instagram"></i></a>
          </div>
        </div>

        <div class="footer-section">
          <h3 class="footer-title">Servicios</h3>
          <ul class="footer-links">
            <li><a href="#servicios">Derecho Corporativo</a></li>
            <li><a href="#servicios">Derecho Civil</a></li>
            <li><a href="#servicios">Derecho Inmobiliario</a></li>
            <li><a href="#servicios">Derecho Laboral</a></li>
          </ul>
        </div>

        <div class="footer-section">
          <h3 class="footer-title">Empresa</h3>
          <ul class="footer-links">
            <li><a href="#equipo">Nuestro Equipo</a></li>
            <li><a href="#servicios">Servicios</a></li>
            <li><a href="#contacto">Contacto</a></li>
            <li><a href="#">Casos de Éxito</a></li>
          </ul>
        </div>

        <div class="footer-section">
          <h3 class="footer-title">Contacto</h3>
          <ul class="footer-contact">
            <li>
              <i class="pi pi-map-marker"></i>
              <span>Av. Providencia 1234, Santiago</span>
            </li>
            <li>
              <i class="pi pi-phone"></i>
              <span>+56 2 2345 6789</span>
            </li>
            <li>
              <i class="pi pi-envelope"></i>
              <span>contacto@estudiojuridico.cl</span>
            </li>
          </ul>
        </div>
      </div>

      <div class="footer-bottom">
        <p>&copy; {{ currentYear }} Cortés & Asociados - Abogados. Todos los derechos reservados.</p>
        <div class="footer-legal">
          <a href="https://cabarcadev.com">Desarrollado por CabarcaDev 2025</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>

.img-nav {
  width: auto;
  height: 100px;
  border-radius: 5px;
}

.footer {
  background: linear-gradient(135deg, #1a1a1a 0%, #2c3e50 100%);
  color: white;
  padding: 4rem 2rem 2rem;
}

.footer-container {
  max-width: 1400px;
  margin: 0 auto;
}

.footer-content {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1.5fr;
  gap: 3rem;
  margin-bottom: 3rem;
}

.footer-brand {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-family: var(--font-heading);
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
}

.footer-brand i {
  font-size: 1.8rem;
  color: var(--color-secondary);
}

.footer-description {
  color: rgba(255, 255, 255, 0.7);
  line-height: 1.8;
  margin-bottom: 1.5rem;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  color: white;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: var(--color-secondary);
  transform: translateY(-3px);
}

.footer-title {
  font-family: var(--font-heading);
  font-size: 1.2rem;
  margin-bottom: 1.5rem;
  color: var(--color-secondary);
}

.footer-links {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.footer-links a {
  color: rgba(255, 255, 255, 0.7);
  transition: all 0.3s ease;
  display: inline-block;
}

.footer-links a:hover {
  color: var(--color-secondary);
  transform: translateX(5px);
}

.footer-contact {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.footer-contact li {
  display: flex;
  align-items: flex-start;
  gap: 0.75rem;
  color: rgba(255, 255, 255, 0.7);
}

.footer-contact i {
  color: var(--color-secondary);
  margin-top: 0.25rem;
}

.footer-bottom {
  padding-top: 2rem;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: rgba(255, 255, 255, 0.5);
}

.footer-legal {
  display: flex;
  gap: 1rem;
  align-items: center;
}

.footer-legal a {
  color: rgba(255, 255, 255, 0.5);
  transition: color 0.3s ease;
}

.footer-legal a:hover {
  color: var(--color-secondary);
}

.separator {
  color: rgba(255, 255, 255, 0.3);
}

@media (max-width: 968px) {
  .footer {
    padding: 3rem 1.5rem 2rem;
  }

  .footer-content {
    grid-template-columns: 1fr;
    gap: 2.5rem;
  }

  .footer-bottom {
    flex-direction: column;
    gap: 1rem;
    text-align: center;
  }
}
</style>
