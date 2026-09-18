<script lang="ts" setup>
import Quote from '@/components/Quote.vue'
import { quotes } from '@/components/testimonials.config'
import { Swiper, SwiperSlide } from 'swiper/vue'
</script>

<template>
  <div class="col-[full]">
    <Swiper :slidesPerView="2.3" :spaceBetween="20" wrapperClass="py-4 max-w-[1200px]">
      <SwiperSlide v-for="q in quotes" :key="q.id">
        <Quote :author="q.author" :text="q.text" :createdAt="q.created"></Quote>
      </SwiperSlide>
    </Swiper>
  </div>
</template>
