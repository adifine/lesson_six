<script setup lang="ts">
import { ref, watch, onMounted, provide } from 'vue'
import { RouterView } from 'vue-router'
import type { Ref } from 'vue'

const isDark = ref(true)

function toggleTheme() {
  isDark.value = !isDark.value
}

watch(isDark, (dark) => {
  document.documentElement.setAttribute('data-theme', dark ? 'dark' : 'light')
})

onMounted(() => {
  document.documentElement.setAttribute('data-theme', 'dark')
})

provide<Ref<boolean>>('isDark', isDark)
provide<() => void>('toggleTheme', toggleTheme)
</script>

<template>
  <RouterView />
</template>

