<template>
    <div class="home-wrapper">
        <h1 class="vissually-hidden">Много уточек</h1>
        <img :src="ManyTxt" alt="Много" class="home-image home-image--many">
        <img :src="DuckTxt" alt="Уточек" class="home-image home-image--duck-text">
        <img :src="Quack" alt="Кря" class="home-image home-image--quack">
        <img :src="is375 ? Duck375 : (is960 ? Duck960 : Duck)" alt="Утка" class="home-image home-image--duck">
        <div class="home-content">
            <p>Маленький друг найдётся для каждого в этом кряквенно жёлтом мире</p>
            <MyButton color="blue">Смотреть уточек</MyButton>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import ManyTxt from '/home/many_txt.svg'
import DuckTxt from '/home/duck_txt.svg'
import Duck from '/home/duck.svg'
import Quack from '/home/quack.svg'
import MyButton from '../ui/MyButton.vue';

import Duck960 from '/home/duck-960.svg'
import Duck375 from '/home/duck_375.png'


const is960 = ref(window.innerWidth <= 960)
const is375 = ref(window.innerWidth <= 375)
function handleResize() {
  is960.value = window.innerWidth <= 960
  is375.value = window.innerWidth <= 375
}
onMounted(() => {
  window.addEventListener('resize', handleResize)
})
onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
})
</script>

<style scoped>


.vissually-hidden{
    position: absolute;
    width: 0.07rem;
    height: 0.07rem;
    margin: -0.07rem;
    clip: rect(0 0 0 0);
}
.home-image {
    display: block;
    max-width: 100%;
    height: auto;
}
.home-image--many {
    width: 37vw;
    /* height: 9.5vw; */
    opacity: 1;
    position: absolute;
    top: 12.3vw;
    left: 2.1vw;
}

.home-image--duck-text {
    width: 42vw;
    /* height: 9.5vw; */
    opacity: 1;
    position: absolute;
    top: 19.5vw;
    left: 56.3vw;
}

.home-image--quack {
    width: 9.3vw;
    opacity: 1;
    position: absolute;
    top: 25.5vw;
    left: 22vw;
}

.home-image--duck {
    width: 48.2vw;
    opacity: 1;
    position: absolute;
    top: 8.9vw;
    left: 26vw;
}

.home-content{
    width: 25vw;
    opacity: 1;
    position: absolute;
    top: 30.3vw;
    left: 66.9vw;
 
    gap: 0.44rem;
}
.home-content p {
    font-size: 1.1rem;
    line-height: 1.4rem;
    letter-spacing: 0.055rem;
    margin: 0;
    text-align: left;
    margin-bottom: 0.7vw;
}

@media (min-width: 1281px) {
.home-wrapper { 
    min-height: 100vh;
      height: 60vw;
      overflow: hidden;
      position: relative;
      margin-top: -7vw;
}
}

@media (max-width: 960px) {

  .home-wrapper {
      width: 98.1vw;
      height: 60vw;
      overflow: hidden;
      position: relative;
   } 
    .home-image--many {
        top: 8vw;
        left: 1.2vw;
        width: 49vw;
    }
    
    .home-image--duck-text {
        top: 20.6vw;
        left: 0.4vw;
        width: 56.5vw;
    }
    
    .home-image--quack {
        top: 22vw;
        left: 61vw;
        width: 12.5vw;
    }
    
    .home-image--duck {
        top: 0vw;
        left: 66.3vw;
        width: 32vw;
    }
    
    .home-content{
        width: 34vw;
        top: 34.6vw;
        left: 0vw;
    }

}

@media (max-width: 375px) {
      .home-wrapper {
      width: 92vw;
      height: 150vw;
      padding-right: 4.58%;
      overflow: hidden;
      position: relative;
   } 
    .home-image--many {
        width: 76vw;
        top: 15vw;
        left: 2vw;
    }
    .home-image--duck-text {
        width: 87vw;
        top: 36vw;
        left: 0.8vw;
    }
    .home-image--duck {
        width: 51vw;
        top: 68vw;
        left: 45vw;
    }
    .home-image--quack {
        width: 16.5vw;
        top: 99.5vw;
        left: 39.5vw;
    }
    .home-content {
        width: 85vw;
        top: 61vw;
        left: 0vw;
 
    }
    .home-content p {
        font-size: 1.2rem;
        line-height: 1.4rem;
        letter-spacing: 0rem;
    }
    .my-button {
        margin-top: 2.5vw;
    }
}
</style> 