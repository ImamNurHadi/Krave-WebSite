<template>
  <section class="products" id="products">
    <div class="container">
      <h2 class="section-title">National Flavors</h2>
      <p class="section-subtitle">Discover our signature collection of handcrafted cookies and desserts</p>
      
      <div class="filter-tabs">
        <button 
          v-for="category in categories" 
          :key="category"
          :class="['filter-btn', { active: activeCategory === category }]"
          @click="filterProducts(category)"
        >
          {{ category }}
        </button>
      </div>
      
      <div class="products-grid">
        <div 
          v-for="product in filteredProducts" 
          :key="product.id"
          class="product-card fade-in-up"
          @click="openModal(product)"
        >
          <div class="product-image-container">
            <img 
              :src="product.image" 
              :alt="product.name" 
              class="product-image"
              @error="handleImageError"
            >
            <div class="product-badge" v-if="product.isNew">NEW</div>
            <div class="product-rating">
              <span class="stars">⭐⭐⭐⭐⭐</span>
              <span class="rating-text">{{ product.rating }}</span>
            </div>
          </div>
          
          <div class="product-info">
            <h3>{{ product.name }}</h3>
            <p class="product-description">{{ product.description }}</p>
            
            <div class="product-details">
              <div class="price">${{ product.price }}</div>
              <div class="calories">{{ product.calories }} cal</div>
            </div>
            
            <div class="product-actions">
              <button class="btn btn-secondary">Learn More</button>
              <button class="btn btn-primary">Order Now</button>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Product Modal -->
    <div class="modal-overlay" v-if="selectedProduct" @click="closeModal">
      <div class="modal" @click.stop>
        <button class="modal-close" @click="closeModal">&times;</button>
        
        <div class="modal-content">
          <div class="modal-image">
            <img :src="selectedProduct.image" :alt="selectedProduct.name">
          </div>
          
          <div class="modal-details">
            <h2>{{ selectedProduct.name }}</h2>
            <div class="modal-rating">
              <span class="stars">⭐⭐⭐⭐⭐</span>
              <span>{{ selectedProduct.rating }} ({{ selectedProduct.reviews }} reviews)</span>
            </div>
            
            <p class="modal-description">{{ selectedProduct.fullDescription }}</p>
            
            <div class="nutritional-info">
              <h4>Nutritional Information</h4>
              <div class="nutrition-grid">
                <div class="nutrition-item">
                  <span class="label">Calories</span>
                  <span class="value">{{ selectedProduct.calories }}</span>
                </div>
                <div class="nutrition-item">
                  <span class="label">Fat</span>
                  <span class="value">{{ selectedProduct.fat }}g</span>
                </div>
                <div class="nutrition-item">
                  <span class="label">Sugar</span>
                  <span class="value">{{ selectedProduct.sugar }}g</span>
                </div>
                <div class="nutrition-item">
                  <span class="label">Protein</span>
                  <span class="value">{{ selectedProduct.protein }}g</span>
                </div>
              </div>
            </div>
            
            <div class="modal-actions">
              <div class="price-section">
                <span class="price">${{ selectedProduct.price }}</span>
                <span class="price-note">per cookie</span>
              </div>
              <button class="btn btn-primary modal-btn">Add to Cart</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProductsSection',
  data() {
    return {
      activeCategory: 'All',
      selectedProduct: null,
      categories: ['All', 'Cookies', 'Brownies', 'Cakes', 'Seasonal'],
      products: [
        {
          id: 1,
          name: "Milk Chocolate Chip Cookie",
          description: "The classic—you can't go wrong. Thick, soft, and packed with milk chocolate chips.",
          fullDescription: "Our signature milk chocolate chip cookie is made with premium Belgian chocolate chips, Madagascar vanilla, and European butter. Each cookie is baked to perfection with a golden exterior and soft, chewy center that melts in your mouth.",
          image: "/picture/6c54f810-416b-4266-a628-fc00b5d4ed49_MilkChocolateChip_FlyingAerial_TECH.png",
          category: 'Cookies',
          price: 4.99,
          calories: 320,
          fat: 16,
          sugar: 24,
          protein: 4,
          rating: 4.8,
          reviews: 1247,
          isNew: false
        },
        {
          id: 2,
          name: "Peanut Butter Cup Brownie",
          description: "A gooey brownie topped with velvety peanut butter mousse, a drizzle of chocolate, and peanut butter cups.",
          fullDescription: "Indulgent fudge brownie layered with creamy peanut butter mousse and topped with mini peanut butter cups. This decadent treat combines rich chocolate with smooth peanut butter for the ultimate dessert experience.",
          image: "/picture/964fefc4-77ce-4f56-bde6-064d181822d4_ChocolatePeanutButterBrownie_LTO_FlyingAerial_TECH.png",
          category: 'Brownies',
          price: 5.99,
          calories: 450,
          fat: 24,
          sugar: 32,
          protein: 8,
          rating: 4.9,
          reviews: 892,
          isNew: true
        },
        {
          id: 3,
          name: "Churro Cake",
          description: "Two layers of cinnamon and sugar-coated cinnamon cake layered with crunchy streusel and creamy cinnamon buttercream.",
          fullDescription: "A celebration of cinnamon sugar goodness with layers of moist cinnamon cake, crunchy cinnamon streusel, and smooth cinnamon buttercream. Topped with a dusting of cinnamon sugar for that authentic churro experience.",
          image: "/picture/3f58c3b5-d52d-4ab1-905d-46f5012650d0_ChurroCakeDessert_FlyingAerial_TECH.png",
          category: 'Cakes',
          price: 6.99,
          calories: 380,
          fat: 18,
          sugar: 28,
          protein: 5,
          rating: 4.7,
          reviews: 654,
          isNew: false
        },
        {
          id: 4,
          name: "Raspberry Lemonade Cookie",
          description: "A lemon cookie smothered with a marbled swirl of lemon and raspberry frostings infused with fresh house-made raspberry jam.",
          fullDescription: "Bright and tangy lemon cookie base topped with a beautiful marbled frosting of lemon and raspberry flavors. Made with real raspberry jam and fresh lemon zest for an authentic summer taste that's both refreshing and indulgent.",
          image: "/picture/8e31c971-09e9-4e08-b1d6-765ed1f9f0dc_RaspberryLemonade_FlyingAerial_TECH.png",
          category: 'Seasonal',
          price: 5.49,
          calories: 290,
          fat: 12,
          sugar: 26,
          protein: 3,
          rating: 4.6,
          reviews: 423,
          isNew: true
        },
        {
          id: 5,
          name: "S'mores Cookie",
          description: "A graham cracker cookie packed with milk chocolate chips then topped with a melty marshmallow, chocolate drizzle, and buttery graham cracker crumbs.",
          fullDescription: "Capture the essence of campfire s'mores in cookie form. Graham cracker cookie base loaded with chocolate chips, topped with toasted marshmallow, rich chocolate drizzle, and crunchy graham cracker pieces.",
          image: "/picture/ce1deb6c-c43d-434f-890a-d5d12d4de95b_Smores_FlyingAerial_TECH.png",
          category: 'Cookies',
          price: 5.99,
          calories: 360,
          fat: 16,
          sugar: 30,
          protein: 4,
          rating: 4.8,
          reviews: 756,
          isNew: false
        },
        {
          id: 6,
          name: "Dirt Cake Cookie",
          description: "A dark chocolate cookie coated in cookies & cream crumbs, swirled with fudge frosting, sprinkled with chocolate streusel, and finished with a gummy worm.",
          fullDescription: "A playful take on the classic dirt cake dessert. Rich chocolate cookie base covered in crushed chocolate cookies, fudge frosting swirls, chocolate streusel, and topped with a gummy worm for that authentic 'dirt' experience.",
          image: "/picture/9c9e2619-037a-47f1-9b64-cb83307d7769_DirtCake_FlyingAerial_TECH.png",
          category: 'Cookies',
          price: 5.49,
          calories: 340,
          fat: 17,
          sugar: 28,
          protein: 4,
          rating: 4.5,
          reviews: 334,
          isNew: false
        },
        {
          id: 7,
          name: "French Toast Cookie",
          description: "A fluffy, buttery cookie topped with cinnamon egg wash, a dollop of buttercream, a sweet syrup drizzle, and a sprinkle of powdered sugar.",
          fullDescription: "Start your morning right with this breakfast-inspired cookie. Soft and fluffy base with cinnamon egg wash glaze, creamy buttercream, maple syrup drizzle, and a dusting of powdered sugar.",
          image: "/picture/46bf1e33-f9bf-40ce-be5e-f02de5d47146_FrenchToast_FlyingAerial_TECH.png",
          category: 'Cookies',
          price: 5.99,
          calories: 310,
          fat: 14,
          sugar: 25,
          protein: 5,
          rating: 4.7,
          reviews: 567,
          isNew: true
        }
      ]
    }
  },
  computed: {
    filteredProducts() {
      if (this.activeCategory === 'All') {
        return this.products
      }
      return this.products.filter(product => product.category === this.activeCategory)
    }
  },
  methods: {
    filterProducts(category) {
      this.activeCategory = category
    },
    openModal(product) {
      this.selectedProduct = product
      document.body.style.overflow = 'hidden'
    },
    closeModal() {
      this.selectedProduct = null
      document.body.style.overflow = 'auto'
    },
    handleImageError(event) {
      event.target.style.background = 'linear-gradient(45deg, #f5f5f5, #eeeeee)'
      event.target.style.display = 'flex'
      event.target.style.alignItems = 'center'
      event.target.style.justifyContent = 'center'
      event.target.innerHTML = '<div style="font-size: 4rem; color: #ddd;">🍪</div>'
    }
  }
}
</script>

