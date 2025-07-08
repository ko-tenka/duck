<template>
  <nav class="navbar">
    <div class="navbar-left">
      <img :src="Logo" alt="логотип" class="navbar-logo">
    </div>
    <ul class="navbar-list">
      <li><a href="#">Главная</a></li>
      <li><a href="#">Каталог <img :src="Arrow" alt="стрелка" class="catalog-arrow"></a></li>
      <li><a href="#">Блог</a></li>
      <li><a href="#">Отзывы</a></li>
      <li><a href="#">Контакты</a></li>
    </ul>
    <div class="navbar-actions">
      <UiIcon name="basket" />
      <MyButton color="orange">Заказать обратный звонок</MyButton>
    </div>
  </nav>
</template>

<script setup>
import Logo from '/Logo.svg'
import Arrow from '/arrow_down.svg'
import UiIcon from '../ui/Icon.vue';
import MyButton from '../ui/MyButton.vue';
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
</style>