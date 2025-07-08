<template>
  <button
    class="icon-btn"
    type="button"
    @mousedown="isPressed = true"
    @mouseup="isPressed = false"
    @mouseleave="isPressed = false; isHovered = false"
    @mouseover="isHovered = true"
    @mouseout="isHovered = false"
  >
    <img :src="iconSrc" :alt="name" class="icon-img" />
  </button>
</template>

<script>
export default {
  name: 'UiIcon',
  props: {
    name: {
      type: String,
      required: true,
      validator: value => ['basket', 'nav'].includes(value),
    },
    size: {
      type: [Number, String],
      default: 24,
    },
  },
  data() {
    return {
      isHovered: false,
      isPressed: false,
    };
  },
  computed: {
    iconSrc() {
      if (this.isPressed) {
        return `/icon/${this.name}_pressed.svg`;
      }
      if (this.isHovered) {
        return `/icon/${this.name}_hover.svg`;
      }
      return `/icon/${this.name}.svg`;
    },
  },
};
</script> 

<style scoped>
.icon-btn {
  background: none;
  border: none;
  padding: 0;
  cursor: pointer;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.icon-img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}
</style>
