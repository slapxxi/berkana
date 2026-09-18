<script lang="ts" setup>
import logoImg from '@/assets/logo.jpg'
import TelegramIcon from '@/assets/telegram-icon.svg'
import WhatsAppIcon from '@/assets/whatsapp-icon.svg'
import Button from '@/components/Button.vue'
import { items, nav } from '@/components/header.config'
import MenuIcon from '@/components/MenuIcon.vue'
import { ref } from 'vue'

const menuOpen = ref(false)

function toggleMenu() {
  menuOpen.value = !menuOpen.value
}
</script>

<template>
  <header class="sticky -top-19 z-20 col-[full] row-1 grid grid-cols-subgrid bg-white">
    <div
      class="col-[main] grid grid-cols-[80px_auto] justify-between gap-8 py-4 lg:grid-cols-[80px_1fr_auto]"
    >
      <img :src="logoImg" alt="" class="w-full" />

      <nav class="hidden lg:block">
        <ul class="flex flex-wrap justify-between gap-4 text-sm">
          <li
            v-for="(item, index) in items"
            :key="index"
            class="grid auto-rows-min grid-cols-[20px_auto] gap-x-3"
          >
            <component :is="item.icon" class="w-full text-xamber-500" />
            <h3 v-if="item.title" class="text-neutral-500">{{ item.title }}</h3>
            <div class="col-2" v-html="item.text" />
          </li>
        </ul>
      </nav>

      <div class="grid grid-cols-[repeat(2,25px)] gap-3 self-center text-xamber-500">
        <TelegramIcon class="w-full" />
        <WhatsAppIcon class="w-full" />
      </div>
    </div>

    <div class="z-10 col-[full] grid grid-cols-subgrid bg-zinc-900 py-3 text-white">
      <div class="col-[main] flex items-center justify-between gap-2">
        <button
          @click="toggleMenu"
          :class="{ 'text-white/70': menuOpen }"
          class="transition-[color]"
        >
          <MenuIcon class="size-10" :open="menuOpen" />
        </button>

        <nav class="hidden flex-1 md:block">
          <ul class="flex justify-around">
            <li v-for="(item, index) in nav" :key="index">{{ item }}</li>
          </ul>
        </nav>

        <Button>заказать звонок</Button>
      </div>
    </div>

    <div class="menu bg-xamber-500 text-white" v-if="menuOpen">
      <div class="col-2 py-4">menu with content</div>
    </div>
  </header>
</template>

<style scoped>
.menu {
  grid-column: full;
  grid-row: 3;
  position: absolute;
  display: grid;
  grid-template-columns: 1fr minmax(auto, 1288px) 1fr;
  width: 100%;
  transition:
    opacity 140ms ease-in-out,
    transform 140ms ease-in-out;

  @starting-style {
    opacity: 0;
    transform: translateY(-100%);
  }
}
</style>
