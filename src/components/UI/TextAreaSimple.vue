<script>
export default {
  name: 'textarea-simple',
  props: {
    disabled: [Boolean],
    text: [String]
  },
}
</script>

<template>
  <textarea
    class="textarea"
    rows="10"
    :disabled="disabled"
    :value="text"
  ></textarea>
</template>

<style scoped>
.textarea {
  background-color: transparent;
  border: 1px solid #555;
  border-radius: 8px;
  padding: 8px;
  width: clamp(220px, 50%, 1280px)
}
</style>