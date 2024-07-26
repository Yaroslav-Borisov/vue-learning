<template>
  <input :value="value" @change="updateInput" class="input" />
</template>

<script>
export default {
  name: 'Input',
  props: {
    value: [String, Number],
  },
  methods: {
    updateInput(event) {
      this.$emit('update:value', event.target.value);
    },
  },
};
</script>

<style scoped>
.input {
  padding: 5px;
  border: 2px solid #000000;
}
</style>
