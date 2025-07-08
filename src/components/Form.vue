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
  width: 417px;
  height: 360px;
  background: #fff;
  border-radius: 20px;
  padding: 40px 40px 40px 40px;
  box-sizing: border-box;
  opacity: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  gap: 20px;
}
.form-close {
  position: absolute;
  top: 9px;
  right: 7px;
  background: none;
  border: none;
  /* font-size: 26px; */
  /* width: 20px;
  height: 20px; */
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
  gap: 5px;
  width: 100%;
  align-items: center;
  align-items: flex-start;
}
.form-fields input {
  width: 337px;
  height: 40px;
  padding: 10px 16px;
  border-radius: 14px;
  border: 1px solid #ddd;
  font-size: 16px;
  opacity: 1;
  box-sizing: border-box;
  display: block;
}
.form-fields input::placeholder {
  color: rgba(167, 167, 167, 1);
  opacity: 1;
}
.form-submit {
  background: rgba(234, 179, 8, 1);
  color: #fff;
  border: none;
  border-radius: 8px;
  padding: 10px 0;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.2s;
  width: 100%;
  margin-top: -10px;
}
.form-submit:hover {
  background: rgba(254, 199, 28, 1);
}
.form-agreement {
  /* margin-top: 10px; */
  font-size: 14px;
  color: rgba(0, 0, 0, 1);
  text-align: start;
  line-height: 1.4;
}
.form-agreement .form-link {
  color: rgba(37, 129, 235, 1);
  text-decoration: none;
  cursor: pointer;
}
.form-label {
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-style: normal;
  font-size: 16px;
  line-height: 22px;
  letter-spacing: 0%;
  color: rgba(0,0,0,1);
  margin-bottom: 2px;
  display: block;
  text-align: left;
  width: 337px;
}
.form-label--name {
  margin-bottom: -1px;
}
.form-label--phone {
  margin-bottom: -1px;
  margin-top: 8px;
}
.form-required {
  color: #E53935;
  font-size: 16px;
  vertical-align: middle;
}
@media (max-width: 960px) {
  .form-popup {
    width: 344px;
    height: 320px;
    border-radius: 20px;
    padding: 20px 16px 20px 16px;
    gap: 20px;
  }
  .form-fields input {
    width: 312px;
    height: 40px;
    border-radius: 14px;
    padding: 10px 16px;
    opacity: 1;
    border-width: 1px;
  }
  .form-agreement {
    line-height: 22px;
  }
  .form-label--phone {
  margin-top: 6px;
}
}
</style> 