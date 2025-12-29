<script setup lang="ts">
import type { ButtonProps } from '@nuxt/ui';

const links = ref<ButtonProps[]>([
  {
    label: 'Get started',
    color: 'neutral'
  },
  {
    label: 'Learn more',
    color: 'neutral',
    variant: 'subtle',
    trailingIcon: 'i-lucide-arrow-right'
  }
])
</script>

<template>
  <UPageCTA
    title="Getting Started with Nuxt UI"
    description="Build beautiful, responsive, and accessible user interfaces with Nuxt UI, the official component library for Nuxt.js."
    orientation="horizontal"
    :links="links"
  >
    <img
      src="https://picsum.photos/640/728"
      width="320"
      height="364"
      alt="Illustration"
      class="w-full rounded-lg"
    />
  </UPageCTA>
</template>
