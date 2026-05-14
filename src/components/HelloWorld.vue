<script setup lang="ts">
import { useI18n } from 'vue-i18n'
import { useCounterStore } from '@/stores/counter'

const { t } = useI18n()
const counter = useCounterStore()
</script>

<template>
  <div class="flex flex-col items-center gap-8 text-center">
    <div class="space-y-2">
      <h1 class="text-3xl font-bold text-gray-800">{{ t('home.title') }}</h1>
      <p class="text-gray-500">{{ t('home.description') }}</p>
    </div>

    <div class="flex flex-wrap justify-center gap-3">
      <span class="badge">Vue 3</span>
      <span class="badge">Vite</span>
      <span class="badge">TypeScript</span>
      <span class="badge">TailwindCSS 4</span>
      <span class="badge">vue-i18n</span>
      <span class="badge">vue-router</span>
      <span class="badge">Pinia</span>
      <span class="badge">SCSS</span>
    </div>

    <div class="counter-card">
      <p class="counter-value">{{ counter.count }}</p>
      <p class="counter-double">{{ t('home.doubleCount', { count: counter.doubleCount }) }}</p>
      <div class="flex gap-3 mt-4">
        <button class="counter-btn" @click="counter.decrement">－</button>
        <button class="counter-btn reset-btn" @click="counter.reset">{{ t('common.reset') }}</button>
        <button class="counter-btn" @click="counter.increment">＋</button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.badge {
  display: inline-block;
  padding: $spacing-xs $spacing-sm;
  background-color: $color-primary-light;
  color: $color-primary-dark;
  border-radius: $border-radius-base;
  font-size: $font-size-sm;
  font-weight: 500;
}

.counter-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: $spacing-lg $spacing-xl;
  background-color: #fff;
  border-radius: $border-radius-lg;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.08);
  min-width: 220px;
}

.counter-value {
  font-size: 3rem;
  font-weight: 700;
  color: $color-primary;
  line-height: 1;
}

.counter-double {
  margin-top: $spacing-xs;
  font-size: $font-size-sm;
  color: #9ca3af;
}

.counter-btn {
  padding: $spacing-xs $spacing-base;
  background-color: $color-primary;
  color: #fff;
  border-radius: $border-radius-base;
  font-size: $font-size-lg;
  font-weight: 600;
  cursor: pointer;
  transition: background-color 0.2s;
  min-width: 44px;

  &:hover {
    background-color: $color-primary-dark;
  }

  &.reset-btn {
    background-color: #e5e7eb;
    color: $color-secondary;
    font-size: $font-size-sm;

    &:hover {
      background-color: #d1d5db;
    }
  }
}
</style>
