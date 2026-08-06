<script setup lang="ts">
import ArrowLeftIcon from '@/assets/arrow-left-icon.svg'
import ArrowRightIcon from '@/assets/arrow-right-icon.svg'
import certImage from '@/assets/cert.jpg'
import Controls from '@/components/Controls.vue'
import IconButton from '@/components/IconButton.vue'

const title = 'Сертификаты и лицензии'
const text =
  'Мы понимаем, что качество и безопасность — это главные приоритеты в сфере аренды специальной техники. Поэтому мы постоянно стремимся к соблюдению всех стандартов и требованиям, которые гарантируют надёжность и эффективность нашей работы.'
</script>

<template>
  <div class="relative col-[full] my-20 grid grid-cols-subgrid grid-rows-[32px_auto_32px]">
    <div class="col-[full/main] row-2 h-full w-full bg-xamber-500" />

    <div class="col-[main] row-span-full grid grid-cols-2 grid-rows-subgrid gap-8 text-white">
      <div class="row-2 flex gap-8">
        <div class="grid gap-4 self-center">
          <h2 class="text-3xl font-bold">{{ title }}</h2>
          <p>{{ text }}</p>
        </div>

        <div class="grid gap-4 self-end">
          <IconButton variant="outline">
            <ArrowRightIcon class="w-8" />
          </IconButton>
          <IconButton variant="outline">
            <ArrowLeftIcon class="w-8" />
          </IconButton>
        </div>
      </div>

      <div class="col-2 row-span-full grid grid-cols-2 gap-2">
        <img :src="certImage" alt="" class="w-full rounded-2xl shadow" />
        <img :src="certImage" alt="" class="w-full rounded-2xl shadow" />
      </div>
    </div>

    <Controls class="absolute -right-4 bottom-16 col-[main] w-2 self-end" />
  </div>
</template>
