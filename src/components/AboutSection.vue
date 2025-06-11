<template>
  <section class="about" id="about">
    <div class="container">
      <div class="about-hero">
        <h2 class="section-title">Our Sweet Story</h2>
        <p class="hero-text">
          At Krave, we believe every moment deserves something extraordinary. What started as a passion for 
          creating the perfect cookie has grown into a mission to bring joy, one delicious bite at a time.
        </p>
      </div>
      
      <div class="story-content">
        <div class="story-grid">
          <div class="story-item">
            <div class="story-icon">🏠</div>
            <h3>Founded in 2018</h3>
            <p>Started in a small kitchen with big dreams and an even bigger passion for creating the perfect cookie experience.</p>
          </div>
          <div class="story-item">
            <div class="story-icon">👥</div>
            <h3>Family Owned</h3>
            <p>Still proudly family-owned and operated, bringing that personal touch to every batch we make.</p>
          </div>
          <div class="story-item">
            <div class="story-icon">🌟</div>
            <h3>Premium Quality</h3>
            <p>We source only the finest ingredients and never compromise on quality, because you deserve the best.</p>
          </div>
          <div class="story-item">
            <div class="story-icon">💝</div>
            <h3>Community First</h3>
            <p>Supporting local communities and creating moments of joy that bring people together.</p>
          </div>
        </div>
      </div>
      
      <div class="values-section">
        <h3 class="values-title">What Drives Us</h3>
        <div class="values-grid">
          <div class="value-card">
            <h4>Quality First</h4>
            <p>Every cookie is made with premium ingredients and baked fresh daily. We never cut corners because quality is our promise to you.</p>
          </div>
          <div class="value-card">
            <h4>Innovation</h4>
            <p>We're constantly creating new flavors and perfecting our recipes, pushing the boundaries of what a cookie can be.</p>
          </div>
          <div class="value-card">
            <h4>Experience</h4>
            <p>From the moment you walk in to the last bite, we're committed to creating an unforgettable experience.</p>
          </div>
        </div>
      </div>
      
      <div class="team-section">
        <h3 class="team-title">Meet Our Team</h3>
        <div class="team-grid">
          <div class="team-member">
            <div class="member-photo">
              <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=300&h=300&fit=crop&crop=face" alt="Alex Johnson">
            </div>
            <div class="member-info">
              <h4>Alex Johnson</h4>
              <p class="role">Founder & Head Baker</p>
              <p class="bio">"I started Krave with a simple mission: create cookies so good, they become unforgettable moments."</p>
            </div>
          </div>
          <div class="team-member">
            <div class="member-photo">
              <img src="https://images.unsplash.com/photo-1494790108755-2616b332c2c2?w=300&h=300&fit=crop&crop=face" alt="Sarah Mitchell">
            </div>
            <div class="member-info">
              <h4>Sarah Mitchell</h4>
              <p class="role">Chief Recipe Developer</p>
              <p class="bio">"Every new flavor is a labor of love. I spend months perfecting each recipe until it's absolutely perfect."</p>
            </div>
          </div>
          <div class="team-member">
            <div class="member-photo">
              <img src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=300&h=300&fit=crop&crop=face" alt="Mike Rodriguez">
            </div>
            <div class="member-info">
              <h4>Mike Rodriguez</h4>
              <p class="role">Operations Manager</p>
              <p class="bio">"I ensure every location maintains our high standards and that every customer feels like family."</p>
            </div>
          </div>
        </div>
      </div>
      
      <div class="commitment-section">
        <h3 class="commitment-title">Our Commitment</h3>
        <div class="commitment-grid">
          <div class="commitment-item">
            <div class="commitment-icon">🌱</div>
            <h4>Sustainability</h4>
            <p>We're committed to sustainable practices, from sourcing ingredients to eco-friendly packaging.</p>
          </div>
          <div class="commitment-item">
            <div class="commitment-icon">🤝</div>
            <h4>Community</h4>
            <p>Supporting local farmers, charities, and events because we believe in giving back to our communities.</p>
          </div>
          <div class="commitment-item">
            <div class="commitment-icon">💫</div>
            <h4>Excellence</h4>
            <p>Never settling for "good enough" - we constantly strive to exceed expectations in everything we do.</p>
          </div>
        </div>
      </div>
      
      <div class="cta-section">
        <h3>Ready to Join Our Story?</h3>
        <p>Experience the difference that passion and quality make. Visit us today and taste what makes Krave special.</p>
        <div class="cta-buttons">
          <a href="#locations" class="btn btn-primary">Find a Location</a>
          <a href="#products" class="btn btn-secondary">View Menu</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'AboutSection'
}
</script>

