<script setup lang="ts">
import { advantages, title, text } from '@/components/advantages.config'
</script>

<template>
  <div class="col-[main] my-20 grid md:grid-cols-[1fr_3fr] gap-8">
    <div class="grid content-start gap-2.5 rounded-[40px] bg-xamber-500 p-8 text-white">
      <h2 class="text-3xl">{{ title }}</h2>
      <p>{{ text }}</p>
    </div>

    <div
      class="grid grid-cols-[repeat(auto-fit,minmax(240px,1fr))] gap-8 rounded-[40px] bg-zinc-50 p-8"
    >
      <div
        v-for="(item, index) in advantages"
        :key="index"
        class="grid justify-items-center gap-2 text-center"
      >
        <div class="grid place-items-center rounded-full bg-white p-4">
          <component :is="item.icon" class="size-8" />
        </div>
        <h3 class="text-lg font-bold">{{ item.title }}</h3>
        <p class="text-neutral-800">{{ item.text }}</p>
      </div>
    </div>
  </div>
</template>
