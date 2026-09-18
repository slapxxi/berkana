<script setup lang="ts">
import About from '@/components/About.vue'
import Advantages from '@/components/Advantages.vue'
import Blog from '@/components/Blog.vue'
import Catalogue from '@/components/Catalogue.vue'
import Categories from '@/components/Categories.vue'
import Certs from '@/components/Certs.vue'
import Header from '@/components/Header.vue'
import Hero from '@/components/Hero.vue'
import OurClients from '@/components/OurClients.vue'
import Popular from '@/components/Popular.vue'
import Testimonials from '@/components/Testimonials.vue'
</script>

<template>
  <div class="wrapper">
    <Header />
    <Hero />
    <Categories />
    <About />
    <Certs />
    <Catalogue />
    <Advantages />
    <Popular />
    <OurClients />
    <Testimonials />
    <Blog />
  </div>
</template>

<style scoped>
.wrapper {
  display: grid;
  grid-template-columns: [full] 1fr [main] minmax(auto, 1288px) [main-end] 1fr [full-end];
  grid-template-rows: auto minmax(calc(100vh - 148px), auto);
  column-gap: calc(var(--spacing) * 8);
}
</style>
