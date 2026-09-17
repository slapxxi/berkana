<script setup lang="ts">
import img1 from '@/assets/blog1.jpg'
import img2 from '@/assets/blog2.jpg'
import img3 from '@/assets/blog3.jpg'
import BlogCard from '@/components/BlogCard.vue'
import Subtitle from '@/components/Subtitle.vue'
import IconButton from '@/components/IconButton.vue'
import ArrowRightIcon from '@/assets/arrow-right-icon.svg'

const text =
  'Здесь вы найдёте полезную информацию и рекомендации по аренде специальной техники, которые помогут вам принимать обоснованные решения и оптимизировать процессы на ваших проектах.'

const posts = [
  {
    id: 1,
    title: 'Советы по безопасному использованию техники',
    text: 'Какие факторы учитывать при выборе спецтехники для вашего проекта.',
    img: img1,
  },
  {
    id: 2,
    title: 'Выбор подходящей техники',
    text: 'Какие факторы учитывать при выборе спецтехники для вашего проекта.',
    img: img2,
  },
  {
    id: 3,
    title: 'Последние новости отрасли',
    text: 'Какие факторы учитывать при выборе спецтехники для вашего проекта.',
    img: img3,
  },
]
</script>

<template>
  <div class="col-[main] my-20">
    <div
      class="grid gap-x-8 auto-rows-min grid-rows-[auto_minmax(auto,128px)] overflow-hidden text-ellipsis"
      :class="$style.container"
    >
      <div class="grid gap-y-4">
        <Subtitle>Блог</Subtitle>
        <h2 class="text-fluid-2xl font-bold">Статьи</h2>
        <p class="text-fluid-lg text-neutral-800/90">{{ text }}</p>
        <div class="flex items-center gap-2 text-xamber-500">
          <span>читать больше</span>
          <IconButton variant="outline">
            <ArrowRightIcon class="w-6" />
          </IconButton>
        </div>
      </div>

      <BlogCard
        v-for="post in posts"
        :key="post.id"
        :title="post.title"
        :text="post.text"
        :img="post.img"
        class="row-span-4 grid-rows-subgrid"
      />
    </div>
  </div>
</template>

<style module>
.container {
  --columns: minmax(auto, 248px) 2fr 2fr 2fr;
  grid-template-columns: var(--columns);
  transition: grid-template-columns 100ms linear;

  &:has(> :nth-child(2):hover) {
    --columns: minmax(auto, 248px) 3fr 2fr 2fr;
  }

  &:has(> :nth-child(3):hover) {
    --columns: minmax(auto, 248px) 2fr 3fr 2fr;
  }

  &:has(> :nth-child(4):hover) {
    --columns: minmax(auto, 248px) 2fr 2fr 3fr;
  }
}
</style>
