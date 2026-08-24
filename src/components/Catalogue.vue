<script setup lang="ts">
import tile1Image from '@/assets/tile-1.png'
import tile2Image from '@/assets/tile-2.png'
import Button from '@/components/Button.vue'
import TileCard from '@/components/TileCard.vue'

const title = 'Каталог спецтехники'
const text =
  'Мы предлагаем консультации по выбору оборудования, учитывая специфику вашего проекта и ваши требования. Свяжитесь с нами для получения рекомендаций и дополнительной информации.'
const cta = 'заказать звонок'
const tiles = [
  {
    title: 'Экскаваторы-погрузчики',
    text: 'от 25 000 руб/смена',
    img: tile1Image,
  },
  {
    title: 'Самосвалы',
    text: 'от 16 000 руб/смена',
    img: tile2Image,
  },
]
</script>

<template>
  <div class="col-[full] my-20 grid grid-cols-subgrid bg-neutral-100/70">
    <div class="col-[main] grid md:grid-cols-[1fr_2fr] gap-8 py-10">
      <div class="flex flex-col gap-4">
        <h2 class="text-3xl font-bold">{{ title }}</h2>
        <p class="text-lg">{{ text }}</p>
        <Button class="mt-auto self-start">{{ cta }}</Button>
      </div>

      <div class="grid md:grid-cols-[repeat(auto-fill,minmax(260px,1fr))] gap-8">
        <TileCard
          v-for="(tile, index) in tiles"
          :key="index"
          :title="tile.title"
          :text="tile.text"
          :img="tile.img"
          class="self-start"
        />
      </div>
    </div>
  </div>
</template>
