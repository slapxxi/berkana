<script setup lang="ts">
import MailIcon from '@/assets/mail-icon.svg'
import PhoneIcon from '@/assets/phone-icon.svg'
import PinIcon from '@/assets/pin-icon.svg'
import TelegramIcon from '@/assets/telegram-icon.svg'
import WhatsappIcon from '@/assets/whatsapp-icon.svg'
import Button from '@/components/Button.vue'
import {
  address,
  email,
  confidentiality,
  copy,
  dev,
  lists,
  phone,
  publicOffer,
  text,
  title,
  workingHours,
} from '@/components/footer.config'
import TextInput from '@/components/TextInput.vue'
import { ref } from 'vue'

const name = ref('')
const phoneInput = ref('')
</script>

<template>
  <footer class="col-[full] grid grid-cols-subgrid bg-neutral-800 text-white">
    <div class="col-[main] grid gap-y-10 pt-20 pb-7.5">
      <h3 class="text-fluid-4xl font-bold uppercase">{{ title }}</h3>
      <p class="text-white/70">{{ text }}</p>
      <form @submit.prevent class="grid gap-4 md:grid-cols-[2fr_2fr_1fr]">
        <TextInput
          v-model="name"
          placeholder="Ваше имя"
          class="border-transparent bg-neutral-700"
        />
        <TextInput
          v-model="phoneInput"
          placeholder="+7 (___)-___-__-__"
          class="border-transparent bg-neutral-700"
        />
        <Button>Оставить Заявку</Button>
      </form>

      <div
        class="grid grid-rows-[minmax(340px,auto)] items-start justify-between lg:grid-cols-[minmax(0,220px)_auto_auto_minmax(0,220px)]"
      >
        <div class="grid gap-y-5">
          <img src="@/assets/logo-bright.png" alt="" class="w-20" />
          <small class="text-lg text-white/50">{{ copy }}</small>
          <small class="text-lg text-white/50">{{ confidentiality }}</small>
          <div>
            <h4 class="text-white/50">время работы</h4>
            <div>{{ workingHours }}</div>
          </div>
        </div>

        <div v-for="list in lists" :key="list.id" class="grid gap-y-4">
          <h4 class="text-xl font-bold">{{ list.title }}</h4>
          <ul class="grid list-none gap-y-2 text-white/50">
            <li v-for="link in list.links" :key="link">{{ link }}</li>
          </ul>
        </div>

        <div class="grid gap-y-4">
          <div class="grid gap-y-4">
            <h4 class="text-xl font-bold">Адрес</h4>
            <div class="inline-grid grid-cols-[14px_1fr] gap-x-2.5">
              <PinIcon class="w-full translate-y-1 text-xamber-500" />
              <p class="text-white/50">
                {{ address }}
              </p>
            </div>
          </div>

          <div class="grid gap-y-4">
            <h4 class="text-xl font-bold">Контакты</h4>
            <div class="inline-grid grid-cols-[18px_1fr] gap-x-2.5 gap-y-2">
              <PhoneIcon class="w-full translate-y-1 text-xamber-500" />
              <p class="text-white/50">
                {{ phone }}
              </p>
            </div>
            <div class="inline-grid grid-cols-[21px_1fr] gap-x-2.5 gap-y-2">
              <MailIcon class="w-full translate-y-1 text-xamber-500" />
              <p class="text-white/50">
                {{ email }}
              </p>
            </div>
          </div>
        </div>
      </div>

      <div
        class="grid grid-cols-[minmax(0,240px)_min-content_minmax(0,240px)] place-items-center justify-between border-t border-white/20 pt-4"
      >
        <small class="text-sm text-white/50">{{ publicOffer }}</small>
        <div class="inline-grid grid-cols-[repeat(2,25px)] gap-x-3 text-xamber-500">
          <TelegramIcon />
          <WhatsappIcon />
        </div>
        <span class="text-sm text-white/50 justify-self-end text-right">
          Разработка сайта: <br />{{ dev }}</span
        >
      </div>
    </div>
  </footer>
</template>
