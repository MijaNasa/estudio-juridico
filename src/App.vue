<template>
  <div class="min-h-screen bg-white">
    <!-- Hero Section -->
    <HeroSection 
      :title="heroData.title"
      :subtitle="heroData.subtitle"
      :backgroundImage="heroData.backgroundImage"
      :whatsappNumber="contactData.whatsappNumber"
      :whatsappMessage="contactData.whatsappMessage"
    />
    
    <!-- Info Section -->
    <InfoSection 
      :title="infoData.title"
      :description="infoData.description"
      :services="infoData.services"
      :image="infoData.image"
      :whatsappNumber="contactData.whatsappNumber"
      :whatsappMessage="contactData.whatsappMessage"
    />
    
    <!-- Testimonials Section -->
    <TestimonialsSection :testimonials="testimonialsData" />
    
    <!-- Final CTA Section -->
    <FinalCTASection 
      :title="ctaData.title"
      :subtitle="ctaData.subtitle"
      :whatsappNumber="contactData.whatsappNumber"
      :whatsappMessage="contactData.whatsappMessage"
    />
    
    <!-- Footer -->
    <footer class="bg-slate-900 text-white py-8">
      <div class="container mx-auto px-4 text-center">
        <p>&copy; 2024 Estudio Jurídico Especializado. Todos los derechos reservados.</p>
        <p class="text-slate-400 text-sm mt-2">Matrícula profesional: XXXXX</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// Datos editables del Hero
const heroData = ref({
  title: "¿Estás pasando por un divorcio complicado?",
  subtitle: "Te ayudamos a proteger tus derechos y los de tu familia con asesoramiento legal especializado",
  backgroundImage: "/placeholder.svg?height=600&width=1200"
})

// Datos de contacto
const contactData = ref({
  whatsappNumber: "5491123456789", // Reemplazar por número real
  whatsappMessage: "Hola, quiero consultar sobre mi caso"
})

// Datos de la sección informativa
const infoData = ref({
  title: "¿Cómo trabajamos en tu caso?",
  description: "Nuestro estudio se especializa en derecho de familia, brindando asesoramiento integral y personalizado. Entendemos que cada situación es única y requiere un enfoque específico.",
  services: [
    "Divorcios consensuados y contenciosos",
    "Régimen de visitas y tenencia de menores",
    "Liquidación de sociedad conyugal",
    "Violencia familiar y medidas cautelares",
    "Adopciones y filiación",
    "Alimentos y cuota alimentaria"
  ],
  image: "/placeholder.svg?height=400&width=600"
})

// Datos de testimonios
const testimonialsData = ref([
  {
    name: "María González",
    text: "Excelente atención y profesionalismo. Me ayudaron en un momento muy difícil y lograron el mejor resultado para mi familia.",
    rating: 5
  },
  {
    name: "Carlos Rodríguez",
    text: "Muy recomendable. Transparentes en sus honorarios y siempre disponibles para resolver mis dudas.",
    rating: 5
  },
  {
    name: "Ana Martínez",
    text: "Gracias a su trabajo pude resolver mi situación de manera rápida y favorable. Totalmente profesionales.",
    rating: 5
  }
])

// Datos del CTA final
const ctaData = ref({
  title: "No esperes más para resolver tu situación legal",
  subtitle: "Contactanos ahora y recibí asesoramiento especializado sin compromiso"
})
</script>

<style>
@import 'tailwindcss';

/* Hero Section */
.hero-section {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  overflow: hidden;
}

.hero-background {
  position: absolute;
  inset: 0;
  z-index: 0;
}

.hero-background img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background: rgba(15, 23, 42, 0.8);
}

.hero-content {
  position: relative;
  z-index: 10;
  text-align: center;
  max-width: 64rem;
  margin: 0 auto;
  padding: 0 1rem;
}

.hero-title {
  font-size: 2.25rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  line-height: 1.2;
}

@media (min-width: 768px) {
  .hero-title {
    font-size: 3.75rem;
  }
}

.hero-subtitle {
  font-size: 1.25rem;
  margin-bottom: 2rem;
  color: rgb(226, 232, 240);
  max-width: 48rem;
  margin-left: auto;
  margin-right: auto;
}

@media (min-width: 768px) {
  .hero-subtitle {
    font-size: 1.5rem;
  }
}

/* Contact Button */
.contact-button {
  display: inline-flex;
  align-items: center;
  gap: 0.75rem;
  border-radius: 0.5rem;
  font-weight: 600;
  transition: all 0.3s ease;
  text-decoration: none;
}

