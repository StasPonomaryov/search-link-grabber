<script>
export default {
  name: 'button-simple'
}
</script>

<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<style scoped>
.btn {
  background-color: rgb(28, 124, 124);
  border: 0;
  border-radius: 8px;
  margin: 0 1rem;
  padding: 10px 15px;
  color: #fff;
}
</style>