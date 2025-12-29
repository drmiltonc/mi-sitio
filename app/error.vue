<script setup lang="ts">
import type { NuxtError } from '#app'

const props = defineProps<{
  error: NuxtError
}>()
</script>

<template>
  <UApp>
    <UError :error="{
      statusCode: 404,
      statusMessage: 'Page not found',
      message: 'The page you are looking for does not exist.'
    }" :clear="{
      color: 'neutral',
      size: 'xs',
      icon: 'i-lucide-arrow-left',
      class: 'rounded-full'
    }" :ui="{
      statusCode: 'text-9xl font-thin',
      statusMessage: 'text-3xl font-semibold mt-2',
      message: 'text-lg text-muted-foreground mt-4',
    }" />
  </UApp>
</template>
