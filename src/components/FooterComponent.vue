<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-brand">
          <h3 class="footer-logo">
            <img src="/logo-krave.png" alt="Krave Logo" class="footer-logo-img">
            Krave
          </h3>
          <p>Creating moments of joy, one delicious cookie at a time.</p>
          <div class="social-links">
            <a href="#" class="social-link">📘</a>
            <a href="#" class="social-link">📷</a>
            <a href="#" class="social-link">🐦</a>
            <a href="#" class="social-link">🎵</a>
          </div>
        </div>
        
        <div class="footer-section">
          <h4>Company</h4>
          <ul>
            <li><a href="#about">Our Story</a></li>
            <li><a href="#careers">Careers</a></li>
            <li><a href="#press">Press</a></li>
            <li><a href="#sustainability">Sustainability</a></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h4>Menu</h4>
          <ul>
            <li><a href="#products">View Menu</a></li>
            <li><a href="#nutrition">Nutrition Info</a></li>
            <li><a href="#catering">Catering</a></li>
            <li><a href="#corporate">Corporate Orders</a></li>
          </ul>
        </div>
        
        <div class="footer-section">
          <h4>Support</h4>
          <ul>
            <li><a href="#contact">Contact Us</a></li>
            <li><a href="#locations">Find a Store</a></li>
            <li><a href="#gift-cards">Gift Cards</a></li>
            <li><a href="#rewards">Rewards</a></li>
          </ul>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>&copy; 2025 Krave. All rights reserved.</p>
        <div class="legal-links">
          <a href="#privacy">Privacy Policy</a>
          <a href="#terms">Terms & Conditions</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'FooterComponent'
}
</script>

<style scoped>
.footer {
  background: #333;
  color: #fff;
  padding: 60px 0 30px;
  width: 100vw;
  margin: 0;
  margin-left: calc(-50vw + 50%);
  position: relative;
  left: 0;
  right: 0;
}

.footer .container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  width: 100%;
}

.footer-content {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1fr;
  gap: 40px;
  margin-bottom: 40px;
}

.footer-brand {
  max-width: 300px;
}

.footer-logo {
  font-size: 2.5rem;
  font-weight: 800;
  color: #e91e63;
  margin-bottom: 15px;
  letter-spacing: -0.02em;
  display: flex;
  align-items: center;
  gap: 8px;
}

.footer-logo-img {
  width: 40px;
  height: 40px;
  object-fit: contain;
}

.footer-brand p {
  color: #ccc;
  line-height: 1.6;
  margin-bottom: 25px;
}

.social-links {
  display: flex;
  gap: 15px;
}

.social-link {
  width: 40px;
  height: 40px;
  background: #555;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  text-decoration: none;
  font-size: 1.2rem;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: #e91e63;
  transform: translateY(-3px);
}

.footer-section h4 {
  font-size: 1.2rem;
  font-weight: 700;
  margin-bottom: 20px;
  color: #e91e63;
}

.footer-section ul {
  list-style: none;
}

.footer-section ul li {
  margin-bottom: 10px;
}

.footer-section ul li a {
  color: #ccc;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-section ul li a:hover {
  color: #e91e63;
}

.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 20px;
  border-top: 1px solid #555;
  color: #999;
}

.legal-links {
  display: flex;
  gap: 20px;
}

.legal-links a {
  color: #999;
  text-decoration: none;
  transition: color 0.3s ease;
}

.legal-links a:hover {
  color: #e91e63;
}

/* Responsive */
@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    gap: 30px;
    text-align: center;
  }

  .footer-brand {
    max-width: none;
  }

  .social-links {
    justify-content: center;
  }

  .footer-bottom {
    flex-direction: column;
    gap: 15px;
    text-align: center;
  }
  
  .footer .container {
    padding: 0 15px;
  }
}

@media (max-width: 480px) {
  .footer .container {
    padding: 0 10px;
  }
}
</style> 