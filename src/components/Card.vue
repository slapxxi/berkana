<script lang="ts" setup>
import ArrowRightIcon from '@/assets/arrow-right-icon.svg'
import IconButton from '@/components/IconButton.vue'

type Props = {
  title: string
  img: string
}

const props = defineProps<Props>()
</script>

<template>
  <div class="card grid overflow-hidden rounded-3xl text-white shadow">
    <img :src="props.img" alt="" />
    <div class="z-10 flex items-center justify-between self-end p-6">
      <h3 class="text-xl font-bold">{{ props.title }}</h3>
      <IconButton>
        <ArrowRightIcon class="size-6" />
      </IconButton>
    </div>
  </div>
</template>

<style scoped>
.card {
  grid-template-areas: 'card';

  &::after {
    content: '';
    grid-area: card;
    background-image: linear-gradient(to top, rgba(0, 0, 0, 0.9), transparent 140px);
  }

  & > * {
    grid-area: card;
  }
}
</style>
