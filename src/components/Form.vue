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
      <button type="submit" class="form-submit">Отправить</button>
      <div class="form-agreement">
        Нажимая кнопку “Отправить”, вы соглашаетесь с <a href="#" class="form-link">политикой конфиденциальности</a> и <a href="#" class="form-link">договором оферты</a>
      </div>
    </form>
  </div>
</template>

<script setup>
// Можно добавить логику, если потребуется
import Close from '/close.svg'
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
  width: 90vw;
  max-width: 26rem;
  height: auto;
  background: var(--color-bg);
  border-radius: 1.25rem;
  padding: 2.5rem 2.5rem 2.5rem 2.5rem;
  box-sizing: border-box;
  opacity: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  gap: 1.25rem;
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
  gap: 0.3rem;
  width: 100%;
  align-items: flex-start;
}
.form-fields input {
  width: 100%;
  min-width: 10rem;
  height: 2.5rem;
  padding: 0.6rem 1rem;
  border-radius: 0.88rem;
  border: 1px solid var(--color-grey);
  font-size: 1rem;
  opacity: 1;
  box-sizing: border-box;
  display: block;
}
.form-fields input::placeholder {
  color: var(--color-placeholder);
  opacity: 1;
}
.form-submit {
  background: var(--color-orange);
  color: var(--color-bg);
  border: none;
  border-radius: 0.5rem;
  padding: 0.6rem 0;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.2s;
  width: 100%;
  margin-top: -0.6rem;
}
.form-submit:hover {
  background: var(--color-orange-hover);
}
.form-agreement {
  font-size: 0.9rem;
  color: var(--color-black);
  text-align: start;
  line-height: 1.4;
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
  font-size: 1rem;
  line-height: 1.375rem;
  letter-spacing: 0%;
  color: var(--color-black);
  margin-bottom: 0.13rem;
  display: block;
  text-align: left;
  width: 100%;
}
.form-label--name {
  margin-bottom: -0.06rem;
}
.form-label--phone {
  margin-bottom: -0.06rem;
  margin-top: 0.5rem;
}
.form-required {
  color: var(--color-error);
  font-size: 1rem;
  vertical-align: middle;
}
@media (max-width: 960px) {
  .form-popup {
    width: 96vw;
    max-width: 21.5rem;
    border-radius: 1.25rem;
    padding: 1.25rem 1rem 1.25rem 1rem;
    gap: 1.25rem;
  }
  .form-fields input {
    width: 100%;
    min-width: 8rem;
    height: 2.5rem;
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