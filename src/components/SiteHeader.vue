<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <h1 class="green">{{ msg }}</h1>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2rem;
  position: relative;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1 {
    font-size: 2.5rem;
    text-align: left;
  }
}
</style>
