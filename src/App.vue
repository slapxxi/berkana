<script setup lang="ts">
import Header from '@/components/Header.vue'
</script>

<template>
  <div class="wrapper" const u>
    <Header />
  </div>
</template>

<style scoped>
.wrapper {
  display: grid;
  grid-template-columns: 1fr [main] minmax(auto, 1288px) [main-end] 1fr;
}
</style>
