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
  margin-top: 37vw;
  margin-left: 1.6rem;
}
.nav-list li {
  display: flex;
  align-items: center;
  margin-right: 2.75rem;
  gap: 1rem; 
}
.nav-list li:last-child {
  margin-right: 0;
}
.nav-list a {
  color: var(--color-text-main);
  text-decoration: none;
  font-weight: 500;
  letter-spacing: 0.03rem;
  font-size: 1rem;
}
.nav-list a:hover {
  color: var(--color-list); 
}
.nav-list img {
  width: 2rem;
  height: 2rem;
  display: inline-block;
  margin-right: -0.5rem;
}

@media (min-width: 1281px) {
.nav-list {
    position: relative;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 41vw auto;
}
}

@media (max-width: 960px) {
  .nav-list {
    min-height: 3rem;
    font-size: 0.88rem;
    margin-top: 0.5rem;
    margin-left: -0.6rem;
    width: 97%;
  }
  .nav-list li {
    margin-right: 1.5rem;
    gap: 1rem;
  }
}

@media (max-width: 375px) {
  .nav-list {
    flex-direction: column;
    align-items: stretch;
    min-height: 2.25rem;
    margin-top: -6rem;
    padding: 0;
    width: 80vw;
    margin-left: 0;
  }
  .nav-list li {
    margin: 0 0 0.75rem 0;
    gap: 1rem;
    font-size: 0.75rem;
    width: 100%;
    justify-content: flex-start;
  }
  .nav-list li:last-child {
    margin-bottom: 0;
  }
  .nav-list img {
    width: 2rem;
    height: 2rem;
  }
}
</style>