<style scoped>
.about {
  padding: 100px 0;
  background: #fff;
}

.about-hero {
  text-align: center;
  margin-bottom: 80px;
}

.section-title {
  font-size: 3rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 30px;
}

.hero-text {
  font-size: 1.3rem;
  color: #666;
  max-width: 800px;
  margin: 0 auto;
  line-height: 1.6;
}

.story-content {
  margin-bottom: 100px;
}

.story-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
  margin-top: 60px;
}

.story-item {
  text-align: center;
  padding: 40px 20px;
  background: #f8f9fa;
  border-radius: 20px;
  transition: transform 0.3s ease;
}

.story-item:hover {
  transform: translateY(-10px);
}

.story-icon {
  font-size: 3rem;
  margin-bottom: 20px;
}

.story-item h3 {
  font-size: 1.5rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 15px;
}

.story-item p {
  color: #666;
  line-height: 1.6;
}

.values-section,
.team-section,
.commitment-section {
  margin-bottom: 100px;
}

.values-title,
.team-title,
.commitment-title {
  text-align: center;
  font-size: 2.5rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 50px;
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
}

.value-card {
  background: linear-gradient(135deg, #e91e63, #c2185b);
  color: #fff;
  padding: 40px 30px;
  border-radius: 20px;
  text-align: center;
}

.value-card h4 {
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 20px;
}

.value-card p {
  line-height: 1.6;
  opacity: 0.9;
}

.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 40px;
}

.team-member {
  background: #f8f9fa;
  padding: 30px;
  border-radius: 20px;
  text-align: center;
  transition: transform 0.3s ease;
}

.team-member:hover {
  transform: translateY(-5px);
}

.member-photo {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  overflow: hidden;
  margin: 0 auto 25px;
  border: 4px solid #e91e63;
}

.member-photo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.member-info h4 {
  font-size: 1.4rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 5px;
}

.role {
  color: #e91e63;
  font-weight: 600;
  margin-bottom: 15px;
}

.bio {
  color: #666;
  line-height: 1.6;
  font-style: italic;
}

.commitment-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
}

.commitment-item {
  text-align: center;
  padding: 30px;
}

.commitment-icon {
  font-size: 3rem;
  margin-bottom: 20px;
}

.commitment-item h4 {
  font-size: 1.4rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 15px;
}

.commitment-item p {
  color: #666;
  line-height: 1.6;
}

.cta-section {
  text-align: center;
  background: linear-gradient(135deg, #fce4ec 0%, #f8bbd9 100%);
  padding: 60px 40px;
  border-radius: 20px;
  margin-top: 80px;
}

.cta-section h3 {
  font-size: 2.2rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 20px;
}

.cta-section p {
  font-size: 1.2rem;
  color: #666;
  margin-bottom: 30px;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.cta-buttons {
  display: flex;
  gap: 20px;
  justify-content: center;
}

.cta-buttons .btn {
  padding: 15px 30px;
  font-size: 1.1rem;
}

/* Responsive */
@media (max-width: 768px) {
  .story-grid {
    grid-template-columns: 1fr;
    gap: 30px;
  }

  .values-grid,
  .team-grid,
  .commitment-grid {
    grid-template-columns: 1fr;
  }

  .cta-buttons {
    flex-direction: column;
    align-items: center;
  }

  .cta-buttons .btn {
    width: 200px;
  }

  .section-title {
    font-size: 2.5rem;
  }

  .hero-text {
    font-size: 1.1rem;
  }

  .values-title,
  .team-title,
  .commitment-title {
    font-size: 2rem;
  }
}
</style> 