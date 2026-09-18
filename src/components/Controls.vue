<script setup lang="ts">
import DotIcon from '@/components/DotIcon.vue'

// with defaults
const props = withDefaults(
  defineProps<{
    orientation?: 'horizontal' | 'vertical'
  }>(),
  {
    orientation: 'vertical',
  },
)
</script>

<template>
  <div class="grid gap-2" :class="{ 'grid-flow-col': props.orientation === 'horizontal' }">
    <button v-for="item in 3" :key="item">
      <DotIcon :active="item === 3" />
    </button>
  </div>
</template>
