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
  <div class="col-[full] grid grid-cols-subgrid bg-zinc-50 my-20">
    <div class="col-[main] grid grid-cols-3 gap-8 py-10">
      <div class="flex gap-4 flex-col">
        <h2 class="text-3xl font-bold">{{ title }}</h2>
        <p class="text-lg">{{ text }}</p>
        <Button class="self-start mt-auto">{{ cta }}</Button>
      </div>

      <TileCard
        v-for="(tile, index) in tiles"
        :key="index"
        :title="tile.title"
        :text="tile.text"
        :img="tile.img"
      />
    </div>
  </div>
</template>
