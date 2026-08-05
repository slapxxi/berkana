<script lang="ts" setup>
const props = defineProps<{ open: boolean }>()
</script>

<template>
  <svg fill="none" stroke="currentColor" viewBox="0 0 31 13">
    <path
      stroke-linecap="round"
      :d="`M.5.5h26m-26 6h26m-26 6h${props.open ? 13 : 26}`"
      class="transition-[d]"
    />
  </svg>
</template>
