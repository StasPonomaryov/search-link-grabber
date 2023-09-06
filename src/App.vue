<script setup>
import SiteHeader from './components/SiteHeader.vue'
import SiteContent from './components/SiteContent.vue'
import SiteFooter from './components/SiteFooter.vue'
</script>

<template>
  <header>
    <div class="wrapper">
      <SiteHeader msg="Link Grabber v.1.0" />
    </div>
  </header>

  <main>
    <div class="wrapper">
      <SiteContent />
    </div>
  </main>

  <footer>
    <div class="wrapper">
      <SiteFooter />
    </div>
  </footer>
</template>

<style scoped>
header {
  line-height: 1.5;
}
header {
  display: flex;
  place-items: center;
}
.wrapper {
  padding: 1rem;
}
header,
footer {
  flex-grow: 0;
  flex-shrink: 0;
}
main {
  flex-grow: 1;
}
</style>
