<script setup lang="ts">
// Slide number, bottom right. Hidden on the cover (page 1).
import { computed } from 'vue'
import { useNav } from '@slidev/client'

const nav = useNav()
const show = computed(() => (nav.currentPage.value || 1) > 1)
</script>

<template>
  <div v-if="show" class="vp-page-number">
    <span class="cur">{{ nav.currentPage.value }}</span>
    <span class="sep">/</span>
    <span class="tot">{{ nav.total.value }}</span>
  </div>
</template>

<style scoped>
.vp-page-number {
  position: fixed;
  right: 1.5rem;
  bottom: 1rem;
  z-index: 60;
  font-family: var(--vp-font-family-mono, monospace);
  font-size: 0.7rem;
  letter-spacing: 0.06em;
  color: var(--vp-c-text-3);
  user-select: none;
}

.vp-page-number .sep { margin: 0 0.25rem; opacity: 0.5; }
.vp-page-number .cur { color: var(--vp-c-text-2); }
</style>
