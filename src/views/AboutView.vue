<script setup lang="ts">
import { useI18n } from 'vue-i18n'

const { t } = useI18n()
</script>

<template>
  <div class="flex flex-col items-center gap-6 text-center">
    <h1 class="text-3xl font-bold text-gray-800">{{ t('about.title') }}</h1>
    <p class="text-gray-500 max-w-md">{{ t('about.description') }}</p>

    <ul class="stack-list">
      <li>Vue 3</li>
      <li>Vite 8</li>
      <li>TypeScript 6</li>
      <li>TailwindCSS 4</li>
      <li>vue-i18n 11</li>
      <li>vue-router 5</li>
      <li>SCSS (Dart Sass)</li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
.stack-list {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: $spacing-sm;
  text-align: left;
  min-width: 200px;

  li {
    padding: $spacing-xs $spacing-base;
    border-left: 3px solid $color-primary;
    background-color: $color-primary-light;
    color: $color-secondary;
    border-radius: 0 $border-radius-sm $border-radius-sm 0;
    font-size: $font-size-sm;
  }
}
</style>
