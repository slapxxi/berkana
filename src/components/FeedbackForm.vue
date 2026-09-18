<script lang="ts" setup>
import Button from '@/components/Button.vue'
import TextArea from '@/components/TextArea.vue'
import TextInput from '@/components/TextInput.vue'
import { title } from '@/components/feedback-form.config'
import { ref } from 'vue'

const name = ref('')
const message = ref('')
const phone = ref('')
</script>

<template>
  <div class="grid auto-rows-min gap-y-10 self-start rounded-4xl bg-white p-10">
    <h3 class="mx-auto max-w-103 text-center font-bold">{{ title }}</h3>

    <form class="grid gap-y-5" @submit.prevent>
      <TextInput placeholder="Ваше имя" v-model="name" />
      <TextInput placeholder="+7 (___)-___-__-__" v-model="phone" />
      <TextArea placeholder="Текст сообщения" v-model="message" />
      <Button>Отправить</Button>
    </form>
  </div>
</template>
