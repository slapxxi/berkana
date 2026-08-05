<script lang="ts" setup>
import Button from '@/components/Button.vue'
import Subtitle from '@/components/Subtitle.vue'

const title = 'Аренда специальной техники для эффективных решений вашего бизнеса'
const subtitle = 'Современная спецтехника'
const text =
  'Мы предлагаем широкий ассортимент спецтехники в аренду, чтобы помочь вам успешно решать задачии в строительстве, ремонте, земельных работах и других сферах.'
</script>

<template>
  <div class="hero text-white">
    <div class="col-[main] row-1 grid grid-cols-2">
      <div class="grid gap-6 self-center">
        <Subtitle>{{ subtitle }}</Subtitle>
        <h2 class="text-4xl">{{ title }}</h2>
        <p class="opacity-60">{{ text }}</p>
        <div class="flex gap-8">
          <Button>заказать звонок</Button>
          <button class="text-white/80">узнать стоимость</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.hero {
  grid-column: full;
  display: grid;
  grid-template-columns: subgrid;
  background: url('@/assets/hero.jpg') no-repeat;
  background-size: cover;
  background-position: bottom;

  &::before {
    content: '';
    grid-row: 1;
    grid-column: full;
    background-color: rgba(0, 0, 0, 0.6);
  }
}
</style>
