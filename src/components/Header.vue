<script lang="ts" setup>
import logoImg from '@/assets/logo.jpg'
import PinIcon from '@/assets/pin-icon.svg'
import TimeIcon from '@/assets/time-icon.svg'
import MailIcon from '@/assets/mail-icon.svg'
import PhoneIcon from '@/assets/phone-icon.svg'

import TelegramIcon from '@/assets/telegram-icon.svg'
import WhatsAppIcon from '@/assets/whatsapp-icon.svg'

const items = [
  { icon: PinIcon, text: 'Санкт-Петербург<br/> пр-кт Индустриальный, 44/2 лит а, оф. 527' },
  { title: 'время работы', icon: TimeIcon, text: 'пн-вс: с 8:00 до 22:00' },
  { title: 'контакты', icon: PhoneIcon, text: '+7 812 561-62-17' },
  { title: 'электронная почта', icon: MailIcon, text: 'ai@berkana.spb.ru' },
]
</script>

<template>
  <header class="header col-[main] py-4">
    <img :src="logoImg" alt="" class="w-full" />

    <nav>
      <ul class="flex justify-between gap-4 text-sm">
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
  </header>
</template>

<style scoped>
.header {
  display: grid;
  grid-template-columns: 80px 1fr auto;
  gap: calc(var(--spacing) * 8);
}
</style>
