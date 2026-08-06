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
    <div class="card grid gap-y-4 rounded-[40px] bg-zinc-50 py-4">
      <h3 class="text-xl font-bold area-[title]">{{ props.title }}</h3>
      <h4
        class="justify-self-start rounded-r-full bg-white p-1 pl-4 pr-4 text-lg font-bold text-xamber-500 area-[text]"
      >
        <span class="col-2">
          {{ props.text }}
        </span>
      </h4>
      <img :src="props.img" alt="" class="area-[card]" />
      <IconButton class="place-self-end area-[cta]">
        <ArrowRightIcon class="size-6" />
      </IconButton>
    </div>
  </div>
</template>

<style scoped>
.card {
  grid-template-rows: [card] min-content min-content 1fr [card-end];
  grid-template-columns: [card] minmax(0, 20px) auto minmax(0, 20px) [card-end];
  grid-template-areas: '. title title' 'text text .' '. cta .';
}
</style>
