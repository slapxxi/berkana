<script setup lang="ts">
import ArrowLeftIcon from '@/assets/arrow-left-icon.svg'
import ArrowRightIcon from '@/assets/arrow-right-icon.svg'
import ExcavatorImage from '@/assets/excavator.jpg'
import SamosvalImage from '@/assets/samosval.jpg'
import Card from '@/components/Card.vue'
import Controls from '@/components/Controls.vue'
import IconButton from '@/components/IconButton.vue'

const categories = [
  {
    title: 'Экскаваторы-погрузчики',
    img: ExcavatorImage,
  },
  {
    title: 'Самосвалы',
    img: SamosvalImage,
  },
]
</script>

<template>
  <div class="col-[main] grid grid-cols-[1fr_10px] gap-4 py-10">
    <div class="grid grid-cols-2 gap-8">
      <Card v-for="(item, index) in categories" :key="index" :title="item.title" :img="item.img" />
    </div>

    <Controls class="self-end mb-6" />

    <div class="col-1 row-2 flex gap-8 justify-self-end">
      <IconButton variant="outline"><ArrowLeftIcon class="size-6" /></IconButton>
      <IconButton variant="fill"><ArrowRightIcon class="size-6" /></IconButton>
    </div>
  </div>
</template>
