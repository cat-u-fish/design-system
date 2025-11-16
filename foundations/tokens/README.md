# Design Token 规范

## 什么是 Design Token

Design Token 是设计系统中的**最小设计决策单元**，用一致的命名来存储视觉设计属性（如颜色、字体、间距等）。它是设计师和开发者之间的"共同语言"。

### 优势

- **一致性**：确保所有产品使用相同的设计语言
- **可维护性**：修改一处，全局生效
- **协作效率**：设计师和开发使用相同的命名体系
- **主题化**：轻松支持暗色模式、品牌定制等

---

## Token 分类体系

### 1. 原始 Token（Primitive Tokens）
最基础的值，通常按类别和数值组织
```
color-blue-500: #3B82F6
spacing-4: 16px
```

### 2. 语义 Token（Semantic Tokens）
赋予原始 Token 含义和用途
```
color-primary: {color-blue-500}
spacing-card-padding: {spacing-4}
```

### 3. 组件 Token（Component Tokens）
特定组件专用的 Token
```
button-primary-bg: {color-primary}
button-padding-x: {spacing-4}
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
```

### 命名原则
- 使用小写字母
- 单词间用 `-` 连接
- 从通用到具体（从左到右）
- 避免缩写（除非是行业通用术语）

---

## Token 详细规范

## 1. Color（颜色）

### 1.1 基础色板（Primitive Colors）

#### 中性色（Neutral/Gray）
```
color-gray-50:  #F9FAFB
color-gray-100: #F3F4F6
color-gray-200: #E5E7EB
color-gray-300: #D1D5DB
color-gray-400: #9CA3AF
color-gray-500: #6B7280
color-gray-600: #4B5563
color-gray-700: #374151
color-gray-800: #1F2937
color-gray-900: #111827
color-gray-950: #030712
```

#### 品牌色（Brand）
```
color-blue-50:  #EFF6FF
color-blue-100: #DBEAFE
color-blue-200: #BFDBFE
color-blue-300: #93C5FD
color-blue-400: #60A5FA
color-blue-500: #3B82F6  # 主品牌色
color-blue-600: #2563EB
color-blue-700: #1D4ED8
color-blue-800: #1E40AF
color-blue-900: #1E3A8A
color-blue-950: #172554
```

#### 功能色（Functional）

**成功色（Success/Green）**
```
color-green-50:  #F0FDF4
color-green-100: #DCFCE7
color-green-500: #22C55E  # 主成功色
color-green-600: #16A34A
color-green-700: #15803D
```

**警告色（Warning/Yellow）**
```
color-yellow-50:  #FEFCE8
color-yellow-100: #FEF9C3
color-yellow-500: #EAB308  # 主警告色
color-yellow-600: #CA8A04
color-yellow-700: #A16207
```

**错误色（Error/Red）**
```
color-red-50:  #FEF2F2
color-red-100: #FEE2E2
color-red-500: #EF4444  # 主错误色
color-red-600: #DC2626
color-red-700: #B91C1C
```

**信息色（Info/Cyan）**
```
color-cyan-50:  #ECFEFF
color-cyan-100: #CFFAFE
color-cyan-500: #06B6D4  # 主信息色
color-cyan-600: #0891B2
color-cyan-700: #0E7490
```

### 1.2 语义色（Semantic Colors）

#### 文本色
```
color-text-primary:   {color-gray-900}     # 主要文本
color-text-secondary: {color-gray-600}     # 次要文本
color-text-tertiary:  {color-gray-500}     # 辅助文本
color-text-disabled:  {color-gray-400}     # 禁用文本
color-text-inverse:   #FFFFFF              # 反色文本（深色背景上）
color-text-link:      {color-blue-600}     # 链接文本
color-text-error:     {color-red-600}      # 错误提示文本
color-text-success:   {color-green-600}    # 成功提示文本
color-text-warning:   {color-yellow-700}   # 警告提示文本
```

#### 背景色
```
color-bg-primary:     #FFFFFF              # 主背景
color-bg-secondary:   {color-gray-50}      # 次级背景
color-bg-tertiary:    {color-gray-100}     # 三级背景
color-bg-overlay:     rgba(0, 0, 0, 0.5)   # 遮罩层
color-bg-disabled:    {color-gray-100}     # 禁用背景
```

#### 边框色
```
color-border-primary:   {color-gray-300}   # 主边框
color-border-secondary: {color-gray-200}   # 次级边框
color-border-focus:     {color-blue-500}   # 焦点边框
color-border-error:     {color-red-500}    # 错误边框
```

