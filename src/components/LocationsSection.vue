<template>
  <section class="locations" id="locations">
    <div class="container">
      <h2 class="section-title">Find Our Locations</h2>
      <p class="section-subtitle">Visit us at any of our convenient locations for the freshest cookies and desserts</p>
      
      <!-- Map Section - Full Width -->
      <div class="map-section">
        <div class="map-container">
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d387190.2799160891!2d-74.25987701513004!3d40.69767006272707!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zNDDCsDQxJzUyLjYiTiA3NMKwMDAnMDAuMCJX!5e0!3m2!1sen!2sus!4v1635959999999!5m2!1sen!2sus"
            width="100%"
            height="500"
            style="border:0; border-radius: 15px;"
            allowfullscreen=""
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade">
          </iframe>
        </div>
      </div>

      <!-- Store Information Grid - Side by Side -->
      <div class="store-info-grid">
        <!-- Main Store Information -->
        <div class="main-store-info">
          <h3>Our Main Store</h3>
          <div class="store-card">
            <div class="store-header">
              <h4>Krave Cookies & Desserts</h4>
              <span class="status open">Open Now</span>
            </div>
            
            <div class="store-details">
              <div class="detail-item">
                <i class="icon">📍</i>
                <div>
                  <strong>Address</strong>
                  <p>123 Sweet Street, Cookie District<br>New York, NY 10001</p>
                </div>
              </div>
              
              <div class="detail-item">
                <i class="icon">📞</i>
                <div>
                  <strong>Phone</strong>
                  <p>(555) 123-KRAV</p>
                </div>
              </div>
              
              <div class="detail-item">
                <i class="icon">🕒</i>
                <div>
                  <strong>Hours</strong>
                  <div class="hours-list">
                    <div class="hour-item">
                      <span>Mon - Thu</span>
                      <span>8:00 AM - 9:00 PM</span>
                    </div>
                    <div class="hour-item">
                      <span>Fri - Sat</span>
                      <span>8:00 AM - 10:00 PM</span>
                    </div>
                    <div class="hour-item">
                      <span>Sunday</span>
                      <span>9:00 AM - 8:00 PM</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            
            <div class="store-actions">
              <a href="https://g.co/kgs/Kge4Ynn" target="_blank" class="btn btn-primary">Get Directions</a>
              <a href="tel:5551234567" class="btn btn-secondary">Call Store</a>
            </div>
          </div>
          
          <!-- Additional Store Features -->
          <div class="store-features-mini">
            <h4>Store Features</h4>
            <div class="feature-tags">
              <span class="feature-tag">🚗 Drive-Thru</span>
              <span class="feature-tag">☕ Coffee Bar</span>
              <span class="feature-tag">🎂 Custom Cakes</span>
              <span class="feature-tag">📦 Online Orders</span>
              <span class="feature-tag">🅿️ Free Parking</span>
              <span class="feature-tag">♿ Wheelchair Accessible</span>
            </div>
          </div>


        </div>
        
        <!-- Other Locations -->
        <div class="other-locations">
          <h3>Other Locations</h3>
          <div class="location-list">
            <div class="location-item">
              <h5>Downtown Branch</h5>
              <p>456 Main Ave, Downtown NY</p>
              <span class="distance">2.3 miles away</span>
            </div>
            <div class="location-item">
              <h5>Mall Location</h5>
              <p>789 Shopping Blvd, Mall Plaza</p>
              <span class="distance">4.8 miles away</span>
            </div>
            <div class="location-item">
              <h5>Airport Terminal</h5>
              <p>JFK Airport Terminal 4</p>
              <span class="distance">12.1 miles away</span>
            </div>
            <div class="location-item">
              <h5>Uptown Store</h5>
              <p>321 Broadway, Uptown NY</p>
              <span class="distance">6.5 miles away</span>
            </div>
            <div class="location-item">
              <h5>Brooklyn Branch</h5>
              <p>987 Park Ave, Brooklyn NY</p>
              <span class="distance">8.2 miles away</span>
            </div>
            <div class="location-item">
              <h5>Queens Location</h5>
              <p>654 Queens Blvd, Queens NY</p>
              <span class="distance">11.3 miles away</span>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Store Features -->
      <div class="store-features">
        <h3>What Makes Our Stores Special</h3>
        <div class="features-grid">
          <div class="feature-item">
            <div class="feature-icon">🍪</div>
            <h4>Fresh Daily</h4>
            <p>All cookies baked fresh every morning in-store</p>
          </div>
          <div class="feature-item">
            <div class="feature-icon">☕</div>
            <h4>Coffee & Drinks</h4>
            <p>Premium coffee and beverages to pair with your treats</p>
          </div>
          <div class="feature-item">
            <div class="feature-icon">🎂</div>
            <h4>Custom Orders</h4>
            <p>Special occasion cakes and bulk orders available</p>
          </div>
          <div class="feature-item">
            <div class="feature-icon">🚗</div>
            <h4>Drive-Thru</h4>
            <p>Quick and convenient drive-thru service available</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'LocationsSection'
}
</script>

