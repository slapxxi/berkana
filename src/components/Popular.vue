<script setup lang="ts">
import ArrowRightIcon from '@/assets/arrow-right-icon.svg'
import ArrowLeftIcon from '@/assets/arrow-left-icon.svg'
import card1Image from '@/assets/bulldozer.png'
import card2Image from '@/assets/excavator.jpg'
import card3Image from '@/assets/samosval.jpg'
import DetailsCard from '@/components/DetailsCard.vue'
import IconButton from '@/components/IconButton.vue'
import Controls from '@/components/Controls.vue'

const title = 'Популярная спецтехника'
const items = [
  {
    title: 'Экскаватор — погрузчик JCB 4CX',
    img: card1Image,
    details: {
      Габариты: [5.62, 2.35, 2.89],
    },
    price: '25 000 руб/смена',
  },
  {
    title: 'Экскаватор — погрузчик JCB 3CX',
    img: card2Image,
    details: {
      Габариты: [5.62, 2.35, 2.89],
    },
    price: '25 000 руб/смена',
  },
  {
    title: 'Самосвал',
    img: card3Image,
    details: {
      Габариты: [5.62, 2.35, 2.89],
    },
    price: '25 000 руб/смена',
  },
]
</script>

<template>
  <div class="col-[full] mt-20">
    <h2 class="text-center text-3xl font-bold">{{ title }}</h2>
  </div>

  <div
    class="col-[full] mt-10 mb-20 grid grid-cols-subgrid gap-x-2 gap-y-5 bg-neutral-100/70 pt-13 pb-30"
  >
    <div class="col-[main] grid gap-8 md:grid-cols-3">
      <DetailsCard
        v-for="(item, index) in items"
        :key="index"
        :title="item.title"
        :img="item.img"
        :details="item.details"
        :price="item.price"
        class="gap-y-0 md:row-span-5 md:grid-rows-subgrid"
      />
    </div>

    <div class="mb-12 hidden self-end md:block">
      <Controls class="w-2" />
    </div>

    <div class="col-[main] hidden justify-end gap-8 md:flex">
      <IconButton variant="outline"><ArrowLeftIcon class="w-6" /></IconButton>
      <IconButton variant="outline"><ArrowRightIcon class="w-6" /></IconButton>
    </div>
  </div>
</template>
