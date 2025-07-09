<template>
    <ul class="nav-list">
      <li><img :src="Arrow" alt="стрелка"><a href="#">Классические</a></li>
      <li><img :src="Arrow" alt="стрелка"><a href="#">Уточки панки</a></li>
      <li><img :src="Arrow" alt="стрелка"><a href="#">Супергерои</a></li>
      <li><img :src="Arrow" alt="стрелка"><a href="#">Милые</a></li>
      <li><img :src="Arrow" alt="стрелка"><a href="#">Для детей</a></li>
      <li><img :src="Arrow" alt="стрелка"><a href="#">Взрослым</a></li>
    </ul>
</template>

<script setup>
import Arrow from '/arrow.svg'
</script>

<style scoped>
.nav-list {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center; /* Центрирует список по горизонтали */
  width: 90vw;
  margin: 0;
  padding: 0 24px;
  list-style: none;
  min-height: 56px;
  margin-top: 597px;
  margin-left: 25px;
}
.nav-list li {
  display: flex;
  align-items: center;
  margin-right: 44px;
  gap: 16px; /* или 4px, подберите визуально */
}
.nav-list li:last-child {
  margin-right: 0;
}
.nav-list a {
  color: rgba(31, 41, 55, 1);
  text-decoration: none;
  font-weight: 500;
  letter-spacing: 0.5px;
  font-size: 16px;
}
.nav-list a:hover {
  color: rgba(37, 129, 235, 1); /* насыщенный синий */
}
.nav-list img {
  width: 32px;
  height: 32px;
  display: inline-block;
  margin-right: -8px; /* или 4px */
}

@media (min-width: 1281px) {
.nav-list {
    position: relative;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 660px auto;
}
}

@media (max-width: 960px) {
  .nav-list {
    min-height: 48px;
    font-size: 14px;
    margin-top: 8px;
    margin-left: -10px;
    width: 97%;
  }
  .nav-list li {
    margin-right: 24px;
    gap: 16px;
  }
}

@media (max-width: 375px) {
  .nav-list {
    flex-direction: column;
    align-items: stretch;
    min-height: 36px;
    margin-top: -94px;
    padding: 0 0px;
    width: 40vw;
    margin-left: 0px;
  }
  .nav-list li {
    margin: 0 0 12px 0;
    gap: 16px;
    font-size: 12px;
    width: 100%;
    justify-content: flex-start;
  }
  .nav-list li:last-child {
    margin-bottom: 0;
  }
  .nav-list img {
    width: 32px;
    height: 32px;
  }
}

</style>