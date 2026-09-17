<script setup lang="ts">
import Button from '@/components/Button.vue'
import ChevronRightIcon from '@/assets/chevron-right-icon.svg'

const props = defineProps<{
  title: string
  text: string
  img: string
}>()
</script>

<template>
  <div class="grid gap-y-4 overflow-hidden rounded-xl text-white group">
    <img
      :src="props.img"
      alt=""
      class="col-1 row-span-full h-full w-full object-cover"
      :class="$style.gradient"
    />

    <div
      :class="$style.gradient"
      class="col-1 row-span-full auto-rows-min opacity-80 group-hover:opacity-100 transition-opacity"
    ></div>

    <h3 class="z-10 col-1 row-2 mx-4 text-fluid-xl font-bold">{{ props.title }}</h3>
    <p class="z-10 col-1 row-3 mx-4 opacity-70">{{ props.text }}</p>
    <Button
      class="z-10 col-1 row-4 mx-4 mt-auto mb-4 flex items-center justify-between gap-4 text-fluid-base"
      >читать подробнее <ChevronRightIcon class="w-3"
    /></Button>
  </div>
</template>

<style module>
.gradient {
  background: linear-gradient(to top, rgba(0, 0, 0, 1), rgba(0, 0, 9, 0.4));
}
</style>
