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
import Duck from '/home/duck.svg'
import Quack from '/home/quack.svg'
import MyButton from '../ui/MyButton.vue';
</script>

<style scoped>
.vissually-hidden{
    position: absolute;
    width: 1px;
    height: 1px;
    margin: -1px;
    clip: rect(0 0 0 0);
}
.home-image {
    display: block;
    max-width: 100%;
    height: auto;
}
.home-image--many {
    width: 471px;
    height: 152px;
    opacity: 1;
    position: absolute;
    top: 148px;
    left: 27px;
}

.home-image--duck-text {
    width: 539px;
    height: 152px;
    opacity: 1;
    position: absolute;
    top: 240px;
    left: 720px;
}

.home-image--quack {
    width: 120px;
    height: 108px;
    opacity: 1;
    position: absolute;
    top: 332px;
    left: 282px;
}

.home-image--duck {
    width: 620px;
    height: 620px;
    opacity: 1;
    position: absolute;
    top: 108px;
    left: 330px;
}

.home-content{
    width: 315px;
    height: 86px;
    opacity: 0.8;
    position: absolute;
    top: 392px;
    left: 853px;
    display: flex;
    flex-direction: column;
    gap: 7px;
}
.home-content p {
    font-size: 16px;
    line-height: 20px;
    letter-spacing: 0.4px;
    margin: 0;
    text-align: left;
}
.home-content .my-button {
    width: 156px;
    height: 38px;
    opacity: 1;
}

@media (min-width: 1281px) {
.home-wrapper {
    position: relative;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 auto;
}
}

@media (max-width: 960px) {
    .home-image--many {
        top: 130px;
    }
    
    .home-image--duck-text {
        top: 252px;
        left: 27px;
    }
    
    .home-image--quack {
        top: 332px;
        left: 602px;
    }
    
    .home-image--duck {
        top: 108px;
        left: 612px;
    }
    
    .home-content{
        opacity: 1;
        text-align: center;
        top: 392px;
        left: 27px;
    }

}

@media (max-width: 375px) {
    .home-image--many {
        width: 300px;
        height: 90px;
        top: 100px;
        left: 15px;
    }
    .home-image--duck-text {
        width: 320px;
        height: 90px;
        top: 160px;
        left: 20px;
    }
    .home-image--duck {
        width: 350px;
        height: 350px;
        top: 60px;
        left: 15px;
    }
    .home-image--quack {
        width: 80px;
        height: 70px;
        top: 220px;
        left: 150px;
    }
    .home-content {
        width: 250px;
        height: 70px;
        top: 280px;
        left: 20px;
        gap: 5px;
    }
    .home-content p {
        font-size: 12px;
        line-height: 16px;
        letter-spacing: 0.2px;
    }
    .home-content .my-button {
        width: 120px;
        height: 32px;
    }
}
</style> 