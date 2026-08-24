<script lang="ts" setup>
import ArrowRightIcon from '@/assets/arrow-right-icon.svg'
import IconButton from '@/components/IconButton.vue'

type Props = {
  title: string
  text: string
  img: string
}

const props = defineProps<Props>()
</script>

<template>
  <div class="rounded-[40px] bg-white p-2.5">
    <div class="card grid gap-y-4 rounded-[40px] bg-neutral-100/70 py-4">
      <img :src="props.img" alt="" />

      <div class="flex flex-col">
        <h3 class="px-4 text-xl font-bold">{{ props.title }}</h3>
        <h4 class="self-start rounded-r-full bg-white px-4 py-2 text-lg font-bold text-xamber-500">
          <span class="col-2">
            {{ props.text }}
          </span>
        </h4>
        <IconButton class="mt-auto ml-auto mr-4 w-min">
          <ArrowRightIcon class="size-6" />
        </IconButton>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  grid-template-areas: 'card';

  & > * {
    grid-area: card;
  }
}
</style>
