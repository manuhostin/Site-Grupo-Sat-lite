<script setup>
import { ref } from 'vue';

const menuOpen = ref(false);
</script>

<template>
  <nav class="navbar">
    <div class="container">
      <a href="#home" class="logo">
        <img src="@/assets/logo.png" alt="Logo" class="logo-img" />
      </a>
      <button @click="menuOpen = !menuOpen" class="menu-button">
        <svg xmlns="http://www.w3.org/2000/svg" class="icon" viewBox="0 0 24 24" stroke="currentColor" fill="none">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
      </button>
      <ul :class="{'open': menuOpen}" class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">Sobre</a></li>
        <li><a href="#services">Serviços</a></li>
        <li><a href="#contact">Contato</a></li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
.navbar {
  background: linear-gradient(135deg, #000000, #000000);
  color: rgb(255, 102, 0);
  padding: 1rem 2rem;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  display: flex;
  justify-content: center;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  transition: background 0.3s ease-in-out;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  width: 100%;
}

.logo-img {
  height: 50px;
  transition: transform 0.3s ease-in-out;
}

.logo-img:hover {
  transform: scale(1.1);
}

.menu-button {
  background: none;
  border: none;
  cursor: pointer;
  color:rgb(255, 102, 0);
  display: none;
}

.icon {
  width: 30px;
  height: 30px;
}

.nav-links {
  font-family: "Poppins", serif;
  list-style: none;
  display: flex;
  gap: 2rem;
}

.nav-links li a {
  text-decoration: none;
  color: rgb(255, 102, 0);
  font-weight: bold;
  font-size: 1.1rem;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  position: relative;
  transition: color 0.3s ease-in-out;
}

.nav-links li a::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 50%;
  width: 0;
  height: 3px;
  background-color: rgb(255, 102, 0);
  transition: width 0.3s ease-in-out, left 0.3s ease-in-out;
}

.nav-links li a:hover {
  color: #ffffff;
}

.nav-links li a:hover::after {
  width: 100%;
  left: 0;
}

@media (max-width: 768px) {
  .menu-button {
    display: block;
  }

  .nav-links {
    display: none;
    flex-direction: column;
    position: absolute;
    top: 70px;
    left: 0;
    width: 100%;
    background: linear-gradient(135deg, #ff6600, #cc5500);
    padding: 1rem 0;
    text-align: center;
  }

  .nav-links.open {
    display: flex;
  }
}
</style>