<style scoped>
.products {
  padding: 100px 0;
  background: #fff;
  width: 100%;
  position: relative;
  z-index: 1;
  display: block;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  width: 100%;
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
  margin-bottom: 50px;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.filter-tabs {
  display: flex;
  justify-content: center;
  gap: 12px;
  margin-bottom: 60px;
  flex-wrap: wrap;
  padding: 0 20px;
}

.filter-btn {
  padding: 12px 24px;
  border: 2px solid #e0e0e0;
  background: #fff;
  color: #666;
  border-radius: 25px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.3s ease;
  font-size: 0.95rem;
  white-space: nowrap;
}

.filter-btn.active,
.filter-btn:hover {
  border-color: #e91e63;
  background: #e91e63;
  color: #fff;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(233, 30, 99, 0.2);
}

.products-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 24px;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  width: 100%;
}

.product-card {
  background: transparent;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  cursor: pointer;
  position: relative;
  width: 100%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.product-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.12);
  border-color: #e91e63;
}

.product-image-container {
  position: relative;
  height: 220px;
  overflow: hidden;
  background: #f8f9fa;
  flex-shrink: 0;
}

.product-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.product-card:hover .product-image {
  transform: scale(1.05);
}

.product-badge {
  position: absolute;
  top: 12px;
  left: 12px;
  background: #ff4444;
  color: #fff;
  padding: 6px 12px;
  border-radius: 15px;
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.product-rating {
  position: absolute;
  top: 12px;
  right: 12px;
  background: rgba(255, 255, 255, 0.95);
  padding: 6px 12px;
  border-radius: 15px;
  font-size: 0.8rem;
  backdrop-filter: blur(10px);
}

.stars {
  margin-right: 4px;
}

.product-info {
  padding: 20px;
  text-align: center;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  justify-content: space-between;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  margin: 0;
}

.product-info h3 {
  font-size: 1.3rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 10px;
  line-height: 1.3;
}

.product-description {
  color: #666;
  line-height: 1.5;
  margin-bottom: 16px;
  font-size: 0.85rem;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  height: auto;
  min-height: 2.5em;
  flex-grow: 1;
}

.product-details {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
  margin-top: auto;
  padding: 12px;
  background: #f8f9fa;
  border-radius: 12px;
}

.price {
  font-size: 1.3rem;
  font-weight: 700;
  color: #e91e63;
}

.calories {
  color: #666;
  font-size: 0.8rem;
  font-weight: 500;
}

.product-actions {
  display: flex;
  gap: 8px;
  justify-content: center;
  margin-top: auto;
}

.product-actions .btn {
  flex: 1;
  padding: 8px 16px;
  font-size: 0.8rem;
  font-weight: 600;
}

/* Modal Styles */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 2000;
  padding: 40px;
  backdrop-filter: blur(4px);
  overflow: hidden;
}

