# Design Token 规范

> **本规范基于数学公式推导而来**，确保所有设计决策可预测、可扩展、可维护。

## 📚 相关文档

### 核心文档

- **[设计原理](./design-principles.md)** - 数学公式推导和设计哲学
- **[扩展色板](./color-palette.md)** - Material Design 标准 17 色完整色阶
- **[暗色模式](./dark-mode.md)** - 完整的暗色模式色彩映射

### 专项文档

- **[Typography 字体系统](./typography.md)** - 字体族、字号、字重、行高完整规范
- **[Spacing 间距系统](./spacing.md)** - 基于 4px 网格的间距体系
- **[Grid 栅格系统](./grid.md)** - 12/24 列双栅格系统（B端推荐 24 列）
- **[Motion 动效系统](./motion.md)** - 动画时长、缓动函数、过渡效果
- **[Container Queries 容器查询](./container-queries.md)** - 现代组件级响应式方案

### 快速参考

- **[📋 Design Token 完整参考](./tokens-reference.md)** - 所有 Token 的完整列表（793 行）
- **[🎨 Figma 导入指南](./figma-import-guide.md)** - Tokens Studio 插件完整导入教程
- **[📦 tokens.json](./tokens.json)** - Tokens Studio 标准格式文件（可直接导入）

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

> **扩展阅读：** [完整 Material Design 色板](./color-palette.md) - 包含 17 种标准色彩（Red、Pink、Purple、Deep Purple、Indigo、Blue、Light Blue、Cyan、Teal、Green、Light Green、Lime、Yellow、Amber、Orange、Deep Orange、Grey）

### 1.1 基础色板（Primitive Colors）

> **基于 Material Design 标准色板系统**，所有颜色经过 **WCAG 对比度验证**。

#### 中性色（Grey）

```
color-grey-50:  #FAFAFA   # 最浅背景 (1.09:1)
color-grey-100: #F5F5F5   # 浅背景 (1.18:1)
color-grey-200: #EEEEEE   # 极浅边框 (1.29:1)
color-grey-300: #E0E0E0   # 浅边框 (1.53:1)
color-grey-400: #BDBDBD   # 禁用文本 (2.26:1 ⚠️ 仅装饰用)
color-grey-500: #9E9E9E   # 辅助文本 (3.15:1 ⚠️)
color-grey-600: #757575   # 次要文本 (4.68:1 ✅ AA)
color-grey-700: #616161   # 深色文本 (6.24:1 ✅ AA)
color-grey-800: #424242   # 极深文本 (10.13:1 ✅ AAA)
color-grey-900: #212121   # 主文本 (16.1:1 ✅ AAA)
```

**注意：** Material Design 使用 "Grey" 而非 "Gray"。

#### 品牌色（Brand / Primary - Blue）

```
color-blue-50:  #E3F2FD   # 浅色背景 (1.15:1)
color-blue-100: #BBDEFB   # 浅色强调 (1.44:1)
color-blue-200: #90CAF9   # 边框 (1.91:1)
color-blue-300: #64B5F6   # 辅助元素 (2.56:1)
color-blue-400: #42A5F5   # 次要按钮 (3.12:1 ⚠️)
color-blue-500: #2196F3   # 主品牌色 (3.94:1 ⚠️)
color-blue-600: #1E88E5   # ⚠️ 对比度仅 3.68:1，不适合文本
color-blue-700: #1976D2   # 推荐文本色（对比度 4.6:1 ✅ AA）
color-blue-800: #1565C0   # 深色 (6.03:1 ✅ AA)
color-blue-900: #0D47A1   # 极深色 (8.59:1 ✅ AAA)
```

**重要：** Blue-600 不符合 WCAG AA 标准，**文本应使用 Blue-700**。

#### 功能色（Functional Colors）

**成功色（Success / Green）**
```
color-green-50:  #E8F5E9   # 浅色背景 (1.13:1)
color-green-100: #C8E6C9   # 浅色强调 (1.38:1)
color-green-200: #A5D6A7   # 边框 (1.74:1)
color-green-300: #81C784   # 辅助元素 (2.22:1)
color-green-400: #66BB6A   # 次要按钮 (2.71:1 ⚠️)
color-green-500: #4CAF50   # 主成功色 (3.36:1 ⚠️)
color-green-600: #43A047   # ⚠️ 对比度仅 3.3:1，不适合文本
color-green-700: #388E3C   # 推荐文本色（对比度 5.44:1 ✅ AA）
color-green-800: #2E7D32   # 深色 (5.13:1 ✅ AA)
color-green-900: #1B5E20   # 极深色 (7.95:1 ✅ AAA)
```

