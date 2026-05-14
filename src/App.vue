<script setup lang="ts">
import { useI18n } from 'vue-i18n'

const { locale, t } = useI18n()

function toggleLocale() {
  locale.value = locale.value === 'zh-CN' ? 'en-US' : 'zh-CN'
}
</script>

<template>
  <div class="min-h-screen bg-gray-50">
    <header class="flex items-center justify-between px-6 py-4 bg-white shadow-sm">
      <nav class="flex items-center gap-6">
        <span class="brand">Vue3 Starter</span>
        <RouterLink to="/" class="nav-link">{{ t('nav.home') }}</RouterLink>
        <RouterLink to="/about" class="nav-link">{{ t('nav.about') }}</RouterLink>
      </nav>
      <button class="lang-btn" @click="toggleLocale">
        {{ locale === 'zh-CN' ? 'EN' : '中文' }}
      </button>
    </header>
    <main class="container mx-auto px-4 py-12">
      <RouterView />
    </main>
  </div>
</template>

<style lang="scss" scoped>
.brand {
  font-size: $font-size-lg;
  font-weight: 600;
  color: $color-primary;
}

.nav-link {
  font-size: $font-size-base;
  color: $color-secondary;
  text-decoration: none;
  padding-bottom: 2px;
  border-bottom: 2px solid transparent;
  transition: all 0.2s;

  &:hover,
  &.router-link-active {
    color: $color-primary;
    border-bottom-color: $color-primary;
  }
}

.lang-btn {
  padding: $spacing-xs $spacing-sm;
  border: 1px solid $color-primary;
  border-radius: $border-radius-sm;
  color: $color-primary;
  font-size: $font-size-sm;
  cursor: pointer;
  transition: all 0.2s;

  &:hover {
    background-color: $color-primary;
    color: #fff;
  }
}
</style>