.modal {
  background: #fff;
  border-radius: 20px;
  max-width: 900px;
  width: 100%;
  max-height: 90vh;
  overflow: visible;
  position: relative;
  animation: modalSlideIn 0.3s ease-out;
}

@keyframes modalSlideIn {
  from {
    opacity: 0;
    transform: scale(0.9) translateY(20px);
  }
  to {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
}

.modal-close {
  position: absolute;
  top: 20px;
  right: 20px;
  background: rgba(255, 255, 255, 0.9);
  border: none;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  font-size: 1.5rem;
  cursor: pointer;
  color: #666;
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
}

.modal-close:hover {
  background: #e91e63;
  color: #fff;
}

.modal-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  padding: 40px;
  position: relative;
  overflow: visible;
}

.modal-image {
  position: relative;
  z-index: 1;
  overflow: visible;
  background: transparent;
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-image img {
  width: 100%;
  height: 350px;
  object-fit: contain;
  border-radius: 20px;
  transform: none;
  box-shadow: none;
  position: relative;
  z-index: 2;
  background: transparent;
}

.modal-details {
  position: relative;
  z-index: 3;
  padding-left: 0px;
}

.modal-details h2 {
  font-size: 1.8rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 15px;
  line-height: 1.3;
}

.modal-rating {
  margin-bottom: 20px;
  color: #666;
  font-size: 0.95rem;
}

.modal-description {
  color: #666;
  line-height: 1.6;
  margin-bottom: 30px;
}

.nutritional-info h4 {
  color: #333;
  margin-bottom: 15px;
  font-weight: 600;
  font-size: 1.1rem;
}

.nutrition-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 8px;
  margin-bottom: 30px;
}

