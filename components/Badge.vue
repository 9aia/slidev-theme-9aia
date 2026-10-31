<script setup lang="ts">
withDefaults(defineProps<{
  type?: 'info' | 'tip' | 'warning' | 'danger'
  text?: string
}>(), {
  type: 'tip',
  text: undefined,
})
</script>

<template>
  <span class="vp-badge" :class="type">
    <slot>{{ text }}</slot>
  </span>
</template>

<style>
.vp-badge {
  display: inline-block;
  margin-left: 2px;
  border: 1px solid transparent;
  border-radius: 12px;
  padding: 0 10px;
  font-size: 12px;
  font-weight: 600;
  line-height: 22px;
  vertical-align: middle;
  transform: translateY(-2px);
}

.vp-badge.info {
  color: var(--vp-c-text-1);
  background-color: var(--vp-c-default-soft);
}

.vp-badge.tip {
  color: var(--vp-c-brand-1);
  background-color: var(--vp-c-brand-soft);
}

.vp-badge.warning {
  color: var(--vp-c-warning-1);
  background-color: var(--vp-c-warning-soft);
}

.vp-badge.danger {
  color: var(--vp-c-danger-1);
  background-color: var(--vp-c-danger-soft);
}
</style>
