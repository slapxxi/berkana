<script setup lang="ts">
import DotIcon from '@/components/DotIcon.vue'
</script>

<template>
  <div class="grid gap-2">
    <button v-for="item in 3" :key="item">
      <DotIcon :active="item === 3" />
    </button>
  </div>
</template>