.nutrition-item {
  display: flex;
  justify-content: space-between;
  padding: 12px;
  background: #f8f9fa;
  border-radius: 8px;
  font-size: 0.9rem;
}

.label {
  color: #666;
  font-weight: 500;
}

.value {
  font-weight: 600;
  color: #333;
}

.modal-actions {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 20px;
  border-top: 1px solid #eee;
}

.price-section .price {
  font-size: 1.8rem;
  font-weight: 700;
  color: #e91e63;
}

.price-note {
  color: #666;
  font-size: 0.85rem;
  margin-left: 8px;
}

.modal-btn {
  padding: 15px 30px;
  font-size: 1rem;
  font-weight: 600;
}

/* Responsive */
@media (max-width: 1024px) {
  .products-grid {
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
  }
}

@media (max-width: 768px) {
  .products-grid {
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
    padding: 0 15px;
  }

  .filter-tabs {
    justify-content: flex-start;
    overflow-x: auto;
    padding-bottom: 10px;
    margin-bottom: 40px;
    padding: 0 15px 10px;
  }

  .filter-btn {
    white-space: nowrap;
    font-size: 0.9rem;
    padding: 10px 20px;
  }

  .product-actions {
    flex-direction: column;
    gap: 10px;
  }

  .modal-content {
    grid-template-columns: 1fr;
    gap: 24px;
    padding: 30px 20px;
    overflow: hidden;
  }

  .modal-image {
    overflow: hidden;
  }

  .modal-image img {
    width: 110%;
    height: 280px;
    transform: translateX(-5%) translateY(0);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
    border-radius: 15px;
  }

  .modal-details {
    padding-left: 0;
  }

  .nutrition-grid {
    grid-template-columns: 1fr;
  }

  .modal-actions {
    flex-direction: column;
    gap: 20px;
    align-items: stretch;
  }

  .modal-btn {
    width: 100%;
  }
}

@media (max-width: 480px) {
  .products {
    padding: 60px 0;
  }

  .products-grid {
    grid-template-columns: 1fr;
    gap: 20px;
    padding: 0 10px;
  }

  .product-info {
    padding: 16px;
  }

  .filter-tabs {
    gap: 8px;
    padding: 0 10px 10px;
  }

  .filter-btn {
    padding: 8px 16px;
    font-size: 0.85rem;
  }
}
</style> 