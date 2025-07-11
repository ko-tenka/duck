<template>
    <div class="home-wrapper">
        <h1 class="vissually-hidden">Много уточек</h1>
        <img :src="ManyTxt" alt="Много" class="home-image home-image--many">
        <img :src="DuckTxt" alt="Уточек" class="home-image home-image--duck-text">
        <img :src="Quack" alt="Кря" class="home-image home-image--quack">
        <img :src="Duck" alt="Утка" class="home-image home-image--duck">
        <div class="home-content">
            <p>Маленький друг найдётся для каждого в этом кряквенно жёлтом мире</p>
            <MyButton color="blue">Смотреть уточек</MyButton>
        </div>
    </div>
</template>

<script setup>
import ManyTxt from '/home/many_txt.svg'
import DuckTxt from '/home/duck_txt.svg'
import Duck from '/home/duck.png'
import Quack from '/home/quack.svg'
import MyButton from '../ui/MyButton.vue';
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
    width: 30vw;
    height: 9.5vw;
    opacity: 1;
    position: absolute;
    top: 9.5vw;
    left: 1.7vw;
}

.home-image--duck-text {
    width: 34vw;
    height: 9.5vw;
    opacity: 1;
    position: absolute;
    top: 15.6vw;
    left: 46vw;
}

.home-image--quack {
    width: 7.5vw;
    height: 6.8vw;
    opacity: 1;
    position: absolute;
    top: 21vw;
    left: 18vw;
}

.home-image--duck {
    width: 40vw;
    height: 40vw;
    opacity: 1;
    position: absolute;
    top: 6.7vw;
    left: 21vw;
}

.home-content{
    width: 20vw;
    height: 5.4vw;
    opacity: 0.8;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    flex-direction: column;
    gap: 0.44rem;
}
.home-content p {
    font-size: 1.1rem;
    line-height: 1.25rem;
    letter-spacing: 0.025rem;
    margin: 0;
    text-align: left;
}
.home-content .my-button {
    width: 9.8vw;
    height: 2.4vw;
    opacity: 1;
}

@media (min-width: 1281px) {
.home-wrapper {
    position: relative;
    width: 100%;
    max-width: 1280px;
    min-height: 100vh;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
}
}

@media (max-width: 960px) {

  .home-wrapper {
      width: 100%;
      height: 31vw;
      padding-right: 1.7%;
      overflow: hidden;
      position: relative;
   } 
    .home-image--many {
        top: 3vw;
        left: 0.7vw;

    }
    
    .home-image--duck-text {
        top: 10.6vw;
        left: 0.3vw;
    }
    
    .home-image--quack {
        top: 12.8vw;
        left: 36vw;
    }
    
    .home-image--duck {
        top: -1vw;
        left: 40vw;
        width: 36vw;
        height: 36vw;
    }
    
    .home-content{
        opacity: 1;
        text-align: center;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
    }

}

@media (max-width: 375px) {
      .home-wrapper {
      width: 100%;
      height: 36vw;
      padding-right: 4.58%;
      overflow: hidden;
      position: relative;
   } 
    .home-image--many {
        width: 18vw;
        height: 4vw;
        top: 3.2vw;
        left: 0.4vw;
    }
    .home-image--duck-text {
        width: 21vw;
        height: 4vw;
        top: 8.1vw;
        left: 0.2vw;
    }
    .home-image--duck {
        width: 22vw;
        height: 22vw;
        top: 15.3vw;
        left: 10.5vw;
    }
    .home-image--quack {
        width: 4vw;
        height: 4vw;
        top: 13.7vw;
        left: 9.4vw;
    }
    .home-content {
        width: 16vw;
        height: 4vw;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        gap: 0.3rem;
    }
    .home-content p {
        font-size: 0.8rem;
        line-height: 1.1rem;
        letter-spacing: 0.01rem;
    }
    .home-content .my-button {
        width: 8vw;
        height: 2vw;
    }
}
</style> 