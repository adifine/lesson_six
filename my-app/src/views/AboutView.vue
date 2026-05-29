<script setup lang="ts">
import { inject } from 'vue'
import { RouterLink } from 'vue-router'
import type { Ref } from 'vue'

const isDark = inject<Ref<boolean>>('isDark')!
const toggleTheme = inject<() => void>('toggleTheme')!
</script>

<template>
  <main class="page">
    <div class="card">
      <button
        class="theme-toggle"
        @click="toggleTheme"
        :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'"
      >
        {{ isDark ? '☀️' : '🌙' }}
      </button>

      <h1 class="title">About Me</h1>

      <p class="body-text">
        Hi, I'm Adi Fine — a developer, creator, and builder with a passion for
        crafting clean, purposeful digital experiences.
      </p>
      <p class="body-text">
        I love working across the stack, from designing interfaces to shipping
        full-featured web apps.
      </p>

      <RouterLink to="/" class="back-link">← Back</RouterLink>
    </div>
  </main>
</template>

<style scoped>
.page {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem 1rem;
}

.card {
  width: 100%;
  max-width: 480px;
  background: var(--card-bg);
  border-radius: 1.5rem;
  padding: 2.5rem 2rem;
  text-align: center;
  position: relative;
  box-shadow: 0 8px 40px rgba(0, 0, 0, 0.35);
}

.theme-toggle {
  position: absolute;
  top: 1rem;
  right: 1rem;
  background: var(--toggle-bg);
  border: none;
  border-radius: 50%;
  width: 2.5rem;
  height: 2.5rem;
  font-size: 1.1rem;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition:
    background 0.3s,
    transform 0.2s;
}

.theme-toggle:hover {
  transform: scale(1.1);
}

.title {
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--text);
  margin-bottom: 1.25rem;
}

.body-text {
  color: var(--subtext);
  font-size: 0.975rem;
  line-height: 1.7;
  margin-bottom: 1rem;
}

.back-link {
  display: inline-block;
  margin-top: 1.25rem;
  color: var(--subtext);
  font-size: 0.875rem;
  text-decoration: none;
  transition: color 0.2s;
}

.back-link:hover {
  color: var(--text);
}
</style>
