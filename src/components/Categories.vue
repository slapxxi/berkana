<script setup lang="ts">
import ArrowLeftIcon from '@/assets/arrow-left-icon.svg'
import ArrowRightIcon from '@/assets/arrow-right-icon.svg'
import Card from '@/components/Card.vue'
import Controls from '@/components/Controls.vue'
import IconButton from '@/components/IconButton.vue'
import { categories } from '@/components/categories.config'
</script>

<template>
  <div class="col-[main] my-20 grid grid-cols-[1fr_10px] gap-4">
    <div class="grid gap-8 md:grid-cols-2">
      <Card v-for="(item, index) in categories" :key="index" :title="item.title" :img="item.img" />
    </div>

    <Controls class="mb-6 hidden w-2 self-end md:grid" />

    <div class="col-1 row-2 hidden gap-8 justify-self-end md:flex">
      <IconButton variant="outline"><ArrowLeftIcon class="size-6" /></IconButton>
      <IconButton variant="fill"><ArrowRightIcon class="size-6" /></IconButton>
    </div>
  </div>
</template>
