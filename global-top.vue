<script setup lang="ts">
// Progress bar pinned to the very top of the viewport: one line, brand gradient.
// Lives in the theme so every 9aia deck gets it without touching slides.md.
import { computed } from 'vue'
import { useNav } from '@slidev/client'

const nav = useNav()
const width = computed(() => {
  const total = nav.total.value || 1
  const current = nav.currentPage.value || 1
  return `${Math.min(100, Math.max(0, (current / total) * 100))}%`
})
</script>

<template>
  <div class="vp-progress" aria-hidden="true">
    <div class="vp-progress-bar" :style="{ width }" />
  </div>
</template>

<style scoped>
.vp-progress {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  z-index: 60;
  background: var(--vp-c-bg-alt);
}

.vp-progress-bar {
  height: 100%;
  background: linear-gradient(90deg, #bd34fe, #41d1ff);
  transition: width 0.35s ease;
}
</style>
