<template>
  <section class="reviews" id="reviews">
    <div class="container">
      <h2 class="section-title">What Our Customers Say</h2>
      <p class="section-subtitle">Over 500,000 happy customers can't be wrong!</p>
      
      <div class="reviews-stats">
        <div class="stat">
          <h3>4.8★</h3>
          <p>Average Rating</p>
        </div>
        <div class="stat">
          <h3>50K+</h3>
          <p>Reviews</p>
        </div>
        <div class="stat">
          <h3>98%</h3>
          <p>Would Recommend</p>
        </div>
      </div>
      
      <!-- Horizontal Reviews Slider -->
      <div class="reviews-slider-container">
        <div class="reviews-slider" ref="reviewsSlider">
          <div 
            v-for="review in reviews" 
            :key="review.id"
            class="review-card"
          >
            <div class="review-header">
              <div class="reviewer-info">
                <div class="avatar">
                  <img :src="review.avatar" :alt="review.name">
                </div>
                <div class="reviewer-details">
                  <h4>{{ review.name }}</h4>
                  <p class="review-date">{{ review.date }}</p>
                </div>
              </div>
              <div class="rating">
                <span v-for="n in 5" :key="n" class="star" :class="{ filled: n <= review.rating }">★</span>
              </div>
            </div>
            
            <div class="review-content">
              <p>{{ review.comment }}</p>
              <div class="review-product" v-if="review.product">
                <span class="product-tag">{{ review.product }}</span>
              </div>
            </div>
            
            <div class="review-actions">
              <button class="helpful-btn" @click="markHelpful(review.id)">
                👍 Helpful ({{ review.helpful }})
              </button>
              <div class="social-proof">
                <span class="verified">✓ Verified</span>
              </div>
            </div>
          </div>
        </div>
        
        <!-- Navigation Arrows -->
        <button class="slider-nav prev" @click="slideLeft">‹</button>
        <button class="slider-nav next" @click="slideRight">›</button>
      </div>
      
      <div class="leave-review">
        <h3>Share Your Experience</h3>
        <p>We'd love to hear about your Krave experience!</p>
        <button class="btn btn-primary" @click="openReviewForm">Write a Review</button>
      </div>
    </div>
    
    <!-- Social Media Reviews -->
    <div class="social-reviews">
      <div class="container">
        <h3>Follow Us for More Sweet Moments</h3>
        <div class="social-grid">
          <div 
            v-for="post in socialPosts" 
            :key="post.id"
            class="social-post"
          >
            <img :src="post.image" :alt="post.description">
            <div class="social-overlay">
              <div class="social-info">
                <span class="platform">{{ post.platform }}</span>
                <p>{{ post.description }}</p>
                <div class="social-stats">
                  <span>❤️ {{ post.likes }}</span>
                  <span>💬 {{ post.comments }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ReviewsSection',
  data() {
    return {
      currentSlide: 0,
      reviews: [
        {
          id: 1,
          name: "Sarah Johnson",
          avatar: "https://images.unsplash.com/photo-1494790108755-2616b332c2c2?w=100&h=100&fit=crop&crop=face",
          rating: 5,
          date: "2 days ago",
          comment: "Absolutely incredible! The Milk Chocolate Chip cookies are perfection. Soft, chewy, and loaded with chocolate. Will definitely be ordering again!",
          product: "Milk Chocolate Chip Cookie",
          helpful: 24,
          verified: true
        },
        {
          id: 2,
          name: "Mike Chen",
          avatar: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=100&h=100&fit=crop&crop=face",
          rating: 5,
          date: "1 week ago",
          comment: "The S'mores cookie transported me back to childhood campfires. The marshmallow topping is perfectly toasted and the graham cracker crumbs add the perfect crunch!",
          product: "S'mores Cookie",
          helpful: 18,
          verified: true
        },
        {
          id: 3,
          name: "Emily Rodriguez",
          avatar: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=100&h=100&fit=crop&crop=face",
          rating: 4,
          date: "3 days ago",
          comment: "Love the variety! Tried the Churro Cake and it was amazing. The cinnamon flavor is spot on. Only wish they were a bit bigger for the price.",
          product: "Churro Cake",
          helpful: 12,
          verified: true
        },
        {
          id: 4,
          name: "David Kim",
          avatar: "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?w=100&h=100&fit=crop&crop=face",
          rating: 5,
          date: "5 days ago",
          comment: "The Peanut Butter Cup Brownie is a game changer! Rich, fudgy, and the peanut butter mousse is heavenly. Best dessert I've had in years!",
          product: "Peanut Butter Cup Brownie",
          helpful: 31,
          verified: true
        },
        {
          id: 5,
          name: "Lisa Thompson",
          avatar: "https://images.unsplash.com/photo-1544725176-7c40e5a71c5e?w=100&h=100&fit=crop&crop=face",
          rating: 5,
          date: "1 week ago",
          comment: "Perfect for parties! Ordered a dozen mixed cookies and everyone was impressed. The French Toast cookie was unexpectedly delicious!",
          product: "Mixed Dozen",
          helpful: 15,
          verified: true
        },
        {
          id: 6,
          name: "James Wilson",
          avatar: "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=100&h=100&fit=crop&crop=face",
          rating: 4,
          date: "4 days ago",
          comment: "Great quality ingredients and beautiful presentation. The Raspberry Lemonade cookie is refreshing and not too sweet. Will order again!",
          product: "Raspberry Lemonade Cookie",
          helpful: 9,
          verified: true
        }
      ],
      socialPosts: [
        {
          id: 1,
          platform: "Instagram",
          image: "/6c54f810-416b-4266-a628-fc00b5d4ed49_MilkChocolateChip_FlyingAerial_TECH.png",
          description: "Classic comfort in every bite! 🍪✨",
          likes: 1250,
          comments: 89
        },
        {
          id: 2,
          platform: "TikTok",
          image: "/ce1deb6c-c43d-434f-890a-d5d12d4de95b_Smores_FlyingAerial_TECH.png",
          description: "S'mores cookie = childhood dreams ✨🔥",
          likes: 2340,
          comments: 156
        },
        {
          id: 3,
          platform: "Instagram",
          image: "/46bf1e33-f9bf-40ce-be5e-f02de5d47146_FrenchToast_FlyingAerial_TECH.png",
          description: "Breakfast cookie anyone? 🥞🍪",
          likes: 890,
          comments: 67
        },
        {
          id: 4,
          platform: "Twitter",
          image: "/8e31c971-09e9-4e08-b1d6-765ed1f9f0dc_RaspberryLemonade_FlyingAerial_TECH.png",
          description: "Summer vibes in cookie form! 🍋🫐",
          likes: 674,
          comments: 43
        }
      ]
    }
  },
  methods: {
    slideLeft() {
      const slider = this.$refs.reviewsSlider
      slider.scrollBy({ left: -300, behavior: 'smooth' })
    },
    slideRight() {
      const slider = this.$refs.reviewsSlider
      slider.scrollBy({ left: 300, behavior: 'smooth' })
    },
    markHelpful(reviewId) {
      const review = this.reviews.find(r => r.id === reviewId)
      if (review) {
        review.helpful++
      }
    },
    openReviewForm() {
      // Placeholder for review form modal
      alert('Review form would open here!')
    }
  }
}
</script>

