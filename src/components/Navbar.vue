<template>
  <nav class="navbar">
    <div class="navbar-left">
      <img :src="Logo" alt="логотип" class="navbar-logo">
    </div>
    <ul class="navbar-list" v-if="!isMobileMenuOpen">
      <li><a href="#">Главная</a></li>
      <li><a href="#">Каталог <img :src="Arrow" alt="стрелка" class="catalog-arrow"></a></li>
      <li><a href="#">Блог</a></li>
      <li><a href="#">Отзывы</a></li>
      <li><a href="#">Контакты</a></li>
    </ul>
    <div class="navbar-actions">
      <UiIcon name="basket" v-if="!isMobileMenuOpen" />
      <MyButton color="orange" v-if="!isMobileButtonInMenu && (!isMobileMenuOpen || !isMobile960)" @click="showPopup = true">Заказать обратный звонок</MyButton>
      <button class="burger-btn" @click="toggleMobileMenu" v-if="isMobile">
        <UiIcon v-if="!isMobileMenuOpen" name="nav" />
        <img v-else :src="Close" alt="Закрыть" class="close-icon" />
      </button>
    </div>
    <div v-if="isMobileMenuOpen" class="overlay" @click="toggleMobileMenu"></div>
    <div :class="['mobile-menu', { 'mobile-menu--open': isMobileMenuOpen }]">
      <ul>
        <li><a href="#">Главная</a></li>
        <li><a href="#">Каталог</a></li>
        <li><a href="#">Блог</a></li>
        <li><a href="#">Отзывы</a></li>
        <li><a href="#">Контакты</a></li>
      </ul>
      <div class="mobile-menu-btn" v-if="isMobileButtonInMenu">
        <MyButton color="orange" @click="showPopup = true">Заказать обратный звонок</MyButton>
      </div>
    </div>
    <Form v-if="showPopup" @close="showPopup = false" />
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import Logo from '/Logo.svg'
import Arrow from '/arrow_down.svg'
import UiIcon from '../ui/Icon.vue'
import MyButton from '../ui/MyButton.vue'
import Form from './Form.vue'
import Close from '/close.svg'

const isMobile = ref(false)
const isMobileMenuOpen = ref(false)
const isMobileButtonInMenu = ref(false)
const isMobile960 = ref(false)
const showPopup = ref(false)

function checkMobile() {
  isMobile.value = window.innerWidth <= 980
  isMobile960.value = window.innerWidth <= 960
  isMobileButtonInMenu.value = window.innerWidth <= 375
  if (!isMobile.value) isMobileMenuOpen.value = false
}

function toggleMobileMenu() {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

onMounted(() => {
  checkMobile()
  window.addEventListener('resize', checkMobile)
})
onUnmounted(() => {
  window.removeEventListener('resize', checkMobile)
})
</script>

<style scoped>
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 3.5rem;
  background: var(--color-bg);
  margin-top: 0.7rem;
}

.navbar-left {
  flex: 0 0 auto;
}

.navbar-logo {
  height: 2.9rem;
  width: auto;
  display: block;
}

.navbar-list {
  display: flex;
  gap: 1.5rem;
  list-style: none;
  margin: 0;
  padding: 0;
  flex: 1 1 0%;
  justify-content: center;
  margin-left: 6.8rem;
}

.navbar-list a {
  text-decoration: none;
  color: var(--color-black);
  font-weight: 500;
  transition: color 0.2s;
  position: relative;
  display: flex;
  align-items: center;
  gap: 0.38rem;
  letter-spacing: 0.3px;
  font-size: 1rem;
}

.navbar-list a img {
  display: inline-block;
}

.navbar-list a::after {
  content: '';
  display: block;
  width: 100%;
  height: 0.13rem;
  background: var(--color-list);
  position: absolute;
  left: 0;
  bottom: -0.8rem;
  opacity: 0;
  transition: opacity 0.2s;
}

.navbar-list a:hover {
  color: var(--color-list);
}

.navbar-list a:hover::after {
  opacity: 1;
}

.navbar-actions {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  flex: 0 0 auto;
}

.catalog-arrow {
  margin-left: 0.06rem;
}

.burger-btn {
  display: none;
  background: none;
  border: none;
  padding: 0;
  margin-left: 1rem;
  cursor: pointer;
}

.mobile-menu {
  position: absolute;
  top: 3.5rem;
  left: 0;
  right: 0;
  background: var(--color-bg);
  box-shadow: none;
  z-index: 100;
  overflow: hidden;
  max-height: 0;
  opacity: 0;
  transition: max-height 0.8s cubic-bezier(0.4,0,0.2,1), opacity 0.6s;
  pointer-events: none;
  border-radius: 0 0 0.75rem 0.75rem;
}
.mobile-menu--open {
  max-height: 31.25rem;
  opacity: 1;
  pointer-events: auto;
}
.mobile-menu ul {
  list-style: none;
  margin: 0;
  padding: 2.2rem 0 1rem 0;
  display: flex;
  flex-direction: column;
  gap: 1.56rem;
  align-items: center;
}
.mobile-menu a {
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-style: normal;
  font-size: 0.88rem;
  line-height: 1.25rem;
  letter-spacing: 0.5%;
  color: var(--color-black);
  text-decoration: none;
  position: relative;
  transition: color 0.2s;
}
.mobile-menu a::after {
  content: '';
  display: block;
  width: 100%;
  height: 0.13rem;
  background: var(--color-list);
  position: absolute;
  left: 0;
  bottom: -0.5rem;
  opacity: 0;
  transition: opacity 0.2s;
}
.mobile-menu a:hover {
  color: var(--color-list);
}
.mobile-menu a:hover::after {
  opacity: 1;
}

.mobile-menu-btn {
  display: none;
}

.close-icon {
  width: 2.5rem;
  height: 2.5rem;
  display: block;
}

.overlay {
  position: fixed;
  top: 3.5rem;
  left: 0;
  width: 100vw;
  height: calc(100vh - 3.5rem);
  background: rgba(0,0,0,0.45);
  z-index: 99;
  transition: opacity 0.3s;
  pointer-events: auto;
}

@media (max-width: 960px) {
  .navbar-list {
    display: none !important;
  }
  .navbar-actions {
    gap: 0.5rem;
    flex-direction: row;
  }
  .burger-btn {
    display: flex;
    align-items: center;
  }
}

@media (max-width: 375px) {
  .navbar {
    margin-top: 0;
  }
  .navbar-actions {
    gap: 0;
  }
  .navbar-actions MyButton,
  .navbar-actions .my-button {
    display: none !important;
  }
  .mobile-menu-btn {
    display: flex;
    justify-content: center;
    padding: 0.63rem 0 0.5rem 0;
    padding-bottom: 2.2rem;
  }
}
</style>