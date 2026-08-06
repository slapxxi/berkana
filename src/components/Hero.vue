<script lang="ts" setup>
import ArrowRightIcon from '@/assets/arrow-right-icon.svg'
import ServeIcon from '@/assets/serve-icon.svg'
import Button from '@/components/Button.vue'
import Controls from '@/components/Controls.vue'
import IconButton from '@/components/IconButton.vue'
import Subtitle from '@/components/Subtitle.vue'

const title = 'Аренда специальной техники для эффективных решений вашего бизнеса'
const subtitle = 'Современная спецтехника'
const text =
  'Мы предлагаем широкий ассортимент спецтехники в аренду, чтобы помочь вам успешно решать задачии в строительстве, ремонте, земельных работах и других сферах.'
const features = [
  {
    title: 'Гибкие условия аренды',
    text: 'Краткосрочная и долгосрочная аренда, мы подстраиваемся под ваши требования.',
  },
  {
    icon: ServeIcon,
    title: 'Профессиональное обслуживание',
    text: 'Наша команда экспертов всегда готова помочь вам выбрать подходящую технику и ответить на все вопросы.',
  },
]
</script>

<template>
  <div class="hero text-white">
    <div class="col-[main] row-1 grid gap-y-12 py-4 md:grid-cols-2">
      <div class="grid gap-2 self-end">
        <Subtitle>{{ subtitle }}</Subtitle>
        <h2 class="text-4xl">{{ title }}</h2>
        <p class="opacity-60">{{ text }}</p>
      </div>

      <div class="flex gap-8 self-start md:row-2">
        <Button>заказать звонок</Button>
        <button class="flex items-center gap-2 text-white/80">
          узнать стоимость

          <IconButton variant="outline">
            <ArrowRightIcon class="size-4" />
          </IconButton>
        </button>
      </div>

      <div class="grid grid-cols-[1fr_1fr_10px] gap-4 md:row-2">
        <div
          v-for="item in features"
          :key="item.title"
          class="flex flex-col gap-2 rounded-3xl border border-white/15 bg-black/25 p-6 backdrop-blur-sm"
          :class="{ 'self-end': !item.icon }"
        >
          <component :is="item.icon" v-if="item.icon" class="size-8" />
          <h3 class="mt-auto text-xl">{{ item.title }}</h3>
          <p class="text-lg text-white/70">{{ item.text }}</p>
        </div>

        <Controls class="self-end mb-12" />
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
