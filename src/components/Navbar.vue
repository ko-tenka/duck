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
  height: 56px;
  background: #fff;
  margin-top: 11px;
}

.navbar-left {
  flex: 0 0 auto;
}

.navbar-logo {
  height: 40px;
  width: auto;
  display: block;
}

.navbar-list {
  display: flex;
  gap: 21px;
  list-style: none;
  margin: 0;
  padding: 0;
  flex: 1 1 0%;
  justify-content: center;
  margin-left: 99px;
}

.navbar-list a {
  text-decoration: none;
  color: rgba(0, 0, 0, 1);
  font-weight: 500;
  transition: color 0.2s;
  position: relative;
  display: flex;
  align-items: center;
  gap: 6px;
  letter-spacing: 0.3px;
}

.navbar-list a img {
  /* width: 16px;
  height: 16px; */
  display: inline-block;
}

.navbar-list a::after {
  content: '';
  display: block;
  width: 100%;
  height: 2px;
  background: rgba(37, 129, 235, 1);
  position: absolute;
  left: 0;
  bottom: -13px;
  opacity: 0;
  transition: opacity 0.2s;
}

.navbar-list a:hover {
  color: rgba(37, 129, 235, 1);
}

.navbar-list a:hover::after {
  opacity: 1;
}

.navbar-actions {
  display: flex;
  align-items: center;
  gap: 8px;
  flex: 0 0 auto;
}

.catalog-arrow {
  margin-left: 1px; /* gap 6px - 5px = 1px */
}

.burger-btn {
  display: none;
  background: none;
  border: none;
  padding: 0;
  margin-left: 16px;
  cursor: pointer;
}

.mobile-menu {
  position: absolute;
  top: 56px;
  left: 0;
  right: 0;
  background: #fff;
  box-shadow: none;
  z-index: 100;
  overflow: hidden;
  max-height: 0;
  opacity: 0;
  transition: max-height 0.8s cubic-bezier(0.4,0,0.2,1), opacity 0.6s;
  pointer-events: none;
  border-radius: 0 0 12px 12px;
}
.mobile-menu--open {
  max-height: 500px;
  opacity: 1;
  pointer-events: auto;
}
.mobile-menu ul {
  list-style: none;
  margin: 0;
  padding: 35px 0 16px 0;
  display: flex;
  flex-direction: column;
  gap: 25px;
  align-items: center;
}
.mobile-menu a {
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-style: normal;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.5%;
  color: rgba(0,0,0,1);
  text-decoration: none;
  position: relative;
  transition: color 0.2s;
}
.mobile-menu a::after {
  content: '';
  display: block;
  width: 100%;
  height: 2px;
  background: rgba(37, 129, 235, 1);
  position: absolute;
  left: 0;
  bottom: -8px;
  opacity: 0;
  transition: opacity 0.2s;
}
.mobile-menu a:hover {
  color: rgba(37, 129, 235, 1);
}
.mobile-menu a:hover::after {
  opacity: 1;
}

.mobile-menu-btn {
  display: none;
}

.close-icon {
  width: 40px;
  height: 40px;
  display: block;
}

.overlay {
  position: fixed;
  top: 56px; /* высота навбара */
  left: 0;
  width: 100vw;
  height: calc(100vh - 56px);
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
    gap: 8px;
    flex-direction: row;
  }
  .burger-btn {
    display: flex;
    align-items: center;
  }
}

@media (max-width: 375px) {
  .navbar {
    margin-top: 0px;
  }
  .navbar-actions {
    gap: 0px;
  }
  .navbar-actions MyButton,
  .navbar-actions .my-button {
    display: none !important;
  }
  .mobile-menu-btn {
    display: flex;
    justify-content: center;
    padding: 10px 0 8px 0;
    padding-bottom: 35px;
  }
/* пупупупу */
}
</style>