# Grid 栅格系统 Token

> 响应式栅格布局系统，基于 12 列标准和灵活的间隙配置。
> **基于 4px 基础网格对齐**

---

## 目录

1. [栅格列数配置](#栅格列数配置)
2. [栅格间隙](#栅格间隙)
3. [容器宽度](#容器宽度)
4. [列宽计算公式](#列宽计算公式)
5. [响应式断点映射](#响应式断点映射)
6. [CSS 实现](#css-实现)
7. [使用示例](#使用示例)

---

## 栅格列数配置

### B端推荐：12 列 + 24 列双系统

```
grid-columns:        12     # 标准 12 列（通用布局）
grid-columns-dense:  24     # 密集 24 列（B端复杂表单/表格）
```

**为什么 B端需要 24 列？**

| 列数 | 优势 | 劣势 | 适用场景 |
|-----|------|------|---------|
| **12** | 简洁，常用布局快速实现 | 复杂表单受限 | 卡片、简单布局 |
| **24** | **极致灵活，精细控制** | 稍复杂 | **复杂表单/表格（B端推荐）** |

**12 列可实现的布局比例：**
- 1/12 (8.33%) - 小图标、数字指标
- 2/12 = 1/6 (16.67%) - 侧边栏图标
- 3/12 = 1/4 (25%) - 四列卡片
- 4/12 = 1/3 (33.33%) - 三列卡片（常用）
- 6/12 = 1/2 (50%) - 两列布局（常用）
- 8/12 = 2/3 (66.67%) - 主内容区
- 12/12 (100%) - 全宽

**24 列额外优势（B端场景）：**
- 5 列表单：每列 span 4.8 → **24列可整除为 span 4-5**
- 7 列数据网格：**24列可实现更细粒度**
- 标签 + 输入框：span 4 (标签) + span 8 (输入框) = **精确 1/6 + 1/3**
- 复杂仪表盘：可实现 6/8/12 等多种组合

**Ant Design 为什么用 24 列？**
- B端表单经常需要 "标签宽度 : 输入框宽度 = 1 : 2" 的布局
- 24 = 2³ × 3，可被 1,2,3,4,6,8,12,24 整除
- 支持 5列、7列等特殊场景

### 响应式列数变化

#### 12 列系统（默认）

```
grid-columns-xs:   4      # 手机竖屏（≥ 0px）
grid-columns-sm:   4      # 手机横屏（≥ 640px）
grid-columns-md:   8      # 平板（≥ 768px）
grid-columns-lg:   12     # 笔记本（≥ 1024px）
grid-columns-xl:   12     # 桌面（≥ 1280px）
grid-columns-2xl:  12     # 大屏（≥ 1536px）
```

#### 24 列系统（B端密集布局）

```
grid-columns-dense-xs:   4      # 手机竖屏（≥ 0px）
grid-columns-dense-sm:   8      # 手机横屏（≥ 640px）
grid-columns-dense-md:   12     # 平板（≥ 768px）
grid-columns-dense-lg:   24     # 笔记本（≥ 1024px，启用 24 列）
grid-columns-dense-xl:   24     # 桌面（≥ 1280px）
grid-columns-dense-2xl:  24     # 大屏（≥ 1536px）
```

**使用策略：**
- 移动端：统一使用 4 列（简化布局）
- 平板：12 列或 8 列（过渡阶段）
- 桌面（lg+）：**24 列**（B端完整功能）

---

## 栅格间隙

### 基础间隙（Gutter）

**生成公式：** 基于 `spacing` Token

```
grid-gutter-xs:   8px      # {spacing-2}  手机（紧凑）
grid-gutter-sm:   12px     # {spacing-3}  手机横屏
grid-gutter-md:   16px     # {spacing-4}  平板（推荐基准）
grid-gutter-lg:   24px     # {spacing-6}  桌面（宽松）
grid-gutter-xl:   32px     # {spacing-8}  大屏（超宽松）
```

### 语义化间隙

```
grid-gutter:           {grid-gutter-md}     # 16px  默认间隙（别名）
grid-gutter-compact:   {grid-gutter-xs}     # 8px   紧凑模式
grid-gutter-relaxed:   {grid-gutter-lg}     # 24px  宽松模式
```

### 响应式间隙策略

```css
/* 移动优先，逐级扩大间隙 */
@media (min-width: 0px)    { gap: 8px;  }  /* xs */
@media (min-width: 640px)  { gap: 12px; }  /* sm */
@media (min-width: 768px)  { gap: 16px; }  /* md */
@media (min-width: 1024px) { gap: 24px; }  /* lg */
@media (min-width: 1280px) { gap: 24px; }  /* xl */
```

---

## 容器宽度

### 最大容器宽度（Max Width）

```
grid-container-xs:   100%      # 手机全宽
grid-container-sm:   640px     # 手机横屏最大宽度
grid-container-md:   768px     # 平板最大宽度
grid-container-lg:   1024px    # 笔记本最大宽度
grid-container-xl:   1280px    # 桌面最大宽度（常用）
grid-container-2xl:  1536px    # 大屏最大宽度
grid-container-full: 100%      # 无限制（流式布局）
```

### 容器内边距（Container Padding）

```
grid-container-padding-xs:   16px      # {spacing-4}  手机
grid-container-padding-sm:   20px      # {spacing-5}  手机横屏
grid-container-padding-md:   24px      # {spacing-6}  平板
grid-container-padding-lg:   32px      # {spacing-8}  桌面
grid-container-padding-xl:   40px      # {spacing-10} 大屏
```

---

## 列宽计算公式

### 数学模型

```
单列宽度 = (容器宽度 - (列数 - 1) × 间隙) ÷ 列数
```

**示例计算：** 12 列，1280px 容器，24px 间隙

```
单列宽 = (1280px - 11 × 24px) ÷ 12
       = (1280px - 264px) ÷ 12
       = 1016px ÷ 12
       ≈ 84.67px

4 列宽 = 4 × 84.67px + 3 × 24px
       = 338.68px + 72px
       = 410.68px
```

### CSS Grid 自动计算（推荐）

```css
/* CSS Grid 自动处理列宽计算 */
.grid-container {
  display: grid;
  grid-template-columns: repeat(12, 1fr);  /* 12 等分 */
  gap: 24px;                               /* 间隙 */
}

.span-4 {
  grid-column: span 4;  /* 占据 4 列 */
}
```

---

## 响应式断点映射

### Token 定义

```
breakpoint-xs:   0px       # 手机竖屏（默认）
breakpoint-sm:   640px     # 手机横屏 / 小平板
breakpoint-md:   768px     # 平板
breakpoint-lg:   1024px    # 小屏笔记本
breakpoint-xl:   1280px    # 桌面显示器（常用）
breakpoint-2xl:  1536px    # 大屏显示器
```

### 完整映射表

| 断点 | 宽度 | 列数 | 间隙 | 容器最大宽度 | 容器内边距 | 典型设备 |
|-----|------|-----|------|------------|-----------|---------|
| **xs** | ≥ 0px | 4 | 8px | 100% | 16px | iPhone SE, Galaxy S |
| **sm** | ≥ 640px | 4 | 12px | 640px | 20px | iPhone 14, Pixel |
| **md** | ≥ 768px | 8 | 16px | 768px | 24px | iPad Mini, Tab S |
| **lg** | ≥ 1024px | 12 | 24px | 1024px | 32px | iPad Pro, Surface |
| **xl** | ≥ 1280px | 12 | 24px | 1280px | 32px | MacBook, 桌面 |
| **2xl** | ≥ 1536px | 12 | 32px | 1536px | 40px | 大屏显示器 |

---

## CSS 实现

### CSS Grid 实现（推荐）

```css
/* ========== 基础栅格容器 ========== */
:root {
  /* 栅格配置 */
  --grid-columns: 12;
  --grid-gutter: 16px;      /* md */
  --grid-container-max-width: 1280px;
  --grid-container-padding: 24px;
}

/* 栅格容器 */
.grid-container {
  display: grid;
  grid-template-columns: repeat(var(--grid-columns), 1fr);
  gap: var(--grid-gutter);
  max-width: var(--grid-container-max-width);
  margin: 0 auto;
  padding: 0 var(--grid-container-padding);
}

/* ========== 列跨度工具类 ========== */
.col-1  { grid-column: span 1; }
.col-2  { grid-column: span 2; }
.col-3  { grid-column: span 3; }
.col-4  { grid-column: span 4; }
.col-5  { grid-column: span 5; }
.col-6  { grid-column: span 6; }
.col-7  { grid-column: span 7; }
.col-8  { grid-column: span 8; }
.col-9  { grid-column: span 9; }
.col-10 { grid-column: span 10; }
.col-11 { grid-column: span 11; }
.col-12 { grid-column: span 12; }

/* ========== 响应式配置 ========== */
/* 移动端（xs）：4 列，8px 间隙 */
@media (min-width: 0px) {
  :root {
    --grid-columns: 4;
    --grid-gutter: 8px;
    --grid-container-padding: 16px;
  }
}

/* 手机横屏（sm）：4 列，12px 间隙 */
@media (min-width: 640px) {
  :root {
    --grid-columns: 4;
    --grid-gutter: 12px;
    --grid-container-padding: 20px;
  }
}

/* 平板（md）：8 列，16px 间隙 */
@media (min-width: 768px) {
  :root {
    --grid-columns: 8;
    --grid-gutter: 16px;
    --grid-container-padding: 24px;
  }
}

/* 笔记本/桌面（lg+）：12 列，24px 间隙 */
@media (min-width: 1024px) {
  :root {
    --grid-columns: 12;
    --grid-gutter: 24px;
    --grid-container-padding: 32px;
  }
}

/* 大屏（2xl）：12 列，32px 间隙 */
@media (min-width: 1536px) {
  :root {
    --grid-gutter: 32px;
    --grid-container-padding: 40px;
  }
}

/* ========== 响应式列跨度 ========== */
/* 示例：md:col-6 在平板及以上占 6 列 */
@media (min-width: 768px) {
  .md\:col-1  { grid-column: span 1; }
  .md\:col-2  { grid-column: span 2; }
  .md\:col-3  { grid-column: span 3; }
  .md\:col-4  { grid-column: span 4; }
  .md\:col-6  { grid-column: span 6; }
  .md\:col-8  { grid-column: span 8; }
  .md\:col-12 { grid-column: span 12; }
}

@media (min-width: 1024px) {
  .lg\:col-1  { grid-column: span 1; }
  .lg\:col-2  { grid-column: span 2; }
  .lg\:col-3  { grid-column: span 3; }
  .lg\:col-4  { grid-column: span 4; }
  .lg\:col-6  { grid-column: span 6; }
  .lg\:col-8  { grid-column: span 8; }
  .lg\:col-9  { grid-column: span 9; }
  .lg\:col-12 { grid-column: span 12; }
}
```

### Flexbox 实现（兼容方案）

```css
/* 适用于需要支持旧浏览器的场景 */
.grid-container-flex {
  display: flex;
  flex-wrap: wrap;
  margin: 0 calc(var(--grid-gutter) / -2);
  max-width: var(--grid-container-max-width);
}

.col-flex {
  padding: 0 calc(var(--grid-gutter) / 2);
  margin-bottom: var(--grid-gutter);
}

/* 列宽百分比计算 */
.col-flex-1  { width: 8.333%;  }  /* 1/12 */
.col-flex-2  { width: 16.667%; }  /* 2/12 */
.col-flex-3  { width: 25%;     }  /* 3/12 */
.col-flex-4  { width: 33.333%; }  /* 4/12 */
.col-flex-6  { width: 50%;     }  /* 6/12 */
.col-flex-8  { width: 66.667%; }  /* 8/12 */
.col-flex-12 { width: 100%;    }  /* 12/12 */
```

---

## 使用示例

### 示例 1：三列卡片布局

```html
<div class="grid-container">
  <div class="col-12 md:col-4">卡片 1</div>
  <div class="col-12 md:col-4">卡片 2</div>
  <div class="col-12 md:col-4">卡片 3</div>
</div>
```

**响应式行为：**
- 手机（xs/sm）：每行 1 个卡片（12/4 = 3 列，但只有 4 列总数）
- 平板（md）：每行 1 个卡片（8 列总数，每个占 4 列）
- 桌面（lg+）：每行 3 个卡片（12 列总数，每个占 4 列）

### 示例 2：主内容 + 侧边栏

```html
<div class="grid-container">
  <!-- 主内容区 -->
  <main class="col-12 lg:col-9">
    主要内容
  </main>

  <!-- 侧边栏 -->
  <aside class="col-12 lg:col-3">
    侧边栏
  </aside>
</div>
```

**响应式行为：**
- 手机/平板：上下堆叠（各占 100%）
- 桌面：9:3 比例（75% : 25%）

### 示例 3：仪表盘指标卡片

```html
<div class="grid-container">
  <!-- 4 个指标卡片 -->
  <div class="col-6 md:col-4 lg:col-3">指标 1</div>
  <div class="col-6 md:col-4 lg:col-3">指标 2</div>
  <div class="col-6 md:col-4 lg:col-3">指标 3</div>
  <div class="col-6 md:col-4 lg:col-3">指标 4</div>

  <!-- 图表区域 -->
  <div class="col-12 lg:col-8">主图表</div>
  <div class="col-12 lg:col-4">辅助图表</div>
</div>
```

**响应式行为：**
- 手机（xs/sm）：每行 2 个指标（4 列总数，每个占 2 列）
- 平板（md）：每行 2 个指标（8 列总数，每个占 4 列）
- 桌面（lg+）：每行 4 个指标（12 列总数，每个占 3 列）

### 示例 4：复杂表单布局

```html
<div class="grid-container">
  <!-- 全宽标题 -->
  <div class="col-12">
    <h2>用户信息</h2>
  </div>

  <!-- 两列输入框 -->
  <div class="col-12 md:col-6">
    <label>姓名</label>
    <input type="text">
  </div>
  <div class="col-12 md:col-6">
    <label>邮箱</label>
    <input type="email">
  </div>

  <!-- 三列输入框 -->
  <div class="col-12 md:col-4">
    <label>国家</label>
    <select>...</select>
  </div>
  <div class="col-12 md:col-4">
    <label>省份</label>
    <select>...</select>
  </div>
  <div class="col-12 md:col-4">
    <label>城市</label>
    <select>...</select>
  </div>

  <!-- 全宽备注 -->
  <div class="col-12">
    <label>备注</label>
    <textarea></textarea>
  </div>

  <!-- 按钮右对齐 -->
  <div class="col-12 md:col-6 md:col-start-7">
    <button>提交</button>
  </div>
</div>
```

---

## Tailwind CSS 配置

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      gridTemplateColumns: {
        '4': 'repeat(4, minmax(0, 1fr))',
        '8': 'repeat(8, minmax(0, 1fr))',
        '12': 'repeat(12, minmax(0, 1fr))',
      },
      gap: {
        'grid-xs': '8px',
        'grid-sm': '12px',
        'grid-md': '16px',
        'grid-lg': '24px',
        'grid-xl': '32px',
      },
      maxWidth: {
        'container-sm': '640px',
        'container-md': '768px',
        'container-lg': '1024px',
        'container-xl': '1280px',
        'container-2xl': '1536px',
      },
    },
  },
};
```

---

## 最佳实践

### 1. 移动优先设计

**✅ 推荐：**
```html
<!-- 默认全宽，桌面端 1/3 宽 -->
<div class="col-12 lg:col-4"></div>
```

**❌ 不推荐：**
```html
<!-- 桌面优先，移动端需要覆盖 -->
<div class="col-4 xs:col-12"></div>
```

### 2. 避免嵌套栅格

**✅ 推荐：**
```html
<!-- 扁平化结构 -->
<div class="grid-container">
  <div class="col-8">...</div>
  <div class="col-4">...</div>
</div>
```

**❌ 不推荐（除非必要）：**
```html
<!-- 嵌套栅格增加复杂度 -->
<div class="grid-container">
  <div class="col-8">
    <div class="grid-container">
      <div class="col-6">...</div>
    </div>
  </div>
</div>
```

### 3. 使用语义化类名

**✅ 推荐：**
```html
<div class="product-grid col-12 md:col-6 lg:col-4">
  <!-- 产品卡片 -->
</div>
```

**❌ 不推荐：**
```html
<div class="col-12 md:col-6 lg:col-4">
  <!-- 难以理解用途 -->
</div>
```

---

## 与其他 Token 的关系

### 间隙引用 Spacing Token

```
grid-gutter-xs  → {spacing-2}   (8px)
grid-gutter-sm  → {spacing-3}   (12px)
grid-gutter-md  → {spacing-4}   (16px)
grid-gutter-lg  → {spacing-6}   (24px)
grid-gutter-xl  → {spacing-8}   (32px)
```

### 断点引用 Breakpoints Token

```
grid 响应式 → {breakpoint-xs/sm/md/lg/xl/2xl}
```

### 容器宽度引用 Sizing Token

```
grid-container-* → {size-container-*/breakpoint-*}
```

---

**相关文档：**
- [Design Token 规范](./README.md) - 总览
- [Spacing Token](./spacing.md) - 间距系统
- [Breakpoints](./README.md#9-breakpoints响应式断点) - 响应式断点
- [Container Queries](./container-queries.md) - 现代容器查询

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
**维护者：** 设计系统团队
