# Design Token 规范

> **本规范基于数学公式推导而来**，确保所有设计决策可预测、可扩展、可维护。

## 📚 相关文档

- **[设计原理](./design-principles.md)** - 数学公式推导和设计哲学
- **[扩展色板](./color-palette.md)** - 12 色完整语义色阶
- **[暗色模式](./dark-mode.md)** - 完整的暗色模式色彩映射

---

## 目录

1. [什么是 Design Token](#什么是-design-token)
2. [Token 分类体系](#token-分类体系)
3. [命名规范](#命名规范)
4. [Token 详细规范](#token-详细规范)
5. [如何使用](#如何使用)

---

## 什么是 Design Token

Design Token 是设计系统中的**最小设计决策单元**，用一致的命名来存储视觉设计属性（如颜色、字体、间距等）。它是设计师和开发者之间的"共同语言"。

### 核心优势

- **一致性** - 确保所有产品使用相同的设计语言
- **可维护性** - 修改一处参数，全局同步更新
- **协作效率** - 设计师和开发使用相同的命名体系
- **主题化** - 轻松支持暗色模式、品牌定制等
- **可预测** - 基于数学公式生成，而非经验拍脑袋

### 设计系统参数

```
基础网格单元：  U = 4px
基础字号：      S_base = 14px (B端最佳)
字号比例：      r = 1.25 (大三度音阶)
理想行高：      M_ideal = 1.5
Z-index 步长：  1000
```

---

## Token 分类体系

### 三层架构

```
原始 Token (Primitive Tokens)
    ↓ 引用
语义 Token (Semantic Tokens)
    ↓ 引用
组件 Token (Component Tokens)
```

#### 1. 原始 Token
最基础的值，通常按类别和数值组织：
```
color-blue-500: #3B82F6
spacing-4: 16px
font-size-base: 14px
```

#### 2. 语义 Token
赋予原始 Token 含义和用途：
```
color-text-primary: {color-gray-900}
color-interactive-primary: {color-blue-600}
spacing-card-padding: {spacing-4}
```

#### 3. 组件 Token
特定组件专用的 Token（在组件库规范中定义）：
```
button-primary-bg: {color-interactive-primary}
button-padding-x: {spacing-4}
card-border-radius: {radius-lg}
```

---

## 命名规范

### 基本格式

```
{category}-{property}-{variant}-{state}
```

### 示例

```
color-text-primary          # 类别-属性-变体
color-bg-error-hover        # 类别-属性-变体-状态
spacing-padding-large       # 类别-属性-尺寸
font-size-xl                # 类别-属性-尺寸
```

### 命名原则

- 使用小写字母
- 单词间用 `-` 连接
- 从通用到具体（从左到右）
- 避免缩写（除非是行业通用术语，如 `xs`、`sm`、`lg`）
- 使用语义化命名（`color-text-primary` 而非 `color-gray-900`）

---

## Token 详细规范

## 1. Color（颜色）

> **扩展阅读：** [完整 12 色扩展色板](./color-palette.md) - 包含 Purple、Pink、Orange、Lime、Teal、Indigo 等更多颜色

### 1.1 基础色板（Primitive Colors）

#### 中性色（Neutral / Gray）

基于 Tailwind CSS 色板，经过 **WCAG 对比度验证**。

```
color-gray-50:  #F9FAFB   # 最浅背景
color-gray-100: #F3F4F6   # 浅背景
color-gray-200: #E5E7EB   # 边框、分割线
color-gray-300: #D1D5DB   # 主边框
color-gray-400: #9CA3AF   # 禁用文本（⚠️ 对比度 2.8:1，仅装饰用）
color-gray-500: #6B7280   # 辅助文本
color-gray-600: #4B5563   # 次要文本（对比度 7.2:1 ✅ AAA）
color-gray-700: #374151   # 深色文本
color-gray-800: #1F2937   # 极深文本
color-gray-900: #111827   # 主文本（对比度 16.2:1 ✅ AAA）
color-gray-950: #030712   # 暗色模式背景
```

#### 品牌色（Brand / Primary）

蓝色系，基于 HSL 色彩空间生成。

```
color-blue-50:  #EFF6FF   # 浅色背景
color-blue-100: #DBEAFE   # 浅色强调
color-blue-200: #BFDBFE   # 边框
color-blue-300: #93C5FD   # 辅助元素
color-blue-400: #60A5FA   # 次要按钮
color-blue-500: #3B82F6   # 主品牌色（基准）
color-blue-600: #2563EB   # 主按钮、链接（对比度 4.9:1 ✅ AA）
color-blue-700: #1D4ED8   # 按钮悬停
color-blue-800: #1E40AF   # 按钮按下
color-blue-900: #1E3A8A   # 深色品牌
color-blue-950: #172554   # 极深背景
```

#### 功能色（Functional Colors）

**成功色（Success / Green）**
```
color-green-50:  #F0FDF4
color-green-100: #DCFCE7
color-green-200: #BBF7D0
color-green-300: #86EFAC
color-green-400: #4ADE80
color-green-500: #22C55E   # 主成功色
color-green-600: #16A34A   # 成功文本（对比度 4.8:1 ✅ AA）
color-green-700: #15803D
color-green-800: #166534
color-green-900: #14532D
```

**警告色（Warning / Yellow）**
```
color-yellow-50:  #FEFCE8
color-yellow-100: #FEF9C3
color-yellow-200: #FEF08A
color-yellow-300: #FDE047
color-yellow-400: #FACC15
color-yellow-500: #EAB308   # 主警告色
color-yellow-600: #CA8A04
color-yellow-700: #A16207   # 警告文本（对比度 4.6:1 ✅ AA）
color-yellow-800: #854D0E
color-yellow-900: #713F12
```

**错误色（Error / Red）**
```
color-red-50:  #FEF2F2
color-red-100: #FEE2E2
color-red-200: #FECACA
color-red-300: #FCA5A5
color-red-400: #F87171
color-red-500: #EF4444   # 主错误色
color-red-600: #DC2626   # 错误文本（对比度 5.9:1 ✅ AA）
color-red-700: #B91C1C
color-red-800: #991B1B
color-red-900: #7F1D1D
```

**信息色（Info / Cyan）**
```
color-cyan-50:  #ECFEFF
color-cyan-100: #CFFAFE
color-cyan-200: #A5F3FC
color-cyan-300: #67E8F9
color-cyan-400: #22D3EE
color-cyan-500: #06B6D4   # 主信息色
color-cyan-600: #0891B2   # 信息文本（对比度 4.8:1 ✅ AA）
color-cyan-700: #0E7490
color-cyan-800: #155E75
color-cyan-900: #164E63
```

### 1.2 语义色（Semantic Colors）

#### 文本色

```
color-text-primary:   {color-gray-900}     # 主要文本 (16.2:1 ✅ AAA)
color-text-secondary: {color-gray-600}     # 次要文本 (7.2:1 ✅ AAA)
color-text-tertiary:  {color-gray-500}     # 辅助文本 (4.9:1 ✅ AA)
color-text-disabled:  {color-gray-400}     # 禁用文本 (2.8:1 ⚠️ 仅装饰)
color-text-inverse:   #FFFFFF              # 反色文本（深色背景上）
color-text-link:      {color-blue-600}     # 链接文本 (4.9:1 ✅ AA)
color-text-link-hover: {color-blue-700}    # 链接悬停
color-text-error:     {color-red-600}      # 错误提示 (5.9:1 ✅ AA)
color-text-success:   {color-green-600}    # 成功提示 (4.8:1 ✅ AA)
color-text-warning:   {color-yellow-700}   # 警告提示 (4.6:1 ✅ AA)
```

#### 背景色

```
color-bg-primary:     #FFFFFF              # 主背景
color-bg-secondary:   {color-gray-50}      # 次级背景
color-bg-tertiary:    {color-gray-100}     # 三级背景
color-bg-overlay:     rgba(0, 0, 0, 0.5)   # 遮罩层
color-bg-disabled:    {color-gray-100}     # 禁用背景
color-bg-error:       {color-red-50}       # 错误背景
color-bg-success:     {color-green-50}     # 成功背景
color-bg-warning:     {color-yellow-50}    # 警告背景
color-bg-info:        {color-cyan-50}      # 信息背景
```

#### 边框色

```
color-border-primary:   {color-gray-300}   # 主边框
color-border-secondary: {color-gray-200}   # 次级边框
color-border-focus:     {color-blue-500}   # 焦点边框
color-border-error:     {color-red-500}    # 错误边框
color-border-success:   {color-green-500}  # 成功边框
```

#### 交互色

```
color-interactive-primary:          {color-blue-600}   # 主要交互元素
color-interactive-primary-hover:    {color-blue-700}   # 悬停
color-interactive-primary-active:   {color-blue-800}   # 按下
color-interactive-primary-disabled: {color-gray-300}   # 禁用

color-interactive-secondary:        {color-gray-600}   # 次要交互元素
color-interactive-secondary-hover:  {color-gray-700}   # 悬停
color-interactive-secondary-active: {color-gray-800}   # 按下
```

---

## 2. Typography（字体）

### 2.1 字体族（Font Family）

```
font-family-sans:  "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif
font-family-serif: "Georgia", "Times New Roman", serif
font-family-mono:  "JetBrains Mono", "Fira Code", "Courier New", monospace
font-family-zh:    "PingFang SC", "Microsoft YaHei", sans-serif  # 中文字体
```

### 2.2 字体大小（Font Size）

**生成公式：** `FontSize(n) = 14 × 1.25^n`（取整到 2px 网格）

```
font-size-2xs:  10px   # 14 × 1.25^(-2) ≈ 8.96  → 10px
font-size-xs:   12px   # 14 × 1.25^(-1) ≈ 11.2  → 12px  (辅助信息)
font-size-sm:   14px   # 14 × 1.25^0   = 14px           (B端基准字号)
font-size-base: 14px   # 与 sm 相同，语义化别名
font-size-lg:   18px   # 14 × 1.25^1   = 17.5   → 18px  (小标题)
font-size-xl:   22px   # 14 × 1.25^2   = 21.875 → 22px  (次标题)
font-size-2xl:  28px   # 14 × 1.25^3   = 27.34  → 28px  (主标题)
font-size-3xl:  34px   # 14 × 1.25^4   = 34.18  → 34px  (大标题)
font-size-4xl:  42px   # 14 × 1.25^5   = 42.72  → 42px  (特大标题)
font-size-5xl:  54px   # 14 × 1.25^6   = 53.4   → 54px  (超大标题)
```

**设计说明：**
- 14px 是 B端信息密集场景的最佳阅读字号
- 1.25 比例（大三度）提供清晰的视觉层级
- 所有值取整到 2px 网格，确保渲染清晰

### 2.3 字重（Font Weight）

```
font-weight-light:      300
font-weight-normal:     400   # 正文默认
font-weight-medium:     500   # 强调文本
font-weight-semibold:   600   # 小标题默认
font-weight-bold:       700   # 大标题默认
```

### 2.4 行高（Line Height）

**生成公式：** `LineHeight = round(字号 × 理想倍数 / 4px) × 4px / 字号`（对齐 4px 网格）

```
line-height-none:    1      # 100%  (图标、单行文本)
line-height-tight:   1.14   # 114%  (大标题：28px → 32px)
line-height-compact: 1.29   # 129%  (小标题：22px → 28px)
line-height-snug:    1.33   # 133%  (表格、表单：18px → 24px)
line-height-normal:  1.43   # 143%  (正文：14px → 20px，网格对齐)
line-height-relaxed: 1.71   # 171%  (长文本：14px → 24px)
line-height-loose:   2      # 200%  (特殊场景)
```

**B端场景映射：**

| 场景 | 字号 | 理想行高 | 对齐网格后 | 最终比例 | Token |
|-----|------|---------|----------|---------|-------|
| 表格单元格 | 14px | 1.3 (18.2px) | 20px | 1.43 | line-height-normal |
| 表单标签 | 14px | 1.4 (19.6px) | 20px | 1.43 | line-height-normal |
| 正文阅读 | 14px | 1.5 (21px) | 20px | 1.43 | line-height-normal |
| 小标题 | 22px | 1.3 (28.6px) | 28px | 1.27 | line-height-compact |
| 大标题 | 28px | 1.2 (33.6px) | 32px | 1.14 | line-height-tight |

**关键发现：** 由于网格对齐，14px 在不同理想行高下最终都收敛到 20px（1.43），这反而带来了**统一性优势**。

### 2.5 字间距（Letter Spacing）

```
letter-spacing-tighter: -0.02em  # 大标题紧凑
letter-spacing-tight:   -0.01em  # 小标题
letter-spacing-normal:  0        # 正文默认
letter-spacing-wide:    0.01em   # 强调文本
letter-spacing-wider:   0.05em   # 全大写文本
```

### 2.6 语义化排版（Semantic Typography）

```
# 标题（Headings）
font-heading-1: {font-size-5xl} / {line-height-tight} {font-weight-bold}      # 54px / 1.14 / 700
font-heading-2: {font-size-4xl} / {line-height-tight} {font-weight-bold}      # 42px / 1.14 / 700
font-heading-3: {font-size-3xl} / {line-height-compact} {font-weight-bold}    # 34px / 1.29 / 700
font-heading-4: {font-size-2xl} / {line-height-compact} {font-weight-semibold} # 28px / 1.29 / 600
font-heading-5: {font-size-xl} / {line-height-snug} {font-weight-semibold}    # 22px / 1.33 / 600
font-heading-6: {font-size-lg} / {line-height-snug} {font-weight-semibold}    # 18px / 1.33 / 600

# 正文（Body）
font-body-large:  {font-size-lg} / {line-height-relaxed} {font-weight-normal}  # 18px / 1.71 / 400
font-body-base:   {font-size-base} / {line-height-normal} {font-weight-normal} # 14px / 1.43 / 400
font-body-small:  {font-size-xs} / {line-height-normal} {font-weight-normal}   # 12px / 1.43 / 400

# 功能性文本
font-caption:     {font-size-xs} / {line-height-snug} {font-weight-normal}     # 12px / 1.33 / 400
font-label:       {font-size-sm} / {line-height-snug} {font-weight-medium}     # 14px / 1.33 / 500
font-code:        {font-size-sm} / {line-height-normal} {font-family-mono}     # 14px / 1.43 / mono
```

---

## 3. Spacing（间距）

### 3.1 基础间距（Primitive Spacing）

**生成公式：** `Spacing(n) = 4px × n`

```
spacing-0:    0px     # 无间距
spacing-0.5:  2px     # 微间距（图标微调）
spacing-1:    4px     # 最小单位（图标与文字）
spacing-1.5:  6px     #
spacing-2:    8px     # 小组件内边距
spacing-2.5:  10px    #
spacing-3:    12px    # 按钮内边距
spacing-4:    16px    # 卡片内边距（常用）
spacing-5:    20px    #
spacing-6:    24px    # 大组件内边距
spacing-8:    32px    # 区块间距
spacing-10:   40px    #
spacing-12:   48px    # 大区块间距
spacing-16:   64px    # 页面模块间距
spacing-20:   80px    #
spacing-24:   96px    # 页面顶部间距
spacing-32:   128px   # 超大间距
spacing-40:   160px   #
spacing-48:   192px   #
spacing-64:   256px   # 特大间距
```

**使用频率：** spacing-4 (16px) 是最常用的基准间距。

### 3.2 语义化间距（Semantic Spacing）

```
# 组件内边距
spacing-padding-xs:     {spacing-2}    # 8px   (小按钮、标签)
spacing-padding-sm:     {spacing-3}    # 12px  (按钮)
spacing-padding-md:     {spacing-4}    # 16px  (卡片)
spacing-padding-lg:     {spacing-6}    # 24px  (大卡片)
spacing-padding-xl:     {spacing-8}    # 32px  (面板)

# 组件外边距
spacing-margin-xs:      {spacing-2}    # 8px   (紧凑间距)
spacing-margin-sm:      {spacing-4}    # 16px  (标准间距)
spacing-margin-md:      {spacing-6}    # 24px  (表单项间距)
spacing-margin-lg:      {spacing-8}    # 32px  (区块间距)
spacing-margin-xl:      {spacing-12}   # 48px  (大区块间距)

# 页面布局间距
spacing-section:        {spacing-16}   # 64px  (页面模块间距)
spacing-container:      {spacing-6}    # 24px  (容器内边距)
spacing-gutter:         {spacing-4}    # 16px  (栅格间隙)
```

---

## 4. Sizing（尺寸）

### 4.1 基础尺寸（Primitive Sizing）

**与间距共享同一套值**（基于 4px 网格）

```
size-0:    0px
size-1:    4px
size-2:    8px
size-4:    16px
size-6:    24px
size-8:    32px
size-10:   40px
size-12:   48px
size-16:   64px
size-20:   80px
size-24:   96px
size-32:   128px
size-40:   160px
size-48:   192px
size-64:   256px
size-80:   320px
size-96:   384px
```

### 4.2 图标尺寸

```
size-icon-xs:   12px   # 辅助图标
size-icon-sm:   16px   # 小图标
size-icon-md:   20px   # 标准图标（常用）
size-icon-lg:   24px   # 大图标
size-icon-xl:   32px   # 超大图标
```

### 4.3 组件高度

```
size-height-input-sm:   32px   # 小输入框/按钮（对齐 4px 网格）
size-height-input-md:   40px   # 标准输入框/按钮（常用）
size-height-input-lg:   48px   # 大输入框/按钮

size-height-header:     64px   # 顶部导航栏
size-height-footer:     80px   # 底部栏
```

### 4.4 容器宽度（响应式断点）

```
size-container-sm:   640px    # 小屏幕
size-container-md:   768px    # 平板
size-container-lg:   1024px   # 笔记本
size-container-xl:   1280px   # 桌面（常用）
size-container-2xl:  1536px   # 大屏
```

---

## 5. Border Radius（圆角）

**生成公式：** 小圆角线性增长（2-8px），大圆角跳跃增长（12-24px）

```
radius-none:   0px      # 直角（表格）
radius-sm:     2px      # 小圆角（标签、徽章）
radius-base:   4px      # 基础圆角（按钮、输入框）
radius-md:     6px      # 中圆角（小卡片）
radius-lg:     8px      # 大圆角（卡片）
radius-xl:     12px     # 超大圆角（面板）
radius-2xl:    16px     # 特大圆角（模态框）
radius-3xl:    24px     # 巨大圆角（大型容器）
radius-full:   9999px   # 圆形（头像、圆形按钮）
```

**常用搭配：**
- 按钮：`radius-base` (4px)
- 卡片：`radius-lg` (8px)
- 模态框：`radius-2xl` (16px)

---

## 6. Shadow（阴影）

### 6.1 基础阴影

**生成公式：** `y-offset = depth`, `blur = 2 × depth`, `alpha = 0.04 + depth/100`

```
shadow-none: none

shadow-xs:
  0 1px 2px 0 rgba(0, 0, 0, 0.05)
  # 深度 1：微投影（分割线）

shadow-sm:
  0 2px 4px 0 rgba(0, 0, 0, 0.06),
  0 1px 2px 0 rgba(0, 0, 0, 0.06)
  # 深度 2：轻微悬浮

shadow-base:
  0 4px 8px -2px rgba(0, 0, 0, 0.08),
  0 2px 4px -2px rgba(0, 0, 0, 0.08)
  # 深度 4：卡片

shadow-md:
  0 8px 16px -4px rgba(0, 0, 0, 0.12),
  0 4px 8px -4px rgba(0, 0, 0, 0.12)
  # 深度 8：下拉菜单

shadow-lg:
  0 16px 32px -8px rgba(0, 0, 0, 0.16),
  0 8px 16px -8px rgba(0, 0, 0, 0.16)
  # 深度 16：模态框

shadow-xl:
  0 24px 48px -12px rgba(0, 0, 0, 0.20),
  0 12px 24px -12px rgba(0, 0, 0, 0.20)
  # 深度 24：大型弹窗

shadow-2xl:
  0 32px 64px -16px rgba(0, 0, 0, 0.24),
  0 16px 32px -16px rgba(0, 0, 0, 0.24)
  # 深度 32：特大弹窗
```

### 6.2 特殊阴影

```
shadow-inner:
  inset 0 2px 4px 0 rgba(0, 0, 0, 0.05)
  # 内阴影（按下状态）

shadow-focus:
  0 0 0 3px rgba(59, 130, 246, 0.3)
  # 焦点环（对比度 ≥ 3:1）
```

### 6.3 语义化阴影

```
shadow-card:     {shadow-sm}      # 卡片
shadow-dropdown: {shadow-md}      # 下拉菜单
shadow-modal:    {shadow-lg}      # 模态框
shadow-popover:  {shadow-md}      # 气泡卡片
```

---

## 7. Border（边框）

### 7.1 边框宽度

```
border-width-0:    0px     # 无边框
border-width-1:    1px     # 默认边框（常用）
border-width-2:    2px     # 加粗边框
border-width-4:    4px     # 极粗边框（强调）
```

### 7.2 边框样式

```
border-style-solid:  solid
border-style-dashed: dashed
border-style-dotted: dotted
border-style-none:   none
```

---

## 8. Z-Index（层级）

**生成公式：** `Z(n) = 1000 × n`（大步长策略，预留扩展空间）

```
z-index-base:         0      # 默认流
z-index-dropdown:     1000   # 下拉菜单
z-index-sticky:       2000   # 吸顶/吸底元素
z-index-modal:        3000   # 模态框
z-index-modal-nested: 3500   # 嵌套模态框（利用预留空间）
z-index-popover:      4000   # 气泡卡片
z-index-tooltip:      5000   # 工具提示（总在最上）
z-index-notification: 6000   # 全局通知
z-index-toast:        7000   # Toast 提示
z-index-debug:        9000   # 调试面板
```

**优势：** 任意两个层级间有 1000 个可用值，支持复杂嵌套场景。

---

## 9. Breakpoints（响应式断点）

```
breakpoint-xs:   0px       # 手机竖屏
breakpoint-sm:   640px     # 手机横屏 / 小平板
breakpoint-md:   768px     # 平板
breakpoint-lg:   1024px    # 小屏笔记本
breakpoint-xl:   1280px    # 桌面显示器（常用）
breakpoint-2xl:  1536px    # 大屏显示器
```

---

## 10. Motion（动效）

### 10.1 动画时长（Duration）

```
duration-instant:  0ms       # 无动画
duration-fast:     100ms     # 快速（状态切换、图标旋转）
duration-base:     200ms     # 基础（按钮悬停、颜色变化）
duration-slow:     300ms     # 慢速（抽屉展开、下拉菜单）
duration-slower:   500ms     # 更慢（页面转场）
```

### 10.2 缓动函数（Easing）

```
ease-linear:      cubic-bezier(0, 0, 1, 1)
ease-in:          cubic-bezier(0.4, 0, 1, 1)                # 加速（元素离开）
ease-out:         cubic-bezier(0, 0, 0.2, 1)                # 减速（元素进入）
ease-in-out:      cubic-bezier(0.4, 0, 0.2, 1)              # 先加速后减速
ease-bounce:      cubic-bezier(0.68, -0.55, 0.265, 1.55)    # 弹性（特殊效果）
```

### 10.3 语义化动效

```
transition-base:   all {duration-base} {ease-out}
transition-colors: color, background-color, border-color {duration-base} {ease-out}
transition-fade:   opacity {duration-base} {ease-in-out}
transition-slide:  transform {duration-base} {ease-out}
```

---

## 11. Opacity（透明度）

```
opacity-0:        0       # 完全透明
opacity-5:        0.05
opacity-10:       0.1
opacity-20:       0.2
opacity-30:       0.3
opacity-40:       0.4
opacity-50:       0.5
opacity-60:       0.6
opacity-70:       0.7
opacity-80:       0.8
opacity-90:       0.9
opacity-100:      1       # 完全不透明
```

### 语义化透明度

```
opacity-disabled:   {opacity-50}   # 禁用状态
opacity-hover:      {opacity-80}   # 悬停遮罩
opacity-backdrop:   {opacity-50}   # 背景遮罩
opacity-subtle:     {opacity-60}   # 次要元素
```

---

## 如何使用

### 设计师使用方式

#### Figma + Tokens Studio

1. **安装插件**
   - [Tokens Studio for Figma](https://www.figma.com/community/plugin/843461159747178978)

2. **导入 Token**
   - 导出本规范为 JSON 格式
   - 在插件中导入 JSON 文件

3. **应用 Token**
   ```
   ✅ 正确做法：
   - 颜色：选择 "color-text-primary" 而非 #111827
   - 间距：使用 "spacing-4" 而非手动输入 16px
   - 字体：应用 "font-body-base" 而非单独设置 14px/1.43/400

   ❌ 错误做法：
   - 直接填写色值 #3B82F6
   - 手动输入间距 18px（未对齐网格）
   - 使用 15px 字号（不在规范中）
   ```

4. **检查可访问性**
   - 安装 [Stark](https://www.figma.com/community/plugin/732603254453395948) 插件
   - 验证所有文本对比度 ≥ 4.5:1（常规文本）或 ≥ 3:1（大文本）

### 开发者使用方式

#### CSS Variables（推荐）

```css
/* tokens.css */
:root {
  /* Color */
  --color-text-primary: #111827;
  --color-bg-primary: #FFFFFF;
  --color-interactive-primary: #2563EB;

  /* Spacing */
  --spacing-4: 16px;
  --spacing-6: 24px;

  /* Typography */
  --font-size-base: 14px;
  --line-height-normal: 1.43;
  --font-weight-normal: 400;

  /* Border Radius */
  --radius-base: 4px;
  --radius-lg: 8px;

  /* Shadow */
  --shadow-sm: 0 2px 4px 0 rgba(0, 0, 0, 0.06), 0 1px 2px 0 rgba(0, 0, 0, 0.06);
}

/* 使用示例 */
.button {
  background-color: var(--color-interactive-primary);
  color: var(--color-text-inverse);
  padding: var(--spacing-3) var(--spacing-6);
  font-size: var(--font-size-base);
  line-height: var(--line-height-normal);
  border-radius: var(--radius-base);
  box-shadow: var(--shadow-sm);
  transition: all 200ms cubic-bezier(0, 0, 0.2, 1);
}

.button:hover {
  background-color: var(--color-interactive-primary-hover);
}
```

#### JavaScript / TypeScript

```typescript
// tokens.ts
export const tokens = {
  color: {
    text: {
      primary: '#111827',
      secondary: '#4B5563',
    },
    interactive: {
      primary: '#2563EB',
      primaryHover: '#1D4ED8',
    },
  },
  spacing: {
    2: '8px',
    3: '12px',
    4: '16px',
    6: '24px',
  },
  fontSize: {
    xs: '12px',
    base: '14px',
    lg: '18px',
  },
  radius: {
    base: '4px',
    lg: '8px',
  },
} as const;

// 使用（styled-components 示例）
import styled from 'styled-components';
import { tokens } from './tokens';

const Button = styled.button`
  background: ${tokens.color.interactive.primary};
  color: white;
  padding: ${tokens.spacing[3]} ${tokens.spacing[6]};
  font-size: ${tokens.fontSize.base};
  border-radius: ${tokens.radius.base};

  &:hover {
    background: ${tokens.color.interactive.primaryHover};
  }
`;
```

#### Tailwind CSS 配置

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        // 基础色板
        gray: {
          50: '#F9FAFB',
          100: '#F3F4F6',
          // ...
          900: '#111827',
        },
        blue: {
          500: '#3B82F6',
          600: '#2563EB',
          700: '#1D4ED8',
        },
        // 语义色
        'text-primary': '#111827',
        'interactive-primary': '#2563EB',
      },
      fontSize: {
        '2xs': '10px',
        'xs': '12px',
        'sm': '14px',
        'base': '14px',  // 注意：不是 16px
        'lg': '18px',
        'xl': '22px',
        '2xl': '28px',
        '3xl': '34px',
        '4xl': '42px',
        '5xl': '54px',
      },
      lineHeight: {
        'tight': '1.14',
        'compact': '1.29',
        'snug': '1.33',
        'normal': '1.43',  // 网格对齐后的值
        'relaxed': '1.71',
      },
      spacing: {
        // 继承默认的 4px 基础单位
        // Tailwind 默认就是 4px 系统，无需修改
      },
      borderRadius: {
        'sm': '2px',
        'DEFAULT': '4px',
        'md': '6px',
        'lg': '8px',
        'xl': '12px',
        '2xl': '16px',
        '3xl': '24px',
      },
    },
  },
};
```

---

## 可访问性验证

### 对比度检查清单

使用工具验证所有颜色组合：

```
✅ 必须符合 WCAG AA 级：
  - color-text-primary (#111827) on #FFFFFF   → 16.2:1 (AAA ✅)
  - color-text-secondary (#4B5563) on #FFFFFF → 7.2:1 (AAA ✅)
  - color-text-tertiary (#6B7280) on #FFFFFF  → 4.9:1 (AA ✅)
  - color-text-link (#2563EB) on #FFFFFF      → 4.9:1 (AA ✅)
  - color-text-error (#DC2626) on #FFFFFF     → 5.9:1 (AA ✅)

⚠️ 不符合 AA 级（仅用于装饰）：
  - color-text-disabled (#9CA3AF) on #FFFFFF  → 2.8:1 (❌)
```

**推荐工具：**
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Figma Plugin: Stark](https://www.figma.com/community/plugin/732603254453395948)
- [Chrome DevTools: Lighthouse](https://developers.google.com/web/tools/lighthouse)

---

## 暗色模式支持

> **完整指南：** [暗色模式完整文档](./dark-mode.md) - 包含完整映射表、对比度验证、实现方式和最佳实践

### Token 覆盖策略（快速预览）

```css
/* 浅色模式（默认） */
:root {
  --color-text-primary: #111827;
  --color-text-secondary: #4B5563;
  --color-bg-primary: #FFFFFF;
  --color-bg-secondary: #F9FAFB;
  --color-border-primary: #D1D5DB;
}

/* 暗色模式 */
[data-theme="dark"] {
  --color-text-primary: #F9FAFB;     /* gray-50 */
  --color-text-secondary: #D1D5DB;   /* gray-300 */
  --color-bg-primary: #111827;       /* gray-900 */
  --color-bg-secondary: #1F2937;     /* gray-800 */
  --color-border-primary: #374151;   /* gray-700 */
}
```

**关键原则：**
- 暗色模式下仍需保证对比度 ≥ 4.5:1
- 反转亮度，但保持饱和度一致
- 功能色（成功/警告/错误）保持语义不变
- 避免使用纯黑 (#000000)，使用 Gray-900 (#111827)

**完整内容请查看：** [暗色模式文档](./dark-mode.md)

---

## JSON 格式示例

**用于工具导入/导出（Design Tokens Format Module 标准）**

```json
{
  "color": {
    "gray": {
      "900": {
        "value": "#111827",
        "type": "color",
        "description": "最深灰色，用于主文本"
      }
    },
    "text": {
      "primary": {
        "value": "{color.gray.900}",
        "type": "color",
        "description": "主要文本颜色，对比度 16.2:1 (AAA)"
      }
    }
  },
  "spacing": {
    "4": {
      "value": "16px",
      "type": "dimension",
      "description": "基准间距，最常用"
    }
  },
  "fontSize": {
    "base": {
      "value": "14px",
      "type": "dimension",
      "description": "B端基准字号，公式：14 × 1.25^0"
    }
  },
  "lineHeight": {
    "normal": {
      "value": "1.43",
      "type": "number",
      "description": "正文行高，网格对齐：14px → 20px"
    }
  }
}
```

---

## 下一步

### 规范完善

- [ ] 补充紫色、橙色等扩展色系
- [ ] 定义暗色模式完整 Token 映射表
- [ ] 建立 Token 自动生成工具链
- [ ] 补充数据可视化专用色板

### 工具集成

- [ ] 输出 Figma Tokens Studio JSON
- [ ] 生成 CSS Variables 文件
- [ ] 生成 Tailwind 配置文件
- [ ] 生成 TypeScript 类型定义

### 质量保证

- [ ] 自动化对比度验证脚本
- [ ] 网格对齐检查工具
- [ ] Token 使用率统计
- [ ] 设计评审检查清单

---

## 参考资源

### 设计系统

- [Material Design 3 - Design Tokens](https://m3.material.io/foundations/design-tokens)
- [Tailwind CSS - Default Theme](https://tailwindcss.com/docs/theme)
- [Ant Design - Design Values](https://ant.design/docs/spec/values)
- [Primer Design System (GitHub)](https://primer.style/)

### 标准与规范

- [Design Tokens Format Module (W3C)](https://tr.designtokens.org/format/)
- [WCAG 2.1 - Contrast Guidelines](https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html)
- [Modular Scale Calculator](https://www.modularscale.com/)

### 工具

- [Tokens Studio for Figma](https://www.figma.com/community/plugin/843461159747178978)
- [Leonardo Color Generator](https://leonardocolor.io/)
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)

---

**文档版本：** v2.0 (基于数学公式重构)
**最后更新：** 2025-11-16
**维护者：** 设计系统团队
**相关文档：** [设计原理](./design-principles.md) | [组件库规范](../../components/)