<style scoped>
.locations {
  padding: 100px 0;
  background: transparent;
}

.section-title {
  text-align: center;
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 700;
  color: #333;
  margin-bottom: 20px;
}

.section-subtitle {
  text-align: center;
  font-size: clamp(1rem, 2vw, 1.2rem);
  color: #666;
  margin-bottom: 60px;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.map-section {
  position: relative;
  margin-bottom: 60px;
}

.map-container {
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.store-info-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  margin-bottom: 80px;
}

.main-store-info h3,
.other-locations h3 {
  font-size: 1.8rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 20px;
}

.store-card {
  background: rgba(255, 255, 255, 0.8);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  padding: 30px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  border: 1px solid rgba(240, 240, 240, 0.5);
  margin-bottom: 30px;
}

.store-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 25px;
  padding-bottom: 15px;
  border-bottom: 1px solid #eee;
}

.store-header h4 {
  font-size: 1.4rem;
  font-weight: 700;
  color: #333;
}

.status {
  padding: 6px 12px;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 600;
}

.status.open {
  background: #e8f5e8;
  color: #2e7d2e;
}

.store-details {
  margin-bottom: 25px;
}

.detail-item {
  display: flex;
  gap: 15px;
  margin-bottom: 20px;
  align-items: flex-start;
}

.icon {
  font-size: 1.2rem;
  width: 30px;
  text-align: center;
  flex-shrink: 0;
}

.detail-item strong {
  display: block;
  color: #333;
  font-weight: 600;
  margin-bottom: 5px;
}

.detail-item p {
  color: #666;
  margin: 0;
  line-height: 1.4;
}

.hours-list {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.hour-item {
  display: flex;
  justify-content: space-between;
  color: #666;
  font-size: 0.9rem;
}

.store-actions {
  display: flex;
  gap: 15px;
}

.store-actions .btn {
  flex: 1;
  padding: 12px 20px;
  text-align: center;
  text-decoration: none;
}

.other-locations h4 {
  font-size: 1.3rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 15px;
}

.location-list {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.location-item {
  padding: 15px;
  background: rgba(248, 249, 250, 0.5);
  backdrop-filter: blur(5px);
  border-radius: 12px;
  border: 1px solid rgba(238, 238, 238, 0.5);
}

.location-item h5 {
  font-weight: 600;
  color: #333;
  margin-bottom: 5px;
}

.location-item p {
  color: #666;
  margin: 0 0 5px 0;
  font-size: 0.9rem;
}

.distance {
  color: #e91e63;
  font-size: 0.8rem;
  font-weight: 500;
}

/* Main Store Additional Content */
.store-features-mini {
  margin-top: 30px;
}

.store-features-mini h4 {
  font-size: 1.2rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 15px;
}

.feature-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 25px;
}

.feature-tag {
  background: rgba(233, 30, 99, 0.1);
  color: #e91e63;
  padding: 6px 12px;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 500;
  border: 1px solid rgba(233, 30, 99, 0.2);
}



.store-features {
  text-align: center;
  
}

.store-features h3 {
  font-size: 2rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 40px;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 30px;
  
}

.feature-item {
  text-align: center;
  padding: 30px 20px;
  background: rgba(248, 249, 250, 0.6);
  backdrop-filter: blur(10px);
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  border-radius: 15px;
  border: 1px solid rgba(240, 240, 240, 0.5);
  transition: transform 0.3s ease;
}

.feature-item:hover {
  transform: translateY(-5px);
}

.feature-icon {
  font-size: 3rem;
  margin-bottom: 15px;
}

.feature-item h4 {
  font-size: 1.3rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 10px;
}

.feature-item p {
  color: #666;
  line-height: 1.5;
}

/* Responsive */
@media (max-width: 768px) {
  .store-info-grid {
    grid-template-columns: 1fr;
    gap: 30px;
  }

  .map-container iframe {
    height: 350px;
  }

  .store-actions {
    flex-direction: column;
  }

  .features-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
  }
}

@media (max-width: 480px) {
  .store-card {
    padding: 20px;
  }

  .map-container iframe {
    height: 300px;
  }

  .features-grid {
    grid-template-columns: 1fr;
  }
}
</style> 