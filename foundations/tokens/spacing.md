# Spacing 间距系统 Token

> 基于 4px 基础网格的间距系统，确保所有元素对齐和垂直节奏一致。
> **公式驱动，可预测可扩展**

---

## 目录

1. [基础间距](#基础间距primitive-spacing)
2. [语义化间距](#语义化间距semantic-spacing)
3. [负间距](#负间距negative-spacing)
4. [使用示例](#使用示例)

---

## 基础间距（Primitive Spacing）

### 生成公式

\`\`\`
Spacing(n) = 4px × n
\`\`\`

### Token 清单

\`\`\`
spacing-0:    0px      # 无间距
spacing-0.5:  2px      # 微间距（图标微调）
spacing-1:    4px      # 最小单位（图标与文字）
spacing-1.5:  6px      #
spacing-2:    8px      # 小组件内边距
spacing-2.5:  10px     #
spacing-3:    12px     # 按钮内边距
spacing-4:    16px     # 卡片内边距（常用，基准）
spacing-5:    20px     #
spacing-6:    24px     # 大组件内边距
spacing-8:    32px     # 区块间距
spacing-10:   40px     #
spacing-12:   48px     # 大区块间距
spacing-16:   64px     # 页面模块间距
spacing-20:   80px     #
spacing-24:   96px     # 页面顶部间距
spacing-32:   128px    # 超大间距
spacing-40:   160px    #
spacing-48:   192px    #
spacing-64:   256px    # 特大间距
\`\`\`

### 设计策略

| n 范围 | 步长 | 用途 |
|--------|------|------|
| 0-6 | 1 | 组件内部精细间距 (0-24px) |
| 6-12 | 2 | 组件外边距、卡片间距 (24-48px) |
| 12-24 | 4 | 区块间距 (48-96px) |
| 24+ | 8 | 页面级大间距 (96px+) |

**核心理念：** 小间距需要更多选择（精细控制），大间距跳跃式增长（避免过多相似值）

---

## 语义化间距（Semantic Spacing）

### 组件内边距（Padding）

\`\`\`
spacing-padding-xs:   {spacing-2}    # 8px   (小按钮、标签)
spacing-padding-sm:   {spacing-3}    # 12px  (按钮)
spacing-padding-md:   {spacing-4}    # 16px  (卡片，推荐)
spacing-padding-lg:   {spacing-6}    # 24px  (大卡片)
spacing-padding-xl:   {spacing-8}    # 32px  (面板)
\`\`\`

### 组件外边距（Margin）

\`\`\`
spacing-margin-xs:    {spacing-2}    # 8px   (紧凑间距)
spacing-margin-sm:    {spacing-4}    # 16px  (标准间距)
spacing-margin-md:    {spacing-6}    # 24px  (表单项间距)
spacing-margin-lg:    {spacing-8}    # 32px  (区块间距)
spacing-margin-xl:    {spacing-12}   # 48px  (大区块间距)
\`\`\`

### 页面布局间距

\`\`\`
spacing-section:      {spacing-16}   # 64px  (页面模块间距)
spacing-container:    {spacing-6}    # 24px  (容器内边距)
spacing-gutter:       {spacing-4}    # 16px  (栅格间隙)
\`\`\`

---

## 负间距（Negative Spacing）

用于特殊布局场景（如偏移、重叠）

\`\`\`
spacing-n-1:    -4px
spacing-n-2:    -8px
spacing-n-3:    -12px
spacing-n-4:    -16px
spacing-n-6:    -24px
spacing-n-8:    -32px
\`\`\`

### 使用场景

- **重叠布局**：头像堆叠（\`margin-left: var(--spacing-n-2)\`）
- **偏移调整**：微调元素位置
- **抵消边距**：取消父容器多余间距

---

## CSS Variables 定义

\`\`\`css
:root {
  /* 基础间距 */
  --spacing-0: 0px;
  --spacing-0-5: 2px;
  --spacing-1: 4px;
  --spacing-1-5: 6px;
  --spacing-2: 8px;
  --spacing-2-5: 10px;
  --spacing-3: 12px;
  --spacing-4: 16px;    /* 基准 */
  --spacing-5: 20px;
  --spacing-6: 24px;
  --spacing-8: 32px;
  --spacing-10: 40px;
  --spacing-12: 48px;
  --spacing-16: 64px;
  --spacing-20: 80px;
  --spacing-24: 96px;
  --spacing-32: 128px;
  --spacing-40: 160px;
  --spacing-48: 192px;
  --spacing-64: 256px;

  /* 语义化间距 */
  --spacing-padding-xs: var(--spacing-2);
  --spacing-padding-sm: var(--spacing-3);
  --spacing-padding-md: var(--spacing-4);
  --spacing-padding-lg: var(--spacing-6);
  --spacing-padding-xl: var(--spacing-8);

  --spacing-margin-xs: var(--spacing-2);
  --spacing-margin-sm: var(--spacing-4);
  --spacing-margin-md: var(--spacing-6);
  --spacing-margin-lg: var(--spacing-8);
  --spacing-margin-xl: var(--spacing-12);

  --spacing-section: var(--spacing-16);
  --spacing-container: var(--spacing-6);
  --spacing-gutter: var(--spacing-4);

  /* 负间距 */
  --spacing-n-1: -4px;
  --spacing-n-2: -8px;
  --spacing-n-3: -12px;
  --spacing-n-4: -16px;
  --spacing-n-6: -24px;
  --spacing-n-8: -32px;
}
\`\`\`

---

## 使用示例

### 组件内边距

\`\`\`css
.button-sm {
  padding: var(--spacing-2) var(--spacing-3);  /* 8px 12px */
}

.button-md {
  padding: var(--spacing-3) var(--spacing-4);  /* 12px 16px */
}

.card {
  padding: var(--spacing-4);  /* 16px */
}

.modal {
  padding: var(--spacing-6);  /* 24px */
}
\`\`\`

### 组件间距

\`\`\`css
.form-group {
  margin-bottom: var(--spacing-6);  /* 24px 表单项间距 */
}

.section {
  margin-bottom: var(--spacing-16);  /* 64px 页面模块间距 */
}

.stack > * + * {
  margin-top: var(--spacing-4);  /* 16px 垂直堆叠间距 */
}
\`\`\`

### 栅格间隙

\`\`\`css
.grid {
  display: grid;
  gap: var(--spacing-gutter);  /* 16px */
}
\`\`\`

---

## 最佳实践

### 1. 优先使用语义化 Token

✅ **推荐：**
\`\`\`css
.card {
  padding: var(--spacing-padding-md);
  margin-bottom: var(--spacing-margin-md);
}
\`\`\`

❌ **不推荐：**
\`\`\`css
.card {
  padding: 16px;  /* 硬编码 */
  margin-bottom: 24px;
}
\`\`\`

### 2. 保持一致的间距比例

✅ **推荐：**
\`\`\`css
.section {
  padding-top: var(--spacing-16);     /* 64px */
  padding-bottom: var(--spacing-16);  /* 64px */
}
\`\`\`

❌ **不推荐：**
\`\`\`css
.section {
  padding-top: var(--spacing-16);     /* 64px */
  padding-bottom: var(--spacing-12);  /* 48px，不一致 */
}
\`\`\`

### 3. 使用 Stack 布局（推荐）

\`\`\`css
/* 垂直堆叠元素 */
.stack > * + * {
  margin-top: var(--spacing-4);
}

/* 水平堆叠元素 */
.inline-stack > * + * {
  margin-left: var(--spacing-2);
}
\`\`\`

---

**相关文档：**
- [Design Token 规范](./README.md) - 总览
- [Grid 栅格系统](./grid.md) - 栅格间隙
- [设计原理](./design-principles.md) - 数学公式

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
**维护者：** 设计系统团队
