<script setup lang="ts">
import Button from '@/components/Button.vue'
import TileCard from '@/components/TileCard.vue'
import { cta, text, tiles, title } from '@/components/catalogue.config'
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
