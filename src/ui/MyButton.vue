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
      default: 'orange',
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
  height: 2.6rem;
  opacity: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Inter', sans-serif;
  font-weight: 600;
  font-style: normal;
  font-size: 1rem;
  line-height: 100%;
  letter-spacing: 0.04em;
  text-align: center;
  border-radius: 0.5rem;
  border: none;
  padding: 0 0.9rem;
  background: var(--color-orange);
  cursor: pointer;
  transition: background 0.2s;
  color: var(--color-bg);
}
.my-button--orange {
  background: var(--color-orange);
}
.my-button--orange:hover {
  background: var(--color-orange-hover);
}
.my-button--orange:active {
  background: var(--color-orange-active);
}
.my-button--blue {
  background: var(--color-list);
}
.my-button--blue:hover {
  background: var(--color-blue-hover);
}
.my-button--blue:active {
  background: var(--color-blue-active);
}
</style>