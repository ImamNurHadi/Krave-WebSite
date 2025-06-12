<template>
  <header class="header">
    <nav class="nav-container">
      <a href="#" class="logo">
        <img src="/logo-krave.png" alt="Krave Logo" class="logo-img">
        Krave
      </a>
      
      <div class="nav-menu" :class="{ active: isMenuOpen }">
        <ul>
          <li><a href="#home" @click="closeMenu">Home</a></li>
          <li><a href="#products" @click="closeMenu">Menu</a></li>
          <li><a href="#locations" @click="closeMenu">Locations</a></li>
          <li><a href="#catering" @click="closeMenu">Catering</a></li>
          <li><a href="#about" @click="closeMenu">About</a></li>
          <li><a href="#reviews" @click="closeMenu">Reviews</a></li>
        </ul>
      </div>
      
      <div class="nav-actions">
        <a href="#" class="sign-in">Sign in</a>
        <a href="#order" class="btn btn-primary">Order Now</a>
      </div>
      
      <button class="mobile-menu-btn" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
      </button>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'HeaderComponent',
  data() {
    return {
      isMenuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },
    closeMenu() {
      this.isMenuOpen = false
    }
  }
}
</script>

<style scoped>
.header {
  background: #fff;
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  backdrop-filter: blur(10px);
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
}

.logo {
  font-size: 2.5rem;
  font-weight: 800;
  color: #e91e63;
  text-decoration: none;
  letter-spacing: -0.02em;
  display: flex;
  align-items: center;
  gap: 8px;
}

.logo-img {
  width: 40px;
  height: 40px;
  object-fit: contain;
}

.nav-menu ul {
  display: flex;
  list-style: none;
  gap: 40px;
  align-items: center;
}

.nav-menu ul li a {
  text-decoration: none;
  color: #333;
  font-weight: 500;
  font-size: 1rem;
  transition: color 0.3s ease;
}

.nav-menu ul li a:hover {
  color: #e91e63;
}

.nav-actions {
  display: flex;
  gap: 20px;
  align-items: center;
}

.sign-in {
  color: #333;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.sign-in:hover {
  color: #e91e63;
}

.mobile-menu-btn {
  display: none;
  flex-direction: column;
  background: none;
  border: none;
  cursor: pointer;
  padding: 5px;
}

.mobile-menu-btn span {
  width: 25px;
  height: 3px;
  background: #333;
  margin: 3px 0;
  transition: 0.3s;
}

/* Mobile Responsive */
@media (max-width: 768px) {
  .nav-menu {
    position: fixed;
    top: 80px;
    left: -100%;
    width: 100%;
    height: calc(100vh - 80px);
    background: rgba(255, 255, 255, 0.95);
    backdrop-filter: blur(10px);
    transition: left 0.3s ease;
    box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
    z-index: 999;
  }

  .nav-menu.active {
    left: 0;
  }

  .nav-menu ul {
    flex-direction: column;
    padding: 40px;
    gap: 30px;
  }

  .nav-menu ul li a {
    font-size: 1.2rem;
  }

  .mobile-menu-btn {
    display: flex;
  }

  .nav-actions {
    gap: 15px;
  }

  .sign-in {
    display: none;
  }
}
</style> 