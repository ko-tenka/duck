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
  justify-content: center; 
  width: 90vw;
  margin: 0;
  padding: 0 1.5rem;
  list-style: none;
  min-height: 3.5rem;
  margin-top: 47.2vw;
  margin-left: 1.8rem;
  position: relative;
  z-index: var(--z-content);
}
.nav-list li {
  display: flex;
  align-items: center;
  margin-right: 3.2rem; /* увеличено расстояние между элементами */
  gap: 4.4rem; /* стрелка ближе к тексту */
}
.nav-list li:last-child {
  margin-right: 0;
}
.nav-list a {
  color: var(--color-text-main);
  text-decoration: none;
  font-weight: 500;
  letter-spacing: 0.06rem;
  font-size: 1.1rem;
}
.nav-list a:hover {
  color: var(--color-list); 
}
.nav-list img {
  width: 2rem;
  height: 2rem;
  display: inline-block;
  margin-right: -4vw;
}

@media (min-width: 1281px) {
.nav-list {
    margin-top: -8vw;
    
}
.nav-list a {
  z-index: 1000;
  pointer-events: auto;
}
}

@media (max-width: 960px) {
  .nav-list {
    /* min-height: 3rem; */
    font-size: 0.88rem;
    margin-top: -4.5rem;
    margin-left: -0.6rem;
    width: 97%;
  }
  .nav-list li {
    margin-right: 1.8rem;
    gap: 3.5rem;
  }
}

@media (max-width: 375px) {
  .nav-list {
    flex-direction: column;
    align-items: stretch;
    min-height: 2.25rem;
    margin-top: -7.3rem;
    padding: 0;
    width: 80vw;
    margin-left: 0.1rem;
  }
  .nav-list li {
    margin: 0 0 1.15rem 0;
    gap: 1.8rem;
    font-size: 0.75rem;
    width: 100%;
    justify-content: flex-start;
  }
  .nav-list img {
    width: 2rem;
    height: 2rem;
  }
}
</style>