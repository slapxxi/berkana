<script setup lang="ts">
import ClockIcon from '@/assets/clock-icon.svg'
import CoinIcon from '@/assets/coin-icon.svg'
import TruckIcon from '@/assets/truck-icon.svg'
import WrenchIcon from '@/assets/wrench-icon.svg'
import HeadsetIcon from '@/assets/headset-icon.svg'
import ExcavatorIcon from '@/assets/excavator-icon.svg'

const title = 'Преимущества аренды'
const text =
  'Мы предлагаем аренду широкого ассортимента техники с множеством преимуществ, которые делают наш сервис выгодным и удобным.'
const advantages = [
  {
    icon: CoinIcon,
    title: 'Снижение капиталовложений',
    text: 'Аренда позволяет избежать больших первоначальных затрат на покупку техники.',
  },
  {
    icon: WrenchIcon,
    title: 'Отсутствие затрат на обслуживание',
    text: 'Вся ответственность за техническое обслуживание и ремонт лежит на нас.',
  },
  {
    icon: TruckIcon,
    title: 'Современное оборудование',
    text: 'Наша техника всегда обновляется и проходит регулярное обслуживание.',
  },
  {
    icon: ClockIcon,
    title: 'Экономия времени',
    text: 'Обеспечиваем быструю доставку техники на ваш объект, работайте без задержек.',
  },
  {
    icon: HeadsetIcon,
    title: 'Поддержка',
    text: 'Наша команда экспертов всегда готова помочь вам  в выборе подходящей техники.',
  },
  {
    icon: ExcavatorIcon,
    title: 'Гибкость',
    text: 'Вы можете арендовать технику на короткий или продолжительный срок.',
  },
]
</script>

<template>
  <div class="col-[main] my-20 grid grid-cols-[1fr_3fr] gap-8">
    <div class="rounded-[40px] bg-xamber-500 p-8 text-white">
      <h2 class="text-3xl">{{ title }}</h2>
      <p>{{ text }}</p>
    </div>

    <div class="grid grid-cols-3 gap-8 rounded-[40px] bg-zinc-50 p-8">
      <div
        v-for="(item, index) in advantages"
        :key="index"
        class="grid justify-items-center gap-2 text-center"
      >
        <div class="grid place-items-center rounded-full bg-white p-4">
          <component :is="item.icon" class="size-8" />
        </div>
        <h3 class="text-lg font-bold">{{ item.title }}</h3>
        <p class="text-neutral-800">{{ item.text }}</p>
      </div>
    </div>
  </div>
</template>
