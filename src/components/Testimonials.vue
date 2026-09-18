<script lang="ts" setup>
import Quote from '@/components/Quote.vue'
import { quotes } from '@/components/testimonials.config'
import { Swiper, SwiperSlide } from 'swiper/vue'
import Controls from '@/components/Controls.vue'
</script>

<template>
  <div class="col-[full] overflow-hidden grid grid-cols-subgrid">
    <div class="col-[main]">
      <Swiper
        :slidesPerView="2.3"
        :spaceBetween="10"
        :style="{ width: '100%', height: '100%', overflow: 'visible' }"
      >
        <SwiperSlide v-for="q in quotes" :key="q.id" class="py-12">
          <Quote :author="q.author" :text="q.text" :createdAt="q.created" class="h-full" />
        </SwiperSlide>
      </Swiper>
    </div>
    <div class="col-[main] px-6">
      <Controls orientation="horizontal" class="w-10" />
    </div>
  </div>
</template>
