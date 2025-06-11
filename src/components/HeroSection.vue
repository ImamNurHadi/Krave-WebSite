<template>
  <section class="hero" id="home">
    <div class="hero-container">
      <div class="hero-content">
        <h1 class="hero-title fade-in-up">Premium Cookies & Desserts</h1>
        <p class="hero-subtitle fade-in-up">Indulge in our handcrafted cookies and desserts made with the finest ingredients. Each bite is a moment of pure bliss.</p>
        
        <div class="hero-actions fade-in-up">
          <a href="#products" class="btn btn-primary hero-btn">Explore Menu</a>
          <a href="#locations" class="btn btn-secondary hero-btn">Find Location</a>
        </div>
        
        <div class="week-banner fade-in-up">
          <div class="banner-content">
            <h2>🍪 This Week's Special</h2>
            <p>National Flavors Collection</p>
            <span class="banner-date">Available Now</span>
          </div>
        </div>
      </div>
      
      <div class="hero-stats fade-in-up">
        <div class="stat-item">
          <h3>500K+</h3>
          <p>Happy Customers</p>
        </div>
        <div class="stat-item">
          <h3>50+</h3>
          <p>Locations</p>
        </div>
        <div class="stat-item">
          <h3>100+</h3>
          <p>Unique Flavors</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HeroSection'
}
</script>

<style scoped>
.hero {
  background: linear-gradient(135deg, #fce4ec 0%, #f8bbd9 100%);
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding-top: 80px;
  width: 100vw;
  margin-left: calc(-50vw + 50%);
  box-sizing: border-box;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="50" cy="50" r="2" fill="%23ffffff" opacity="0.1"/></svg>') repeat;
  pointer-events: none;
}

.hero-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  width: 100%;
  position: relative;
  z-index: 2;
}

.hero-content {
  text-align: center;
  margin-bottom: 60px;
}

.hero-title {
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 800;
  color: #333;
  margin-bottom: 24px;
  letter-spacing: -0.02em;
  line-height: 1.1;
}

.hero-subtitle {
  font-size: clamp(1.1rem, 2.5vw, 1.3rem);
  color: #555;
  margin-bottom: 40px;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
  font-weight: 400;
}

.hero-actions {
  display: flex;
  gap: 20px;
  justify-content: center;
  margin-bottom: 40px;
  flex-wrap: wrap;
}

.hero-btn {
  padding: 15px 32px;
  font-size: 1.1rem;
  font-weight: 600;
  min-width: 160px;
}

.week-banner {
  background: #fff;
  padding: 24px;
  border-radius: 20px;
  margin: 0 auto 40px;
  max-width: 400px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  border: 2px solid #e91e63;
}

.banner-content h2 {
  color: #e91e63;
  font-size: 1.6rem;
  font-weight: 700;
  margin-bottom: 8px;
}

.banner-content p {
  color: #666;
  font-size: 1rem;
  margin-bottom: 12px;
  font-weight: 500;
}

.banner-date {
  background: #e91e63;
  color: #fff;
  padding: 6px 16px;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 600;
  display: inline-block;
}

.hero-stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  max-width: 600px;
  margin: 0 auto;
}

.stat-item {
  text-align: center;
  padding: 16px;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 15px;
  backdrop-filter: blur(10px);
}

.stat-item h3 {
  font-size: 2.2rem;
  font-weight: 800;
  color: #e91e63;
  margin-bottom: 8px;
  line-height: 1;
}

.stat-item p {
  color: #555;
  font-weight: 500;
  font-size: 0.9rem;
  margin: 0;
}

/* Animation delays */
.fade-in-up:nth-child(1) { animation-delay: 0.1s; }
.fade-in-up:nth-child(2) { animation-delay: 0.2s; }
.fade-in-up:nth-child(3) { animation-delay: 0.3s; }
.fade-in-up:nth-child(4) { animation-delay: 0.4s; }
.fade-in-up:nth-child(5) { animation-delay: 0.5s; }

/* Responsive */
@media (max-width: 768px) {
  .hero {
    min-height: 100vh;
    padding: 100px 0 40px;
    margin-left: 0;
    width: 100%;
  }

  .hero-container {
    padding: 0 15px;
  }

  .hero-content {
    margin-bottom: 40px;
  }

  .hero-actions {
    flex-direction: column;
    align-items: center;
    gap: 15px;
    margin-bottom: 30px;
  }

  .hero-btn {
    width: 200px;
    padding: 12px 24px;
  }

  .week-banner {
    margin-bottom: 30px;
    padding: 20px;
  }

  .banner-content h2 {
    font-size: 1.4rem;
  }

  .hero-stats {
    grid-template-columns: 1fr;
    gap: 15px;
    max-width: 280px;
  }

  .stat-item {
    padding: 12px;
  }

  .stat-item h3 {
    font-size: 1.8rem;
  }
}

@media (max-width: 480px) {
  .hero {
    min-height: 90vh;
    padding: 90px 0 20px;
  }

  .week-banner {
    padding: 16px;
    margin-bottom: 25px;
  }

  .banner-content h2 {
    font-size: 1.2rem;
  }

  .banner-content p {
    font-size: 0.9rem;
  }

  .hero-stats {
    gap: 12px;
  }

  .stat-item h3 {
    font-size: 1.6rem;
  }

  .stat-item p {
    font-size: 0.85rem;
  }
}
</style> 