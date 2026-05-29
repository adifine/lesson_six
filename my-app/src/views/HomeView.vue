<script setup lang="ts">
import { ref, watch, onMounted } from 'vue'

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

      <div class="avatar"></div>

      <h1 class="name">Adi Fine</h1>
      <p class="tagline">Developer · Creator · Builder</p>

      <div class="links">
        <a href="#" class="link-btn">Portfolio</a>
        <a href="https://linkedin.com/in/adifine" class="link-btn" target="_blank" rel="noopener">LinkedIn</a>
        <a href="mailto:adi@example.com" class="link-btn">Email</a>
      </div>
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

.avatar {
  width: 96px;
  height: 96px;
  border-radius: 50%;
  background: var(--avatar-bg);
  margin: 0 auto 1.5rem;
  border: 3px solid var(--btn-hover-bg);
}

.name {
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--text);
  margin-bottom: 0.4rem;
}

.tagline {
  color: var(--subtext);
  font-size: 0.95rem;
  margin-bottom: 2rem;
}

.links {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.link-btn {
  display: block;
  padding: 0.85rem 1.5rem;
  background: var(--btn-bg);
  color: var(--btn-text);
  text-decoration: none;
  border-radius: 0.75rem;
  font-weight: 600;
  font-size: 1rem;
  transition:
    background 0.2s,
    transform 0.2s,
    box-shadow 0.2s;
}

.link-btn:hover {
  background: var(--btn-hover-bg);
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.25);
}
</style>
