<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'Button',
};
</script>

<style scoped>
.button {
  margin: 0;
  padding: 10px;
  font-weight: 700;
  background: none;
  border: 2px solid #000000;
  cursor: pointer;
}
</style>
