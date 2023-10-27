<script setup>
import { ref } from "vue";

const mobileMenuOpen = ref(false);

const toggleMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value;
};
</script>

<template>
  <header class="bg-gray-200">
    <div v-show="!mobileMenuOpen" class="flex items-center py-4 px-6">
      <div class="mr-16">
        <a class="text-gray-800 font-bold" href="#">
          <i class="fa-solid fa-code mr-2"></i>
          <span class="text-green-500">Lfernando316</span>
        </a>
      </div>
      <div class="hidden md:flex md:items-center md:justify-center">
        <nav id="menu" class="">
          <a
            class="mx-6 text-gray-800 hover:text-green-500 hvr-underline-from-left"
            href="#home"
            >Home</a
          >
          <a
            class="mx-6 text-gray-800 hover:text-green-500 hvr-underline-from-left"
            href="#about"
            >Sobre mí</a
          >
          <a
            class="mx-6 text-gray-800 hover:text-green-500 hvr-underline-from-left"
            href="#habilities"
            >Habilidades</a
          >
          <a
            class="mx-6 text-gray-800 hover:text-green-500 hvr-underline-from-left"
            href="#portfolio"
            >Portafolio</a
          >
          <a
            class="mx-6 text-gray-800 hover:text-green-500 hvr-underline-from-left"
            href="#contact"
            >Contacto</a
          >
        </nav>
      </div>
      <!-- <div class="md:hidden">
        <i id="btnOpen" class=" "></i>
      </div> -->
      <div class="md:hidden ml-auto">
        <button
          @click="toggleMenu"
          class="text-gray-800 hover:text-green-500 focus:outline-none"
        >
          <i v-if="!mobileMenuOpen" class="fa-solid fa-bars text-xl"></i>
        </button>
      </div>
    </div>
    <div
      v-if="mobileMenuOpen"
      class="md:hidden flex flex-col items-center py-4 px-6"
    >
      <!-- Opciones de menú para dispositivos móviles -->
      <button
        @click="toggleMenu"
        class="text-gray-800 hover:text-green-500 focus:outline-none ml-auto"
      >
        <i v-if="mobileMenuOpen" class="fa-solid fa-xmark fa-spin"></i>
      </button>
      <a class="block text-gray-800 hover:text-green-500" href="#home">Home</a>
      <a class="block text-gray-800 hover:text-green-500" href="#about"
        >Sobre mí</a
      >
      <a class="block text-gray-800 hover:text-green-500" href="#habilities"
        >Habilidades</a
      >
      <a class="block text-gray-800 hover:text-green-500" href="#portfolio"
        >Portafolio</a
      >
      <a class="block text-gray-800 hover:text-green-500" href="#contact"
        >Contacto</a
      >
    </div>
  </header>
</template>

<style>
/* .navbar {
  position: fixed;
  top: 0;
  width: 100%;
  height: 80px;
  background-color: #181818;
  box-shadow: 0px 0px 15px -12px #e4ee89;
  z-index: 999;
}

.navbar__container {
  position: relative;
  display: flex;
  align-items: center;
  width: 100%;
  height: inherit;
  justify-content: space-between;
  max-width: 1320px;
  margin: 0 auto;
}

.navbar__logo {
  padding-left: 0.5rem;
} */

/* .navbar__link {
  display: flex;
  align-items: center;
  gap: 0.25rem;
  text-decoration: none;
  color: #909096;
}

.navbar__link:hover {
  color: #08fdd8;
}

.navbar__icon {
  font-size: 1.2rem;
}

.navbar__name {
  color: #08fdd8;
}

.navbar__menu {
  width: 100%;
  background-color: #181818;
}

.navbar__list {
  display: flex;
  gap: 0.5rem;
  font-size: 1rem;
  font-weight: 700;
} */

.hvr-underline-from-left {
  display: inline-block;
  vertical-align: middle;
  -webkit-transform: perspective(1px) translateZ(0);
  transform: perspective(1px) translateZ(0);
  box-shadow: 0 0 1px rgba(0, 0, 0, 0);
  position: relative;
  overflow: hidden;
}
.hvr-underline-from-left:before {
  content: "";
  position: absolute;
  z-index: -1;
  left: 0;
  right: 100%;
  bottom: 0;
  background: linear-gradient(90deg, #e4ee89, #fd2155);
  height: 4px;
  -webkit-transition-property: right;
  transition-property: right;
  -webkit-transition-duration: 0.3s;
  transition-duration: 0.3s;
  -webkit-transition-timing-function: ease-out;
  transition-timing-function: ease-out;
}
.hvr-underline-from-left:hover:before,
.hvr-underline-from-left:focus:before,
.hvr-underline-from-left:active:before {
  right: 0;
}

.navbar__button {
  padding-right: 0.5rem;
}

.btn--close,
.btn--open {
  cursor: pointer;
  color: #08fdd8;
  font-size: 30px;
}

/* hasta los 500, 0 - 500 */
@media (max-width: 400px) {
  .navbar__menu {
    position: absolute;
    top: -400%;
    width: 100%;
    background-color: #181818;
    border-radius: 0 0 20px 20px;
    box-shadow: 0px 0px 15px -3px #00000042;
    transition: all 0.3s ease;
  }

  .navbar__menu.active {
    top: 0;
  }

  .navbar__list {
    margin: 2rem 0 1.5rem;
    flex-direction: column;
    align-items: center;
  }

  .btn--close {
    color: #aaa;
    position: absolute;
    top: 8px;
    right: 8px;
  }
}

.wrapper {
  margin-top: 40px;
}

/* désde 500px, 500 ... */
@media (min-width: 400px) {
  .btn--close {
    display: none;
  }

  .navbar__list {
    justify-content: center;
    align-items: center;
    gap: 3rem;
  }

  .navbar__button {
    display: none;
  }
}
</style>
