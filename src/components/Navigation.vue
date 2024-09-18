<template>
  <nav>
    <div class="container">
      <h1 class="logo">Przemek Pastuszka</h1>
      <ul v-bind:class="{ show: isMenuVisible }" id="nav-list">
        <li><a href="#about" @click="toggleMenu">About</a></li>
        <li><a href="#experience" @click="toggleMenu">Experience</a></li>
        <li><a href="#education" @click="toggleMenu">Education</a></li>
      </ul>
      <span class="mobile-nav-toggle" @click="toggleMenu">&#9776;</span>
    </div>
  </nav>
</template>

<script lang="ts">
export default {
  data() {
    return {isMenuVisible: false}
  },
  methods: {
    toggleMenu() {
      this.isMenuVisible = !this.isMenuVisible;
    },
  }
}
</script>

<style scoped>
nav {
  background-color: #ffffff;
  padding: 20px 0;
  position: sticky;
  top: 0;
  width: 100%;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  z-index: 999;
}

nav .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 20px;
}

nav ul li {
  position: relative;
}

nav ul li:hover {
  background-color: #f4f4f9;
}

nav ul li a {
  text-decoration: none;
  font-size: 1.1rem;
  color: #333;
  text-transform: uppercase;
  font-weight: 500;
  transition: color 0.3s ease;
}

/* Mobile Navigation Toggle (Hamburger Menu) */
.mobile-nav-toggle {
  display: none;
  font-size: 1.8rem;
  cursor: pointer;
}

@media (max-width: 768px) {
  nav ul {
    display: none;
    flex-direction: column;
    position: absolute;
    top: 80px;
    left: 0;
    width: 100%;
    background-color: #fff;
    text-align: center;
  }

  nav ul.show {
    display: flex;
  }

  .mobile-nav-toggle {
    display: block;
    color: #333;
  }
}
</style>