**重要：** Green-600 不符合 WCAG AA 标准，**文本应使用 Green-700**。

**警告色（Warning / Amber）**
```
color-amber-50:  #FFF8E1   # 浅色背景 (1.06:1)
color-amber-100: #FFECB3   # 极浅背景 (1.15:1)
color-amber-200: #FFE082   # 边框 (1.29:1)
color-amber-300: #FFD54F   # 辅助元素 (1.48:1)
color-amber-400: #FFCA28   # 强调元素 (1.65:1)
color-amber-500: #FFC107   # 主警告色 (1.84:1 ❌)
color-amber-600: #FFB300   # 深色 (2.04:1 ❌)
color-amber-700: #FFA000   # 更深色 (2.28:1 ❌)
color-amber-800: #FF8F00   # 极深色 (2.56:1 ❌)
color-amber-900: #FF6F00   # 最深色 (2.79:1 ❌ 仍不达标)
```

**警告：** Amber 所有色阶都不符合 WCAG AA 标准！
**解决方案：** 使用反转配色 - `Grey-900` 文本 + `Amber-100` 背景 = 13.7:1 ✅ AAA

**错误色（Error / Red）**
```
color-red-50:  #FFEBEE   # 浅色背景 (1.11:1)
color-red-100: #FFCDD2   # 浅色强调 (1.31:1)
color-red-200: #EF9A9A   # 边框 (1.68:1)
color-red-300: #E57373   # 辅助元素 (2.19:1)
color-red-400: #EF5350   # 次要按钮 (2.84:1 ⚠️)
color-red-500: #F44336   # 主错误色 (3.53:1 ⚠️)
color-red-600: #E53935   # 深色 (4.03:1 ⚠️)
color-red-700: #D32F2F   # 推荐文本色（对比度 4.98:1 ✅ AA）
color-red-800: #C62828   # 极深色 (6.14:1 ✅ AA)
color-red-900: #B71C1C   # 最深色 (8.29:1 ✅ AAA)
```

**重要：** Red-600 不符合 WCAG AA 标准，**文本应使用 Red-700**。

**信息色（Info / Blue）**
> 与品牌色共用 Blue 色板，文本推荐使用 Blue-700。

### 1.2 语义色（Semantic Colors）

#### 文本色

```
color-text-primary:    {color-grey-900}    # 主要文本 #212121 (16.1:1 ✅ AAA)
color-text-secondary:  {color-grey-600}    # 次要文本 #757575 (4.68:1 ✅ AA)
color-text-tertiary:   {color-grey-500}    # 辅助文本 #9E9E9E (3.15:1 ⚠️)
color-text-disabled:   {color-grey-400}    # 禁用文本 #BDBDBD (2.26:1 ⚠️ 仅装饰)
color-text-inverse:    #FFFFFF             # 反色文本（深色背景上）
color-text-link:       {color-blue-700}    # 链接文本 #1976D2 (4.6:1 ✅ AA)
color-text-link-hover: {color-blue-800}    # 链接悬停 #1565C0 (6.03:1 ✅ AA)
color-text-error:      {color-red-700}     # 错误提示 #D32F2F (4.98:1 ✅ AA)
color-text-success:    {color-green-700}   # 成功提示 #388E3C (5.44:1 ✅ AA)
color-text-warning:    {color-grey-900}    # 警告文本 #212121 (16.1:1 ✅ AAA，深色方案)
```

**注意：** 警告文本使用 Grey-900，需搭配 Amber-100 背景。

#### 背景色

```
color-bg-primary:      #FFFFFF             # 主背景
color-bg-secondary:    {color-grey-50}     # 次级背景 #FAFAFA
color-bg-tertiary:     {color-grey-100}    # 三级背景 #F5F5F5
color-bg-overlay:      rgba(0, 0, 0, 0.5)  # 遮罩层
color-bg-disabled:     {color-grey-100}    # 禁用背景 #F5F5F5
color-bg-error:        {color-red-50}      # 错误背景 #FFEBEE
color-bg-success:      {color-green-50}    # 成功背景 #E8F5E9
color-bg-warning:      {color-amber-100}   # 警告背景 #FFECB3（浅色，搭配深色文本）
color-bg-info:         {color-blue-50}     # 信息背景 #E3F2FD
```

#### 边框色

