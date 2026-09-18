<script setup lang="ts">
import PlusIcon from '@/assets/plus-icon.svg'
import { faq, text, title } from '@/components/faq.config'
import FeedbackForm from '@/components/FeedbackForm.vue'
import Subtitle from '@/components/Subtitle.vue'
</script>

<template>
  <div class="col-[full] grid grid-cols-subgrid bg-neutral-100">
    <div
      class="col-[main] my-20 grid justify-between gap-x-8 gap-y-4 md:grid-cols-[minmax(auto,628px)_minmax(auto,550px)]"
    >
      <div class="grid gap-y-4">
        <Subtitle class="h">FAQ</Subtitle>
        <h2 class="text-fluid-3xl font-bold text-neutral-800">{{ title }}</h2>
        <p class="text-neutral-800/80">{{ text }}</p>

        <div class="grid gap-y-2">
          <details v-for="item in faq" :key="item.id" :class="$style.details" name="faq">
            <summary
              class="grid grid-cols-[1fr_32px] items-center rounded-lg bg-white p-4 font-bold hover:bg-white/40"
            >
              <span>
                {{ item.question }}
              </span>
              <PlusIcon class="w-full text-(--fg) transition" data-icon />
            </summary>
            <p class="p-2">{{ item.answer }}</p>
          </details>
        </div>
      </div>

      <FeedbackForm />
    </div>
  </div>
</template>

<style module>
.details {
  --fg: var(--color-xamber-500);

  &::details-content {
    opacity: 0;
    transform: translateY(-10px);
    transition: all 100ms ease-in-out;
  }

  &[open] [data-icon] {
    --fg: var(--color-amber-600);
    transform: rotate(45deg);
  }

  &[open]::details-content {
    transform: none;
    opacity: 1;
  }
}
</style>
