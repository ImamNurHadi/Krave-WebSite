<script>
import HeaderComponent from './components/HeaderComponent.vue'
import HeroSection from './components/HeroSection.vue'
import ProductsSection from './components/ProductsSection.vue'
import LocationsSection from './components/LocationsSection.vue'
import ReviewsSection from './components/ReviewsSection.vue'
import AboutSection from './components/AboutSection.vue'
import FooterComponent from './components/FooterComponent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    HeroSection,
    ProductsSection,
    LocationsSection,
    ReviewsSection,
    AboutSection,
    FooterComponent
  }
}
</script>

<template>
  <div id="app">
    <HeaderComponent />
    <main class="main-content">
      <HeroSection />
      <ProductsSection />
      <LocationsSection />
      <ReviewsSection />
      <AboutSection />
    </main>
    <FooterComponent />
  </div>
</template>

<style>
/* CSS Reset and Base Styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
  scroll-padding-top: 80px;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  color: #333;
  line-height: 1.6;
  background: transparent;
  overflow-x: hidden;
}

#app {
  min-height: 100vh;
  width: 100%;
  display: flex;
  flex-direction: column;
}

.main-content {
  flex: 1;
  width: 100%;
  display: flex;
  flex-direction: column;
}

/* Global Container */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  width: 100%;
}

/* Global Button Styles */
.btn {
  padding: 12px 24px;
  border: none;
  border-radius: 25px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
  cursor: pointer;
  display: inline-block;
  text-align: center;
  font-family: inherit;
  font-size: 0.95rem;
  border: 2px solid transparent;
}

.btn-primary {
  background: #e91e63;
  color: white;
  border-color: #e91e63;
}

.btn-primary:hover {
  background: #c2185b;
  border-color: #c2185b;
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(233, 30, 99, 0.3);
}

.btn-secondary {
  border: 2px solid #e91e63;
  color: #e91e63;
  background: transparent;
}

.btn-secondary:hover {
  background: #e91e63;
  color: #fff;
  transform: translateY(-2px);
}

/* Global Typography */
h1, h2, h3, h4, h5, h6 {
  font-weight: 700;
  line-height: 1.2;
  margin-bottom: 0.5em;
}

p {
  margin-bottom: 1em;
  line-height: 1.6;
}

/* Global Animations */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-in-up {
  animation: fadeInUp 0.6s ease-out forwards;
}

/* Section Spacing - All sections except hero need to account for fixed header */
section:not(#home) {
  padding: 80px 0;
  width: 100%;
}

section {
  width: 100%;
  display: block;
}

/* Global Responsive */
@media (max-width: 768px) {
  .container {
    padding: 0 15px;
  }
  
  section:not(#home) {
    padding: 60px 0;
  }
  
  .btn {
    padding: 10px 20px;
    font-size: 0.9rem;
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 10px;
  }
  
  section:not(#home) {
    padding: 40px 0;
  }
}

/* Utility Classes */
.text-center {
  text-align: center;
}

.mt-0 { margin-top: 0; }
.mt-1 { margin-top: 0.25rem; }
.mt-2 { margin-top: 0.5rem; }
.mt-3 { margin-top: 1rem; }
.mt-4 { margin-top: 1.5rem; }
.mt-5 { margin-top: 3rem; }

.mb-0 { margin-bottom: 0; }
.mb-1 { margin-bottom: 0.25rem; }
.mb-2 { margin-bottom: 0.5rem; }
.mb-3 { margin-bottom: 1rem; }
.mb-4 { margin-bottom: 1.5rem; }
.mb-5 { margin-bottom: 3rem; }

/* Fix for any layout issues */
img {
  max-width: 100%;
  height: auto;
}

/* Smooth scrolling for anchor links */
a[href^="#"] {
  text-decoration: none;
}

/* Ensure no horizontal overflow */
html, body {
  max-width: 100%;
  overflow-x: hidden;
}
</style>
