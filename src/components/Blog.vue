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
      class="grid auto-rows-min gap-x-8 overflow-hidden md:grid-rows-[min-content_minmax(auto,128px)_auto_auto]"
      :class="$style.container"
    >
      <div class="grid auto-rows-min gap-y-4">
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
        class="md:row-span-4 md:grid-rows-subgrid"
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