<style scoped>
.reviews {
  padding: 100px 0;
  background: #f8f9fa;
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

.reviews-stats {
  display: flex;
  justify-content: center;
  gap: 80px;
  margin-bottom: 60px;
}

.stat {
  text-align: center;
  padding: 20px;
  background: rgba(255, 255, 255, 0.8);
  border-radius: 15px;
  backdrop-filter: blur(10px);
  min-width: 120px;
}

.stat h3 {
  font-size: clamp(2rem, 3vw, 2.5rem);
  font-weight: 800;
  color: #e91e63;
  margin-bottom: 8px;
  line-height: 1;
}

.stat p {
  color: #666;
  font-weight: 500;
  font-size: 0.95rem;
  margin: 0;
}

/* Horizontal Reviews Slider */
.reviews-slider-container {
  position: relative;
  margin-bottom: 60px;
}

.reviews-slider {
  display: flex;
  gap: 24px;
  overflow-x: auto;
  scroll-behavior: smooth;
  padding: 20px 0;
  scrollbar-width: none;
  -ms-overflow-style: none;
}

.reviews-slider::-webkit-scrollbar {
  display: none;
}

.review-card {
  background: #fff;
  padding: 24px;
  border-radius: 16px;
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.06);
  border: 1px solid #f0f0f0;
  min-width: 350px;
  max-width: 350px;
  flex-shrink: 0;
  transition: all 0.3s ease;
}

.review-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.1);
  border-color: #e91e63;
}

.review-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 16px;
}

.reviewer-info {
  display: flex;
  gap: 12px;
  align-items: center;
}

