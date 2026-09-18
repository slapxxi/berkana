<script lang="ts" setup>
import type { TextareaHTMLAttributes } from 'vue'

interface Props extends /*@vue-ignore*/ TextareaHTMLAttributes {}

const props = defineProps<Props>()
const model = defineModel<string>()
</script>

<template>
  <textarea v-model="model" v-bind="$attrs" class="rounded-full border border-neutral-400 p-4" />
</template>
