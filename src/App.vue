<script setup lang="ts">
import Header from '@/components/Header.vue'
import Hero from '@/components/Hero.vue'
</script>

<template>
  <div class="wrapper" const u>
    <Header />
    <Hero />
  </div>
</template>

<style scoped>
.wrapper {
  display: grid;
  grid-template-columns: [full] 1fr [main] minmax(auto, 1288px) [main-end] 1fr [full-end];
  grid-template-rows: min-content 1fr;
  column-gap: calc(var(--spacing) * 8);
  min-height: 100vh;
}
</style>
