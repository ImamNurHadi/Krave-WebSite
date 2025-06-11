<template>
  <section class="hero" id="home">
    <div class="video-background">
      <video autoplay muted loop playsinline>
        <source src="/Krave.mp4" type="video/mp4">
      </video>
      <div class="video-overlay"></div>
    </div>
    
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

.video-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.video-background video {
  width: 100%;
  height: 100%;
  object-fit: cover;
  position: absolute;
  top: 0;
  left: 0;
}

.video-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.4);
  z-index: 2;
}

.hero-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  width: 100%;
  position: relative;
  z-index: 3;
}

.hero-content {
  text-align: center;
  margin-bottom: 60px;
}

.hero-title {
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 800;
  color: #fff;
  margin-bottom: 24px;
  letter-spacing: -0.02em;
  line-height: 1.1;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.hero-subtitle {
  font-size: clamp(1.1rem, 2.5vw, 1.3rem);
  color: #f0f0f0;
  margin-bottom: 40px;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
  font-weight: 400;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
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
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

.week-banner {
  background: rgba(255, 255, 255, 0.95);
  padding: 24px;
  border-radius: 20px;
  margin: 0 auto 40px;
  max-width: 400px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
  border: 2px solid #e91e63;
  backdrop-filter: blur(10px);
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
  background: rgba(255, 255, 255, 0.15);
  border-radius: 15px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.stat-item h3 {
  font-size: 2.2rem;
  font-weight: 800;
  color: #fff;
  margin-bottom: 8px;
  line-height: 1;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
}

.stat-item p {
  color: #f0f0f0;
  font-weight: 500;
  font-size: 0.9rem;
  margin: 0;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
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

  .hero-actions {
    flex-direction: column;
    align-items: center;
  }

  .hero-btn {
    min-width: 200px;
  }

  .hero-stats {
    grid-template-columns: 1fr;
    gap: 20px;
    max-width: 300px;
  }

  .week-banner {
    margin: 0 15px 40px;
    max-width: none;
  }
}

@media (max-width: 480px) {
  .hero-container {
    padding: 0 10px;
  }

  .hero-stats {
    gap: 16px;
  }

  .stat-item {
    padding: 12px;
  }
}
</style> 