.contact-button:hover {
  transform: scale(1.05);
}

.contact-button:focus {
  outline: none;
  box-shadow: 0 0 0 4px rgba(16, 185, 129, 0.3);
}

.contact-button-primary {
  background-color: rgb(16, 185, 129);
  color: white;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

.contact-button-primary:hover {
  background-color: rgb(5, 150, 105);
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
}

.contact-button-light {
  background-color: white;
  color: rgb(15, 23, 42);
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

.contact-button-light:hover {
  background-color: rgb(248, 250, 252);
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
}

.contact-button-small {
  padding: 0.5rem 1rem;
  font-size: 0.875rem;
}

.contact-button-medium {
  padding: 0.75rem 1.5rem;
  font-size: 1rem;
}

.contact-button-large {
  padding: 1rem 2rem;
  font-size: 1.125rem;
}

/* Info Section */
.info-section {
  padding: 4rem 0;
  background-color: rgb(248, 250, 252);
}

@media (min-width: 768px) {
  .info-section {
    padding: 6rem 0;
  }
}

.info-grid {
  display: grid;
  gap: 3rem;
  align-items: center;
}

@media (min-width: 1024px) {
  .info-grid {
    grid-template-columns: 1fr 1fr;
  }
}

.info-content {
  order: 2;
}

@media (min-width: 1024px) {
  .info-content {
    order: 1;
  }
}

.info-image-container {
  order: 1;
}

@media (min-width: 1024px) {
  .info-image-container {
    order: 2;
  }
}

.info-title {
  font-size: 1.875rem;
  font-weight: 700;
  color: rgb(15, 23, 42);
  margin-bottom: 1.5rem;
}

@media (min-width: 768px) {
  .info-title {
    font-size: 2.25rem;
  }
}

.info-description {
  font-size: 1.125rem;
  color: rgb(71, 85, 105);
  margin-bottom: 2rem;
  line-height: 1.6;
}

.services-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.service-item {
  display: flex;
  align-items: flex-start;
  gap: 0.75rem;
  margin-bottom: 0.75rem;
}

.service-icon {
  flex-shrink: 0;
  width: 1.5rem;
  height: 1.5rem;
  background-color: rgb(209, 250, 229);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 0.125rem;
}

.service-icon svg {
  width: 1rem;
  height: 1rem;
  color: rgb(5, 150, 105);
}

.service-text {
  color: rgb(51, 65, 85);
}

/* Testimonials */
.testimonials-section {
  padding: 4rem 0;
  background-color: white;
}

@media (min-width: 768px) {
  .testimonials-section {
    padding: 6rem 0;
  }
}

.testimonials-grid {
  display: grid;
  gap: 2rem;
}

@media (min-width: 768px) {
  .testimonials-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .testimonials-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.testimonial-card {
  background-color: rgb(248, 250, 252);
  padding: 1.5rem;
  border-radius: 0.5rem;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  transition: box-shadow 0.3s ease;
}

.testimonial-card:hover {
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.stars {
  display: flex;
  gap: 0.25rem;
  margin-bottom: 1rem;
}

.star {
  width: 1.25rem;
  height: 1.25rem;
  color: rgb(251, 191, 36);
}

.testimonial-text {
  color: rgb(51, 65, 85);
  margin-bottom: 1rem;
  font-style: italic;
}

.testimonial-author {
  color: rgb(15, 23, 42);
  font-weight: 600;
  font-style: normal;
}

/* CTA Section */
.cta-section {
  padding: 4rem 0;
  background-color: rgb(15, 23, 42);
  color: white;
  text-align: center;
}

@media (min-width: 768px) {
  .cta-section {
    padding: 6rem 0;
  }
}

.cta-title {
  font-size: 1.875rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  max-width: 64rem;
  margin-left: auto;
  margin-right: auto;
}

@media (min-width: 768px) {
  .cta-title {
    font-size: 2.25rem;
  }
}

.cta-subtitle {
  font-size: 1.25rem;
  color: rgb(203, 213, 225);
  margin-bottom: 2rem;
  max-width: 32rem;
  margin-left: auto;
  margin-right: auto;
}

/* Utilities */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.animate-bounce {
  animation: bounce 1s infinite;
}

@keyframes bounce {
  0%, 20%, 53%, 80%, 100% {
    transform: translateY(0);
  }
  40%, 43% {
    transform: translateY(-30px);
  }
  70% {
    transform: translateY(-15px);
  }
  90% {
    transform: translateY(-4px);
  }
}
</style>