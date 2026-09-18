<script setup lang="ts">
import ArrowRightIcon from '@/assets/arrow-right-icon.svg'
import { posts, text } from '@/components/blog.config'
import BlogCard from '@/components/BlogCard.vue'
import IconButton from '@/components/IconButton.vue'
import Subtitle from '@/components/Subtitle.vue'
</script>

<template>
  <div class="col-[main] my-20">
    <div
      class="grid auto-rows-min gap-x-8 gap-y-4 md:gap-y-0 overflow-hidden"
      :class="$style.container"
    >
      <div class="grid auto-rows-min gap-y-4 md:col-span-full lg:col-auto md:mb-4">
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
  --columns: 1fr;
  --rows: initial;
  grid-template-columns: var(--columns);
  grid-template-rows: var(--rows);
  transition: grid-template-columns 100ms linear;

  @media (min-width: 768px) {
    --columns: 3fr 3fr 3fr;
    --rows: auto min-content minmax(200px, auto) minmax(100px, auto) minmax(100px, auto);

    &:has(> :nth-child(2):hover) {
      --columns: 4fr 3fr 3fr;
    }

    &:has(> :nth-child(3):hover) {
      --columns: 3fr 4fr 3fr;
    }

    &:has(> :nth-child(4):hover) {
      --columns: 3fr 3fr 4fr;
    }
  }

  @media (min-width: 1024px) {
    --columns: minmax(auto, 248px) 3fr 3fr 3fr;
    --rows: min-content minmax(auto, 128px) auto auto;

    &:has(> :nth-child(2):hover) {
      --columns: minmax(auto, 248px) 4fr 3fr 3fr;
    }

    &:has(> :nth-child(3):hover) {
      --columns: minmax(auto, 248px) 3fr 4fr 3fr;
    }

    &:has(> :nth-child(4):hover) {
      --columns: minmax(auto, 248px) 3fr 3fr 4fr;
    }
  }
}
</style>