#### 交互色
```
color-interactive-primary:        {color-blue-600}     # 主要交互元素
color-interactive-primary-hover:  {color-blue-700}     # 悬停
color-interactive-primary-active: {color-blue-800}     # 按下
color-interactive-secondary:      {color-gray-600}     # 次要交互元素
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
```
font-size-xs:   12px  # 0.75rem
font-size-sm:   14px  # 0.875rem
font-size-base: 16px  # 1rem      # 基准字号
font-size-lg:   18px  # 1.125rem
font-size-xl:   20px  # 1.25rem
font-size-2xl:  24px  # 1.5rem
font-size-3xl:  30px  # 1.875rem
font-size-4xl:  36px  # 2.25rem
font-size-5xl:  48px  # 3rem
font-size-6xl:  60px  # 3.75rem
```

### 2.3 字重（Font Weight）
```
font-weight-thin:       100
font-weight-extralight: 200
font-weight-light:      300
font-weight-normal:     400  # 正文默认
font-weight-medium:     500
font-weight-semibold:   600  # 小标题默认
font-weight-bold:       700  # 大标题默认
font-weight-extrabold:  800
font-weight-black:      900
```

### 2.4 行高（Line Height）
```
line-height-none:   1      # 100%
line-height-tight:  1.25   # 125%
line-height-snug:   1.375  # 137.5%
line-height-normal: 1.5    # 150%   # 正文默认
line-height-relaxed: 1.625 # 162.5%
line-height-loose:  2      # 200%
```

### 2.5 字间距（Letter Spacing）
```
letter-spacing-tighter: -0.05em
letter-spacing-tight:   -0.025em
letter-spacing-normal:  0
letter-spacing-wide:    0.025em
letter-spacing-wider:   0.05em
letter-spacing-widest:  0.1em
```

### 2.6 语义化字体（Semantic Typography）
```
# 标题
font-heading-1: {font-size-5xl} / {line-height-tight} {font-weight-bold} {font-family-sans}
font-heading-2: {font-size-4xl} / {line-height-tight} {font-weight-bold} {font-family-sans}
font-heading-3: {font-size-3xl} / {line-height-snug} {font-weight-semibold} {font-family-sans}
font-heading-4: {font-size-2xl} / {line-height-snug} {font-weight-semibold} {font-family-sans}
font-heading-5: {font-size-xl} / {line-height-normal} {font-weight-semibold} {font-family-sans}
font-heading-6: {font-size-lg} / {line-height-normal} {font-weight-semibold} {font-family-sans}

# 正文
font-body-large:  {font-size-lg} / {line-height-relaxed} {font-weight-normal} {font-family-sans}
font-body-base:   {font-size-base} / {line-height-normal} {font-weight-normal} {font-family-sans}
font-body-small:  {font-size-sm} / {line-height-normal} {font-weight-normal} {font-family-sans}

# 辅助文本
font-caption:     {font-size-xs} / {line-height-normal} {font-weight-normal} {font-family-sans}
font-overline:    {font-size-xs} / {line-height-normal} {font-weight-semibold} {font-family-sans}

# 代码
font-code:        {font-size-sm} / {line-height-normal} {font-weight-normal} {font-family-mono}
```

---

## 3. Spacing（间距）

### 3.1 基础间距（Primitive Spacing）
基于 4px 基准单位
```
spacing-0:   0px
spacing-0.5: 2px
spacing-1:   4px    # 基准单位
spacing-1.5: 6px
spacing-2:   8px
spacing-2.5: 10px
spacing-3:   12px
spacing-4:   16px
spacing-5:   20px
spacing-6:   24px
spacing-7:   28px
spacing-8:   32px
spacing-9:   36px
spacing-10:  40px
spacing-11:  44px
spacing-12:  48px
spacing-14:  56px
spacing-16:  64px
spacing-20:  80px
spacing-24:  96px
spacing-32:  128px
spacing-40:  160px
spacing-48:  192px
spacing-64:  256px
```

### 3.2 语义化间距（Semantic Spacing）
```
# 组件内边距
spacing-padding-xs:     {spacing-2}   # 8px
spacing-padding-sm:     {spacing-3}   # 12px
spacing-padding-md:     {spacing-4}   # 16px
spacing-padding-lg:     {spacing-6}   # 24px
spacing-padding-xl:     {spacing-8}   # 32px

# 组件外边距
spacing-margin-xs:      {spacing-2}   # 8px
spacing-margin-sm:      {spacing-4}   # 16px
spacing-margin-md:      {spacing-6}   # 24px
spacing-margin-lg:      {spacing-8}   # 32px
spacing-margin-xl:      {spacing-12}  # 48px

