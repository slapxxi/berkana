<script lang="ts" setup>
import type { InputHTMLAttributes } from 'vue'

interface Props extends /*@vue-ignore*/ InputHTMLAttributes {}

const props = defineProps<Props>()
const model = defineModel<string>()
</script>

<template>
  <input
    type="text"
    v-model="model"
    v-bind="$attrs"
    class="rounded-full border border-neutral-400 p-4"
  />
</template>
