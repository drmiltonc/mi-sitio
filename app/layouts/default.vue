<script setup lang="ts">

</script>

<template>
  <div>
    <SharedHeader />
    <UMain class="flex flex-col items-center justify-center gap-4 p-8">

      
        <slot />
      

    </UMain>
    <SharedFooter />
  </div>
</template>

<style scoped></style>