# 页面布局间距
spacing-section:        {spacing-16}  # 64px   # 区块间距
spacing-container:      {spacing-6}   # 24px   # 容器内边距
spacing-gutter:         {spacing-4}   # 16px   # 栅格间隙
```

---

## 4. Sizing（尺寸）

### 4.1 基础尺寸（Primitive Sizing）
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
size-icon-xs:   16px
size-icon-sm:   20px
size-icon-md:   24px
size-icon-lg:   32px
size-icon-xl:   40px
```

### 4.3 组件高度
```
size-height-input:      40px   # 输入框默认高度
size-height-button-sm:  32px
size-height-button-md:  40px
size-height-button-lg:  48px
size-height-header:     64px   # 顶部导航栏高度
```

### 4.4 容器宽度
```
size-container-sm:  640px
size-container-md:  768px
size-container-lg:  1024px
size-container-xl:  1280px
size-container-2xl: 1536px
```

---

## 5. Border Radius（圆角）

```
radius-none:   0px
radius-sm:     2px     # 小圆角（标签、徽章）
radius-base:   4px     # 基础圆角（按钮、输入框）
radius-md:     6px     # 中等圆角（卡片）
radius-lg:     8px     # 大圆角（对话框）
radius-xl:     12px    # 超大圆角（面板）
radius-2xl:    16px    # 特大圆角
radius-3xl:    24px    # 巨大圆角
radius-full:   9999px  # 圆形（头像、徽章点）
```

---

## 6. Shadow（阴影）

### 6.1 基础阴影
```
shadow-none: none

shadow-xs:
  0 1px 2px 0 rgba(0, 0, 0, 0.05)

shadow-sm:
  0 1px 3px 0 rgba(0, 0, 0, 0.1),
  0 1px 2px -1px rgba(0, 0, 0, 0.1)

shadow-base:
  0 4px 6px -1px rgba(0, 0, 0, 0.1),
  0 2px 4px -2px rgba(0, 0, 0, 0.1)

shadow-md:
  0 10px 15px -3px rgba(0, 0, 0, 0.1),
  0 4px 6px -4px rgba(0, 0, 0, 0.1)

shadow-lg:
  0 20px 25px -5px rgba(0, 0, 0, 0.1),
  0 8px 10px -6px rgba(0, 0, 0, 0.1)

shadow-xl:
  0 25px 50px -12px rgba(0, 0, 0, 0.25)

shadow-2xl:
  0 50px 100px -20px rgba(0, 0, 0, 0.25)
```

### 6.2 内阴影
```
shadow-inner:
  inset 0 2px 4px 0 rgba(0, 0, 0, 0.05)
```

### 6.3 语义化阴影
```
shadow-card:     {shadow-sm}     # 卡片
shadow-dropdown: {shadow-md}     # 下拉菜单
shadow-modal:    {shadow-xl}     # 弹窗
shadow-focus:    0 0 0 3px rgba(59, 130, 246, 0.3)  # 焦点环
```

---

## 7. Border（边框）

