<script setup lang="ts">
defineProps<{
  label: string
  url: string
  icon: string
}>()
</script>

<template>
  <v-btn
    block
    size="large"
    variant="tonal"
    :prepend-icon="icon"
    :href="url"
    target="_blank"
    rel="noopener"
  >{{ label }}</v-btn>
</template>
