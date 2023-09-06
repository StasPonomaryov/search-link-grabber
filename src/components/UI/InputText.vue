<script>
export default {
  name: 'input-text',
  props: {
    modelValue: [String, Number]
  },
  methods: {
    updateInput(event) {
      this.$emit('update:modelValue', event.target.value)
    }
  }
}
</script>

<template>
  <input
    :value="modelValue"
    @input="updateInput"
    class="input-text"
    type="text"
  />
</template>

<style scoped>
.input-text {
  background-color: #e5e5e5;
  border: 0;
  border-radius: 8px;
  padding: 8px;
  width: clamp(220px, 50%, 1280px)
}
</style>