```
color-border-primary:   {color-grey-300}   # 主边框 #E0E0E0
color-border-secondary: {color-grey-200}   # 次级边框 #EEEEEE
color-border-focus:     {color-blue-500}   # 焦点边框 #2196F3
color-border-error:     {color-red-500}    # 错误边框 #F44336
color-border-success:   {color-green-500}  # 成功边框 #4CAF50
color-border-warning:   {color-amber-500}  # 警告边框 #FFC107
```

#### 交互色

```
color-interactive-primary:          {color-blue-700}   # 主要交互 #1976D2 (4.6:1 ✅ AA)
color-interactive-primary-hover:    {color-blue-800}   # 悬停 #1565C0 (6.03:1 ✅ AA)
color-interactive-primary-active:   {color-blue-900}   # 按下 #0D47A1 (8.59:1 ✅ AAA)
color-interactive-primary-disabled: {color-grey-300}   # 禁用 #E0E0E0

color-interactive-secondary:        {color-grey-600}   # 次要交互 #757575
color-interactive-secondary-hover:  {color-grey-700}   # 悬停 #616161
color-interactive-secondary-active: {color-grey-800}   # 按下 #424242
```

---

## 2. Typography（字体）

> **完整文档：** [Typography 字体系统](./typography.md) - 包含字体族、字号、字重、行高的完整规范和使用示例

### 快速参考

**基础字号：** 14px × 1.25^n （B端最佳信息密度）

\`\`\`
font-size-xs:   12px   # 辅助信息、标签
font-size-sm:   14px   # B端基准（正文）
font-size-lg:   18px   # 小标题
font-size-xl:   22px   # 次级标题
font-size-2xl:  28px   # 主标题 (H3)
font-size-3xl:  34px   # 大标题 (H2)
font-size-4xl:  42px   # 特大标题 (H1)
\`\`\`

**详细内容请查看：** [typography.md](./typography.md)

---

## 3. Spacing（间距）

> **完整文档：** [Spacing 间距系统](./spacing.md) - 包含基础间距、语义化间距、负间距的完整规范

### 快速参考

**生成公式：** Spacing(n) = 4px × n

\`\`\`
spacing-2:    8px      # 小组件内边距
spacing-3:    12px     # 按钮内边距
spacing-4:    16px     # 卡片内边距（常用，基准）
spacing-6:    24px     # 大组件内边距
spacing-8:    32px     # 区块间距
spacing-12:   48px     # 大区块间距
spacing-16:   64px     # 页面模块间距
\`\`\`

**详细内容请查看：** [spacing.md](./spacing.md)

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

## 10. Grid（栅格系统）

> **完整文档：** [Grid 栅格系统](./grid.md) - 包含 12 列栅格、响应式间隙、容器宽度的完整规范

### 快速参考

**栅格配置：**
```
grid-columns:     12      # 标准 12 列系统
grid-gutter-md:   16px    # 栅格间隙（基准）
grid-container-xl: 1280px  # 容器最大宽度
```

**响应式栅格：**
- 移动端（xs/sm）：4 列，8-12px 间隙
- 平板（md）：8 列，16px 间隙
- 桌面（lg+）：12 列，24px 间隙

**详细内容请查看：** [grid.md](./grid.md)

---

## 11. Container Queries（容器查询）

> **完整文档：** [Container Queries 容器查询](./container-queries.md) - 现代组件级响应式方案

### 快速参考

**容器断点：**
```
container-sm:    320px     # 小容器
container-md:    480px     # 中等容器
container-lg:    640px     # 大容器
container-xl:    800px     # 超大容器
```

**基础用法：**
```css
.container {
  container-type: inline-size;
}

