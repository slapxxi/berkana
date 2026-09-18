<script lang="ts" setup>
import QMarkIcon from '@/assets/qmark.svg'

const props = defineProps<{
  author: string
  text: string
  createdAt: string
}>()
</script>

<template>
  <div class="mt-7.5 grid gap-y-5 rounded-4xl p-7.5 shadow-lg">
    <QMarkIcon class="-mt-14 w-15 text-xamber-500" />
    <h3 class="font-bold">{{ props.author }}</h3>
    <p>{{ props.text }}</p>
    <date class="text-neutral-700/50">{{ props.createdAt }}</date>
  </div>
</template>
