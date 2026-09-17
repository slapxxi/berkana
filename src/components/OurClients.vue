<script setup lang="ts">
import lspLogo from '@/assets/lsp-logo.png'
import otdelstroyLogo from '@/assets/otdelstroy-logo.png'
import monolitcityLogo from '@/assets/monolitcity-logo.jpg'
import fitnesshouseLogo from '@/assets/fitnesshouse-logo.png'

const text =
  'В ООО «Беркана» мы гордимся тем, что работаем с широким спектром клиентов, от небольших предприятий до крупных корпораций.'
const logos = [lspLogo, otdelstroyLogo, monolitcityLogo, fitnesshouseLogo]
</script>

<template>
  <div class="col-[full] my-20 grid grid-cols-subgrid">
    <div class="col-[main] grid md:grid-cols-[1fr_2fr] gap-4">
      <div class="grid gap-y-2.5">
        <h2 class="text-fluid-3xl font-bold">Наши клиенты</h2>
        <p class="text-neutral-800/90">{{ text }}</p>
      </div>

      <div
        class="grid grid-cols-[repeat(auto-fit,minmax(auto,160px))] items-center justify-around self-center filter-[grayscale(1)]"
      >
        <img v-for="(logo, i) in logos" :key="i" :src="logo" class="w-full" />
      </div>
    </div>
  </div>
</template>
