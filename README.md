# vue3-vite-typescript-tailwindcss4-starter

一个开箱即用的 Vue3 最小启动模板，集成了当前主流前端技术栈。

## 技术栈

| 依赖 | 版本 | 说明 |
|------|------|------|
| [Vue 3](https://vuejs.org/) | ^3.5 | 渐进式前端框架，全面使用 `<script setup>` |
| [Vite](https://vite.dev/) | ^8.0 | 极速构建工具 |
| [TypeScript](https://www.typescriptlang.org/) | ~6.0 | 类型安全 |
| [TailwindCSS](https://tailwindcss.com/) | ^4.0 | CSS-first 配置，通过 `@tailwindcss/vite` 接入 |
| [SCSS](https://sass-lang.com/) | ^1.99 | 全局变量通过 `additionalData` 自动注入每个组件 |
| [vue-router](https://router.vuejs.org/) | ^5.0 | 官方路由，含懒加载示例 |
| [Pinia](https://pinia.vuejs.org/) | ^3.0 | 官方状态管理，Setup Store 风格 |
| [vue-i18n](https://vue-i18n.intlify.dev/) | ^11.0 | 国际化，支持中英文切换 |

## 项目结构

```
src/
├── components/
│   └── HelloWorld.vue       # 首页演示组件（使用 Pinia store）
├── i18n/
│   └── index.ts             # createI18n 配置（Composition API 模式）
├── locales/
│   ├── zh-CN.ts             # 中文语言包
│   └── en-US.ts             # 英文语言包
├── router/
│   └── index.ts             # 路由配置（/about 懒加载）
├── stores/
│   └── counter.ts           # Pinia counter store（含 computed）
├── styles/
│   ├── index.css            # TailwindCSS 入口（@import "tailwindcss"）
│   └── _variables.scss      # SCSS 全局变量
├── views/
│   ├── HomeView.vue         # / 首页
│   └── AboutView.vue        # /about 关于页
├── App.vue                  # 根组件（顶部导航 + RouterView）
└── main.ts                  # 应用入口
```

## 快速开始

```bash
# 安装依赖
pnpm install

# 启动开发服务器
pnpm dev

# 类型检查 + 生产构建
pnpm build

# 预览生产包
pnpm preview
```

## 关键配置说明

**TailwindCSS 4**：无需 `tailwind.config.js`，直接在 CSS 中 `@import "tailwindcss"`，由 `@tailwindcss/vite` 插件处理。

**SCSS 全局变量**：在 `vite.config.ts` 中配置 `preprocessorOptions.scss.additionalData`，`_variables.scss` 中的变量在所有 `<style lang="scss">` 块中均可直接使用，无需手动 import。

**路径别名**：`@` 指向 `src/`，在 `vite.config.ts` 和 `tsconfig.app.json` 中均已配置。

**vue-i18n**：`legacy: false` 启用 Composition API 模式，使用 `useI18n()` 获取翻译函数。

**Pinia**：采用 Setup Store 风格（`defineStore` + 函数体），支持 `ref`、`computed` 及 action。