### 7.1 边框宽度
```
border-width-0:    0px
border-width-1:    1px   # 默认边框
border-width-2:    2px
border-width-4:    4px
border-width-8:    8px
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

```
z-index-dropdown:   1000   # 下拉菜单
z-index-sticky:     1020   # 吸顶元素
z-index-fixed:      1030   # 固定定位元素
z-index-backdrop:   1040   # 遮罩层
z-index-modal:      1050   # 弹窗
z-index-popover:    1060   # 气泡提示
z-index-tooltip:    1070   # 工具提示
z-index-notification: 1080 # 通知消息
z-index-toast:      1090   # Toast 提示
```

---

## 9. Breakpoints（响应式断点）

```
breakpoint-xs:   0px      # 手机竖屏
breakpoint-sm:   640px    # 手机横屏 / 小平板
breakpoint-md:   768px    # 平板
breakpoint-lg:   1024px   # 小屏笔记本
breakpoint-xl:   1280px   # 桌面显示器
breakpoint-2xl:  1536px   # 大屏显示器
```

---

## 10. Motion（动效）

### 10.1 动画时长（Duration）
```
duration-instant:  0ms      # 无动画
duration-fast:     100ms    # 快速（状态切换）
duration-base:     200ms    # 基础（按钮悬停）
duration-slow:     300ms    # 慢速（抽屉展开）
duration-slower:   500ms    # 更慢（页面转场）
```

### 10.2 缓动函数（Easing）
```
ease-linear:      cubic-bezier(0, 0, 1, 1)
ease-in:          cubic-bezier(0.4, 0, 1, 1)        # 加速
ease-out:         cubic-bezier(0, 0, 0.2, 1)        # 减速
ease-in-out:      cubic-bezier(0.4, 0, 0.2, 1)      # 先加速后减速
ease-bounce:      cubic-bezier(0.68, -0.55, 0.265, 1.55)  # 弹性
```

### 10.3 语义化动效
```
transition-base:  all {duration-base} {ease-out}
transition-fade:  opacity {duration-base} {ease-in-out}
transition-slide: transform {duration-base} {ease-out}
```

---

## 11. Opacity（透明度）

```
opacity-0:        0      # 完全透明
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
opacity-100:      1      # 完全不透明
```

### 语义化透明度
```
opacity-disabled:   {opacity-50}   # 禁用状态
opacity-hover:      {opacity-80}   # 悬停遮罩
opacity-backdrop:   {opacity-50}   # 背景遮罩
```

---

## 如何使用

### 设计师使用方式

#### 在 Figma 中
1. 安装 [Tokens Studio](https://www.figma.com/community/plugin/843461159747178978) 插件
2. 导入 Token JSON 文件
3. 应用 Token 到设计元素：
   - 颜色：使用 `color-text-primary` 而非直接选色
   - 间距：使用 `spacing-4` 而非手动输入 16px
   - 字体：使用 `font-body-base` 而非单独设置

#### 命名图层
```
✅ 使用 Token 名称
Button/Primary/Default → 背景色用 color-interactive-primary

❌ 避免硬编码
Button → 背景色用 #3B82F6
```

### 开发者使用方式

#### CSS Variables
```css
:root {
  /* Color */
  --color-text-primary: #111827;
  --color-bg-primary: #FFFFFF;

  /* Spacing */
  --spacing-4: 16px;

  /* Typography */
  --font-size-base: 16px;
  --line-height-normal: 1.5;
}

.button {
  background-color: var(--color-interactive-primary);
  padding: var(--spacing-3) var(--spacing-6);
  font-size: var(--font-size-base);
  border-radius: var(--radius-base);
}
```

#### JavaScript/TypeScript
```typescript
// tokens.ts
export const tokens = {
  color: {
    text: {
      primary: '#111827',
      secondary: '#6B7280',
    },
  },
  spacing: {
    4: '16px',
    6: '24px',
  },
} as const;

// 使用
import { tokens } from './tokens';

const Button = styled.button`
  background: ${tokens.color.interactive.primary};
  padding: ${tokens.spacing[3]} ${tokens.spacing[6]};
`;
```

#### Tailwind CSS 配置
```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        'text-primary': '#111827',
        'bg-primary': '#FFFFFF',
      },
      spacing: {
        '4': '16px',
        '6': '24px',
      },
    },
  },
};
```

---

## 暗色模式支持

### Token 覆盖
```css
:root {
  --color-text-primary: #111827;
  --color-bg-primary: #FFFFFF;
}

[data-theme="dark"] {
  --color-text-primary: #F9FAFB;
  --color-bg-primary: #111827;
}
```

### 暗色模式 Token（扩展）
```
# 浅色模式（默认）
color-text-primary: {color-gray-900}
color-bg-primary:   #FFFFFF

# 暗色模式
color-text-primary: {color-gray-100}  # 在暗色主题下覆盖
color-bg-primary:   {color-gray-900}  # 在暗色主题下覆盖
```

---

## 文件格式示例

### JSON 格式（用于工具导入/导出）
```json
{
  "color": {
    "gray": {
      "500": {
        "value": "#6B7280",
        "type": "color"
      }
    },
    "text": {
      "primary": {
        "value": "{color.gray.900}",
        "type": "color",
        "description": "主要文本颜色"
      }
    }
  },
  "spacing": {
    "4": {
      "value": "16px",
      "type": "dimension"
    }
  }
}
```

---

## 下一步

- [ ] 补充更多色彩方案（如紫色、橙色系）
- [ ] 定义暗色模式完整 Token 映射
- [ ] 建立 Token 输出工具链（自动生成 CSS/SCSS/JSON）
- [ ] 完善可访问性相关 Token（对比度验证）

---

## 参考资源

- [Material Design Color System](https://material.io/design/color)
- [Tailwind CSS Default Theme](https://tailwindcss.com/docs/theme)
- [Ant Design Design Values](https://ant.design/docs/spec/values)
- [Design Tokens Format Module](https://tr.designtokens.org/format/)