@container (min-width: 480px) {
  .card { /* 响应式样式 */ }
}
```

**详细内容请查看：** [container-queries.md](./container-queries.md)

---

## 12. Motion（动效）

> **完整文档：** [Motion 动效系统](./motion.md) - 包含动画时长、缓动函数、语义化过渡的完整规范

### 快速参考

**动画时长：**
\`\`\`
duration-fast:     100ms     # 快速（状态切换）
duration-base:     200ms     # 基础（按钮悬停，推荐）
duration-slow:     300ms     # 慢速（抽屉展开）
duration-slower:   500ms     # 更慢（页面转场）
\`\`\`

**缓动函数（Material Design）：**
\`\`\`
ease-out:         cubic-bezier(0, 0, 0.2, 1)         # 元素进入（推荐）
ease-in:          cubic-bezier(0.4, 0, 1, 1)         # 元素离开
ease-in-out:      cubic-bezier(0.4, 0, 0.2, 1)       # 位置变化
\`\`\`

**详细内容请查看：** [motion.md](./motion.md)

---

## 13. Opacity（透明度）

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
   - 颜色：选择 "color-text-primary" 而非 #171717
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
  /* Color - Material Design */
  --color-text-primary: #212121;      /* Grey-900, 16.1:1 AAA */
  --color-bg-primary: #FFFFFF;
  --color-interactive-primary: #1976D2;  /* Blue-700, 4.6:1 AA */

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
      primary: '#212121',    // Grey-900, Material Design
      secondary: '#757575',  // Grey-600
    },
    interactive: {
      primary: '#1976D2',       // Blue-700, 4.6:1 AA
      primaryHover: '#1565C0',  // Blue-800, 6.03:1 AA
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
        // Material Design 基础色板
        grey: {  // Material Design 使用 "grey" 不是 "gray"
          50: '#FAFAFA',
          100: '#F5F5F5',
          200: '#EEEEEE',
          300: '#E0E0E0',
          400: '#BDBDBD',
          500: '#9E9E9E',
          600: '#757575',
          700: '#616161',
          800: '#424242',
          900: '#212121',
        },
        blue: {
          50: '#E3F2FD',
          100: '#BBDEFB',
          200: '#90CAF9',
          300: '#64B5F6',
          400: '#42A5F5',
          500: '#2196F3',
          600: '#1E88E5',
          700: '#1976D2',  // 推荐用于文本
          800: '#1565C0',
          900: '#0D47A1',
        },
        green: {
          700: '#388E3C',  // 推荐用于成功文本
          // ... 其他色阶
        },
        red: {
          700: '#D32F2F',  // 推荐用于错误文本
          // ... 其他色阶
        },
        amber: {
          100: '#FFECB3',  // 警告背景
          500: '#FFC107',  // 警告边框
          900: '#FF6F00',  // 警告图标
        },
        // 语义色
        'text-primary': '#212121',        // Grey-900
        'interactive-primary': '#1976D2', // Blue-700
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

使用工具验证所有颜色组合（基于 Material Design）：

```
✅ 必须符合 WCAG AA 级：
  - color-text-primary (#212121) on #FFFFFF   → 16.1:1 (AAA ✅)
  - color-text-secondary (#757575) on #FFFFFF → 4.68:1 (AA ✅)
  - color-text-link (#1976D2) on #FFFFFF      → 4.6:1 (AA ✅)
  - color-text-error (#D32F2F) on #FFFFFF     → 4.98:1 (AA ✅)
  - color-text-success (#388E3C) on #FFFFFF   → 5.44:1 (AA ✅)

⚠️ 需要特殊处理：
  - color-text-tertiary (#9E9E9E) on #FFFFFF  → 3.15:1 (⚠️ 仅辅助)
  - color-text-disabled (#BDBDBD) on #FFFFFF  → 2.26:1 (⚠️ 仅装饰)
  - color-text-warning (#212121) on #FFECB3   → 13.7:1 (AAA ✅ 反转方案)
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
/* 浅色模式（默认） - Material Design */
:root {
  --color-text-primary: #212121;     /* Grey-900 */
  --color-text-secondary: #757575;   /* Grey-600 */
  --color-bg-primary: #FFFFFF;
  --color-bg-secondary: #FAFAFA;     /* Grey-50 */
  --color-border-primary: #E0E0E0;   /* Grey-300 */
}

/* 暗色模式 */
[data-theme="dark"] {
  --color-text-primary: #FAFAFA;     /* Grey-50 */
  --color-text-secondary: #E0E0E0;   /* Grey-300 */
  --color-bg-primary: #212121;       /* Grey-900 */
  --color-bg-secondary: #424242;     /* Grey-800 */
  --color-border-primary: #616161;   /* Grey-700 */
}
```

**关键原则：**
- 暗色模式下仍需保证对比度 ≥ 4.5:1
- 反转亮度，但保持饱和度一致
- 功能色（成功/警告/错误）保持语义不变
- 避免使用纯黑 (#000000)，使用 Grey-900 (#212121)

**完整内容请查看：** [暗色模式文档](./dark-mode.md)

---

## JSON 格式示例

**用于工具导入/导出（Design Tokens Format Module 标准）**

```json
{
  "color": {
    "grey": {
      "900": {
        "value": "#212121",
        "type": "color",
        "description": "Material Design Grey-900，用于主文本"
      }
    },
    "text": {
      "primary": {
        "value": "{color.grey.900}",
        "type": "color",
        "description": "主要文本颜色，对比度 16.1:1 (AAA)"
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
