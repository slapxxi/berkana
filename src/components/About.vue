<script setup lang="ts">
import aboutImage from '@/assets/about.png'
import ArrowRightIcon from '@/assets/arrow-right-icon.svg'
import IconButton from '@/components/IconButton.vue'
import Subtitle from '@/components/Subtitle.vue'
import { points, subtitle, text, title } from '@/components/about.config'
</script>

<template>
  <div class="col-[main] my-20 grid gap-8 md:grid-cols-2">
    <img :src="aboutImage" alt="" class="self-center" />

    <div class="grid gap-4">
      <Subtitle>{{ subtitle }}</Subtitle>
      <h3 class="text-3xl font-bold">{{ title }}</h3>
      <p class="text-lg text-neutral-800" v-for="(item, index) in text" :key="index">{{ item }}</p>
      <button class="flex items-center gap-2 text-xamber-500">
        читать подробнее
        <IconButton variant="outline">
          <ArrowRightIcon class="size-6" />
        </IconButton>
      </button>

      <div class="grid md:grid-cols-3 gap-4">
        <div
          v-for="(item, index) in points"
          :key="index"
          class="grid md:border-r border-neutral-300 pr-2 last:border-0"
        >
          <div class="grid grid-cols-[24px_auto] gap-x-4 self-start py-4">
            <component :is="item.icon" class="w-full" />
            <div class="text-fluid-3xl font-bold text-xamber-500">{{ item.title }}</div>
            <div class="col-2 text-lg text-neutral-800">{{ item.text }}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
