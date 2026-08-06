<script lang="ts" setup>
type Props = {
  variant?: 'outline' | 'fill'
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'fill',
})
</script>

<template>
  <button
    class="cursor-pointer rounded-full border p-3 border-current"
    :class="{
      'bg-xamber-500 border-xamber-500 text-white hover:opacity-80': props.variant === 'fill',
      'opacity-60 hover:opacity-100': props.variant === 'outline',
    }"
  >
    <slot />
  </button>
</template>
