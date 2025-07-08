<template>
  <button :class="['my-button', colorClass]">
    <slot />
  </button>
</template>

<script>
export default {
  name: 'MyButton',
  props: {
    color: {
      type: String,
      default: 'orange', // или 'blue'
    },
  },
  computed: {
    colorClass() {
      return `my-button--${this.color}`;
    },
  },
};
</script>

<style scoped>
.my-button {
  height: 38px;
  opacity: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Inter', sans-serif;
  font-weight: 600;
  font-style: normal;
  font-size: 15px;
  line-height: 100%;
  letter-spacing: 0.5%;
  text-align: center;
  border-radius: 8px;
  border: none;
  padding: 0 12.5px; /* или другой нужный вам padding */
  background: var(--Orange, rgba(234, 179, 8, 1));
  cursor: pointer;
  transition: background 0.2s;

  color: rgba(255, 255, 255, 1);
}
.my-button--orange {
  background: rgba(234, 179, 8, 1);
}
.my-button--orange:hover {
  background: rgba(254, 199, 28, 1);
}
.my-button--orange:active {
  background: rgba(204, 149, 0, 1);
}
.my-button--blue {
  background: rgba(37, 129, 235, 1);
}
.my-button--blue:hover {
  background: rgba(67, 159, 255, 1);
;
}
.my-button--blue:active {
  background: rgba(7, 99, 205, 1);
;
}
</style> 