.avatar {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  overflow: hidden;
  border: 2px solid #e91e63;
  flex-shrink: 0;
}

.avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.reviewer-details h4 {
  font-weight: 600;
  color: #333;
  margin-bottom: 2px;
  font-size: 0.95rem;
}

.review-date {
  color: #888;
  font-size: 0.8rem;
  font-weight: 400;
}

.rating {
  display: flex;
  gap: 1px;
  align-items: center;
}

.star {
  color: #ddd;
  font-size: 1.1rem;
  transition: color 0.2s ease;
}

.star.filled {
  color: #ffd700;
}

.review-content p {
  color: #555;
  line-height: 1.6;
  margin-bottom: 16px;
  font-size: 0.9rem;
}

.product-tag {
  background: #e91e63;
  color: #fff;
  padding: 4px 12px;
  border-radius: 12px;
  font-size: 0.75rem;
  font-weight: 500;
  display: inline-block;
}

.review-actions {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 16px;
  padding-top: 16px;
  border-top: 1px solid #f0f0f0;
}

.helpful-btn {
  background: #f8f9fa;
  border: 1px solid #e0e0e0;
  padding: 6px 12px;
  border-radius: 16px;
  color: #666;
  cursor: pointer;
  transition: all 0.3s ease;
  font-size: 0.8rem;
  font-weight: 500;
}

.helpful-btn:hover {
  border-color: #e91e63;
  color: #e91e63;
  background: #fce4ec;
}

.verified {
  color: #28a745;
  font-size: 0.8rem;
  font-weight: 500;
  display: flex;
  align-items: center;
  gap: 4px;
}

/* Slider Navigation */
.slider-nav {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: #fff;
  border: 2px solid #e91e63;
  color: #e91e63;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  font-size: 1.5rem;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.slider-nav:hover {
  background: #e91e63;
  color: #fff;
  transform: translateY(-50%) scale(1.1);
}

.slider-nav.prev {
  left: -20px;
}

.slider-nav.next {
  right: -20px;
}

.leave-review {
  text-align: center;
  background: #fff;
  padding: 40px;
  border-radius: 20px;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.08);
  border: 1px solid #f0f0f0;
  max-width: 500px;
  margin: 0 auto 80px;
}

.leave-review h3 {
  font-size: 1.6rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 12px;
}

.leave-review p {
  color: #666;
  margin-bottom: 24px;
  font-size: 0.95rem;
}

.social-reviews {
  padding: 80px 0;
  background: #fff;
}

.social-reviews h3 {
  text-align: center;
  font-size: clamp(1.6rem, 3vw, 2rem);
  font-weight: 700;
  color: #333;
  margin-bottom: 40px;
}

.social-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 20px;
}

.social-post {
  position: relative;
  border-radius: 16px;
  overflow: hidden;
  cursor: pointer;
  transition: all 0.3s ease;
  aspect-ratio: 1;
}

.social-post:hover {
  transform: scale(1.02);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
}

.social-post img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.social-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(transparent, rgba(0, 0, 0, 0.85));
  padding: 24px 16px 16px;
  color: #fff;
}

.platform {
  background: #e91e63;
  padding: 4px 8px;
  border-radius: 8px;
  font-size: 0.7rem;
  font-weight: 600;
  margin-bottom: 8px;
  display: inline-block;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.social-overlay p {
  margin-bottom: 8px;
  font-size: 0.85rem;
  line-height: 1.4;
  font-weight: 500;
}

.social-stats {
  display: flex;
  gap: 12px;
  font-size: 0.75rem;
  font-weight: 500;
}

/* Responsive */
@media (max-width: 768px) {
  .reviews-stats {
    flex-direction: column;
    gap: 20px;
    align-items: center;
  }

  .stat {
    min-width: auto;
    width: 100%;
    max-width: 200px;
  }

  .review-card {
    min-width: 280px;
    max-width: 280px;
  }

  .slider-nav {
    display: none;
  }

  .social-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 16px;
  }

  .leave-review {
    padding: 30px 20px;
  }
}

@media (max-width: 480px) {
  .social-grid {
    grid-template-columns: 1fr;
  }

  .reviews-stats {
    gap: 16px;
  }

  .review-card {
    min-width: 260px;
    max-width: 260px;
    padding: 20px;
  }

  .reviewer-info {
    gap: 10px;
  }

  .avatar {
    width: 40px;
    height: 40px;
  }
}
</style> 