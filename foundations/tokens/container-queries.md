# Container Queries 容器查询 Token

> 现代响应式设计方案，基于容器尺寸而非视口尺寸进行样式调整。
> **组件级响应式，更灵活的布局控制**

---

## 目录

1. [什么是容器查询](#什么是容器查询)
2. [容器断点定义](#容器断点定义)
3. [容器类型](#容器类型)
4. [使用示例](#使用示例)
5. [浏览器兼容性](#浏览器兼容性)

---

## 什么是容器查询

### 传统媒体查询 vs 容器查询

**媒体查询（Media Queries）：**
- 基于**视口（viewport）**尺寸响应
- 全局性，所有组件共享同一断点
- 适合页面级布局

**容器查询（Container Queries）：**
- 基于**容器（container）**尺寸响应
- 组件级，每个组件独立响应
- 适合可复用组件（卡片、侧边栏等）

### 为什么需要容器查询？

**问题场景：** 同一个卡片组件，在不同位置需要不同样式

```html
<!-- 主内容区（宽） -->
<div class="content-wide">
  <card>显示三列布局</card>
</div>

<!-- 侧边栏（窄） -->
<aside class="sidebar-narrow">
  <card>显示单列布局</card>
</aside>
```

**媒体查询的局限：**
```css
/* ❌ 两个卡片都会受到影响 */
@media (max-width: 768px) {
  .card { /* 单列布局 */ }
}
```

**容器查询的解决方案：**
```css
/* ✅ 每个卡片根据自身容器宽度响应 */
@container (max-width: 400px) {
  .card { /* 单列布局 */ }
}
```

---

## 容器断点定义

### Token 清单

```
container-xs:    0px       # 超小容器（≥ 0px）
container-sm:    320px     # 小容器（≥ 320px）
container-md:    480px     # 中等容器（≥ 480px）
container-lg:    640px     # 大容器（≥ 640px）
container-xl:    800px     # 超大容器（≥ 800px）
container-2xl:   1024px    # 特大容器（≥ 1024px）
```

### 与视口断点的区别

| 类型 | xs | sm | md | lg | xl | 2xl |
|------|----|----|----|----|----|----|
| **视口断点** | 0px | 640px | 768px | 1024px | 1280px | 1536px |
| **容器断点** | 0px | 320px | 480px | 640px | 800px | 1024px |

**设计理念：** 容器断点更密集，适应组件级的细粒度响应

---

## 容器类型

### container-type 属性

```css
container-type: size;         /* 宽度和高度查询 */
container-type: inline-size;  /* 仅宽度查询（推荐） */
container-type: block-size;   /* 仅高度查询（罕用） */
container-type: normal;       /* 禁用容器查询（默认） */
```

**推荐使用 `inline-size`：**
- 仅响应宽度变化
- 避免高度查询导致的布局循环
- 性能更好

---

## CSS Variables 定义

```css
:root {
  /* 容器断点 */
  --container-xs: 0px;
  --container-sm: 320px;
  --container-md: 480px;
  --container-lg: 640px;
  --container-xl: 800px;
  --container-2xl: 1024px;
}

/* 定义容器上下文 */
.container {
  container-type: inline-size;
  container-name: card;  /* 可选：命名容器 */
}
```

---

## 使用示例

### 示例 1：响应式卡片

```html
<div class="container">
  <div class="card">
    <img class="card-image" src="..." alt="...">
    <div class="card-content">
      <h3 class="card-title">标题</h3>
      <p class="card-description">描述</p>
    </div>
  </div>
</div>
```

```css
/* 定义容器 */
.container {
  container-type: inline-size;
}

/* 默认：小容器，单列布局 */
.card {
  display: flex;
  flex-direction: column;
}

.card-image {
  width: 100%;
}

/* 容器 ≥ 480px：双列布局 */
@container (min-width: 480px) {
  .card {
    flex-direction: row;
    gap: var(--spacing-4);
  }

  .card-image {
    width: 200px;
    flex-shrink: 0;
  }
}

/* 容器 ≥ 640px：大卡片样式 */
@container (min-width: 640px) {
  .card {
    padding: var(--spacing-6);
  }

  .card-title {
    font-size: var(--font-size-xl);
  }
}
```

### 示例 2：命名容器

```html
<div class="sidebar" style="container-name: sidebar;">
  <div class="widget">侧边栏组件</div>
</div>

<div class="main" style="container-name: main;">
  <div class="widget">主内容组件</div>
</div>
```

```css
/* 仅在 sidebar 容器中响应 */
@container sidebar (max-width: 320px) {
  .widget {
    font-size: var(--font-size-xs);
  }
}

/* 仅在 main 容器中响应 */
@container main (min-width: 800px) {
  .widget {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
  }
}
```

### 示例 3：产品列表

```html
<div class="product-grid">
  <div class="product-card">产品 1</div>
  <div class="product-card">产品 2</div>
  <div class="product-card">产品 3</div>
</div>
```

```css
/* 产品网格作为容器 */
.product-grid {
  container-type: inline-size;
  display: grid;
  gap: var(--spacing-4);
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
}

/* 产品卡片根据网格容器宽度响应 */
@container (max-width: 600px) {
  .product-card {
    /* 紧凑样式 */
    padding: var(--spacing-2);
    font-size: var(--font-size-sm);
  }
}

@container (min-width: 601px) and (max-width: 900px) {
  .product-card {
    /* 标准样式 */
    padding: var(--spacing-4);
    font-size: var(--font-size-base);
  }
}

@container (min-width: 901px) {
  .product-card {
    /* 宽松样式 */
    padding: var(--spacing-6);
    font-size: var(--font-size-lg);
  }
}
```

### 示例 4：组合使用（容器查询 + 媒体查询）

```css
/* 页面级：媒体查询控制布局 */
@media (min-width: 1024px) {
  .layout {
    display: grid;
    grid-template-columns: 300px 1fr;
  }
}

/* 组件级：容器查询控制样式 */
.sidebar, .main {
  container-type: inline-size;
}

@container (max-width: 320px) {
  .component {
    /* 极窄容器样式 */
  }
}

@container (min-width: 640px) {
  .component {
    /* 宽容器样式 */
  }
}
```

---

## 容器查询单位

### cq* 单位

```
cqw:  容器宽度的 1%
cqh:  容器高度的 1%
cqi:  容器 inline-size 的 1%（推荐）
cqb:  容器 block-size 的 1%
cqmin: cqi 和 cqb 中较小的值
cqmax: cqi 和 cqb 中较大的值
```

### 使用示例

```css
.card-title {
  /* 字号随容器宽度缩放 */
  font-size: clamp(1rem, 5cqi, 2rem);
}

.responsive-padding {
  /* 内边距随容器宽度缩放 */
  padding: 2cqi 4cqi;
}
```

---

## 最佳实践

### 1. 优先使用 inline-size

✅ **推荐：**
```css
.container {
  container-type: inline-size;  /* 仅宽度 */
}
```

❌ **不推荐（除非必要）：**
```css
.container {
  container-type: size;  /* 宽度+高度，可能导致布局循环 */
}
```

### 2. 结合媒体查询使用

```css
/* 页面级布局：媒体查询 */
@media (min-width: 768px) {
  .layout {
    display: grid;
    grid-template-columns: 1fr 2fr;
  }
}

/* 组件级样式：容器查询 */
@container (min-width: 400px) {
  .card {
    display: flex;
  }
}
```

### 3. 命名容器避免冲突

```css
/* 多个容器时，使用不同名称 */
.sidebar {
  container-name: sidebar;
}

.main {
  container-name: main;
}

@container sidebar (max-width: 300px) {
  /* 仅影响 sidebar 内的元素 */
}
```

---

## 浏览器兼容性

### 支持情况（2025-11-16）

| 浏览器 | 版本 | 支持情况 |
|--------|------|---------|
| Chrome | ≥ 105 | ✅ 完全支持 |
| Edge | ≥ 105 | ✅ 完全支持 |
| Firefox | ≥ 110 | ✅ 完全支持 |
| Safari | ≥ 16 | ✅ 完全支持 |
| Safari iOS | ≥ 16 | ✅ 完全支持 |

**全球覆盖率：** ~90%（2025）

### 渐进增强策略

```css
/* 降级方案：默认样式 */
.card {
  padding: var(--spacing-4);
}

/* 容器查询增强 */
@supports (container-type: inline-size) {
  .container {
    container-type: inline-size;
  }

  @container (min-width: 480px) {
    .card {
      padding: var(--spacing-6);
    }
  }
}
```

### Polyfill（旧浏览器兼容）

```html
<!-- 使用 container-query-polyfill -->
<script src="https://unpkg.com/container-query-polyfill"></script>
```

---

## Tailwind CSS 配置

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      containers: {
        'xs': '0px',
        'sm': '320px',
        'md': '480px',
        'lg': '640px',
        'xl': '800px',
        '2xl': '1024px',
      },
    },
  },
  plugins: [
    require('@tailwindcss/container-queries'),
  ],
};
```

```html
<!-- 使用 Tailwind 容器查询 -->
<div class="@container">
  <div class="@sm:flex @lg:grid-cols-2">
    内容
  </div>
</div>
```

---

**相关文档：**
- [Design Token 规范](./README.md) - 总览
- [Grid 栅格系统](./grid.md) - 栅格布局
- [Breakpoints](./README.md#9-breakpoints响应式断点) - 媒体查询断点

**参考资源：**
- [MDN: CSS Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Container_Queries)
- [Can I Use: Container Queries](https://caniuse.com/css-container-queries)
- [Tailwind Container Queries](https://github.com/tailwindlabs/tailwindcss-container-queries)

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
**维护者：** 设计系统团队
