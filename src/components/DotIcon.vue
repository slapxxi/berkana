<script setup lang="ts">
const props = defineProps<{ active?: boolean }>()
</script>

<template>
  <svg
    viewBox="0 0 8 8"
    class="fill-current stroke-current"
    :class="{ 'fill-xamber-500 stroke-xamber-500': props.active }"
  >
    <circle cx="4" cy="4" r="3" :class="{ 'fill-none': !props.active }" />
  </svg>
</template>
