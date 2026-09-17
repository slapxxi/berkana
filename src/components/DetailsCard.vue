<script lang="ts" setup>
import Button from '@/components/Button.vue'
import Pill from '@/components/Pill.vue'

const props = defineProps<{
  title: string
  img: string
  details: Record<string, string | Array<number>>
  price: string
}>()
</script>

<template>
  <div class="grid gap-4 rounded-[40px] bg-white p-2">
    <div>
      <img :src="img" class="aspect-video w-full rounded-[40px] object-cover" />
    </div>

    <h3 class="text-xl font-bold text-neutral-800">{{ props.title }}</h3>

    <div class="grid gap-1">
      <div
        v-for="[key, value] in Object.entries(props.details)"
        :key="key"
        class="flex items-center gap-2 text-neutral-600"
      >
        <div>{{ key }}:</div>
        <div v-if="Array.isArray(value)" class="flex items-center gap-2">
          <template v-for="(item, index) in value" :key="index">
            <Pill>{{ item }}</Pill>
            <span v-if="index !== value.length - 1" class="text-xs">x</span>
          </template>
        </div>
      </div>
    </div>

    <hr class="my-0 text-neutral-200" />

    <div class="flex flex-wrap gap-2">
      <div class="flex items-center gap-1">
        <span class="translate-y-0.5 text-sm text-neutral-500">от</span>
        <span class="text-2xl font-bold text-neutral-800">
          {{ props.price }}
        </span>
      </div>
      <Button class="flex-1">Заказать</Button>
    </div>
  </div>
</template>
