<template>
  <div class="form-overlay" @click.self="$emit('close')">
    <form class="form-popup">
      <button class="form-close" @click.prevent="$emit('close')">
        <img :src="Close" alt="Закрыть" />
      </button>
      <div class="form-fields">
        <label class="form-label form-label--name">Имя <span class="form-required">*</span></label>
        <input type="text" placeholder="Введите ваше имя" required />
        <label class="form-label form-label--phone">Телефон <span class="form-required">*</span></label>
        <input type="tel" placeholder="+7 000 000 00 00 " required />
      </div>
      <MyButton color="orange" class="form-submit" >Отправить</MyButton>
      <!-- <button type="submit" class="form-submit">Отправить</button> -->
      <div class="form-agreement">
        Нажимая кнопку “Отправить”, вы соглашаетесь с <a href="#" class="form-link">политикой конфиденциальности</a> и <a href="#" class="form-link">договором оферты</a>
      </div>
    </form>
  </div>
</template>

<script setup>
// Можно добавить логику, если потребуется
import Close from '/close.svg'
import MyButton from '../ui/MyButton.vue'
</script>

<style scoped>
.form-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0,0,0,0.45);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 200;
}
.form-popup {
  width: 95vw;
  max-width: 29.6rem;
  min-height: 25.5rem;
  background: var(--color-bg);
  border-radius: 1.25rem;
  padding: 2.5rem 2.8rem 2.5rem 2.8rem;
  box-sizing: border-box;
  opacity: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  gap: 1.3rem;
}
.form-close {
  position: absolute;
  top: 0.6rem;
  right: 0.45rem;
  background: none;
  border: none;
  cursor: pointer;
  color: #888;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}
.form-fields {
  display: flex;
  flex-direction: column;
  gap: 0.27rem;
  width: 100%;
  align-items: flex-start;
  margin-top: 0.2rem;
}
.form-fields input {
  width: 100%;
  min-width: 10rem;
  height: 2.8rem;
  padding: 0.6rem 1rem;
  border-radius: 0.88rem;
  border: 1px solid var(--color-grey);
  font-size: 1rem;
  opacity: 1;
  box-sizing: border-box;
  display: block;
  margin-top: -0.3rem;
}
.form-fields input::placeholder {
  color: var(--color-placeholder);
  opacity: 1;
}
.form-submit {
  width: 100%;
}
.form-agreement {
  font-size: 1rem;
  color: var(--color-black);
  text-align: start;
  line-height: 1.5;
}
.form-agreement .form-link {
  color: var(--color-list);
  text-decoration: none;
  cursor: pointer;
}
.form-label {
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-style: normal;
  font-size: 1.2rem;
  line-height: 2rem;
  letter-spacing: 0%;
  color: var(--color-black);
  /* margin-bottom: 0.2rem; */
  display: block;
  text-align: left;
  width: 100%;
}
.form-label--phone {

  margin-top: 0.4rem;
}
.form-required {
  color: var(--color-error);
  font-size: 1rem;
  vertical-align: middle;
}
@media (max-width: 960px) {
  .form-popup {
    width: 98vw;
    max-width: 24.5rem;
    min-height: 23rem;
    border-radius: 1.25rem;
    padding: 1.21rem 1.2rem 1.26rem 1.19rem;
    gap: 1.4rem;
  }
  .form-fields input {
    width: 100%;
    min-width: 8rem;
    height: 2.8rem;
    border-radius: 0.88rem;
    padding: 0.6rem 1rem;
    opacity: 1;
    border-width: 1px;
  }
  .form-agreement {
    line-height: 1.375rem;
  }
  .form-label--phone {
    margin-top: 0.38rem;
  }
}
</style>