# 语义化色彩系统 - 完整规划

> 基于 12 色完整色板的系统化语义色 Token 体系

---

## 设计原则

### 1. 三层架构

```
Primitive Tokens (基础色板)
    ↓ 引用
Semantic Tokens (语义化 Token)  ← 本文档
    ↓ 引用
Component Tokens (组件 Token)
```

### 2. 命名规范

```
{category}-{element}-{variant}-{state}

示例:
- text-primary           # 主要文本
- bg-input-hover         # 输入框悬停背景
- border-error-focus     # 错误边框聚焦态
- interactive-primary-disabled  # 主交互元素禁用态
```

### 3. 暗色模式策略

- 所有 Token 必须定义浅色/暗色两种模式
- 暗色模式对比度降低至 60-80%，避免视觉疲劳
- 功能色（成功/警告/错误）在暗色模式下保持识别度

---

## 完整分类体系

### 📊 总览统计

| 分类 | Token 数量 | 状态 | 文档 |
|------|-----------|------|------|
| **1. 文本色** | 20 | ✅ 已完成 | [text-colors.md](./text-colors.md) |
| **2. 背景色** | 30 | ✅ 已完成 | [background-colors.md](./background-colors.md) |
| **3. 边框色** | 15 | ✅ 已完成 | [border-colors.md](./border-colors.md) |
| **4. 交互色** | 20 | ✅ 已完成 | [interactive-colors.md](./interactive-colors.md) |
| **5. 功能色** | 20 | ✅ 已完成 | [functional-colors.md](./functional-colors.md) |
| **6. 装饰色** | 15 | 🚧 待补充 | [decorative-colors.md](./decorative-colors.md) |
| **7. 组件色** | 50+ | 🚧 待补充 | [component-colors.md](./component-colors.md) |
| **合计** | **170+** | - | - |

---

## 1️⃣ 文本色（Text Colors）

**目的：** 用于所有文字内容的颜色定义

### Token 清单（20 个）

#### 基础文本（6 个）
- `text-primary` - 主要文本（#171717 / #FAFAFA）
- `text-secondary` - 次要文本（#525252 / #D4D4D4）
- `text-tertiary` - 三级文本（#737373 / #A3A3A3）
- `text-quaternary` - 四级文本（#A3A3A3 / #737373）
- `text-inverse` - 反色文本（#FFFFFF / #171717）
- `text-placeholder` - 占位符文本（#A3A3A3 / #737373）

#### 链接文本（4 个）
- `text-link` - 默认链接
- `text-link-hover` - 悬停链接
- `text-link-visited` - 已访问链接
- `text-link-active` - 激活链接

#### 功能反馈文本（4 个）
- `text-success` - 成功文本
- `text-warning` - 警告文本
- `text-error` - 错误文本
- `text-info` - 信息文本

#### 品牌/强调文本（3 个）
- `text-brand` - 品牌文本
- `text-emphasis` - 强调文本
- `text-highlight` - 高亮文本

#### 代码文本（5 个）
- `text-code` - 行内代码
- `text-code-keyword` - 代码关键字
- `text-code-string` - 代码字符串
- `text-code-comment` - 代码注释
- `text-code-number` - 代码数字

**详见：** [text-colors.md](./text-colors.md)

---

## 2️⃣ 背景色（Background Colors）

**目的：** 用于页面、卡片、容器等背景

### Token 清单（30 个）

#### 页面背景（3 个）
- `bg-page` - 页面主背景
- `bg-page-secondary` - 页面次要背景
- `bg-canvas` - 画布背景

#### 容器背景（8 个）
- `bg-primary` - 主要背景
- `bg-secondary` - 次要背景
- `bg-tertiary` - 三级背景
- `bg-inverse` - 反色背景
- `bg-card` - 卡片背景
- `bg-card-hover` - 卡片悬停
- `bg-popover` - 弹出层背景
- `bg-modal` - 模态框背景

#### 表单背景（5 个）
- `bg-input` - 输入框背景
- `bg-input-hover` - 输入框悬停
- `bg-input-disabled` - 输入框禁用
- `bg-input-readonly` - 输入框只读
- `bg-input-focus` - 输入框聚焦

#### 功能背景（8 个）
- `bg-success` / `bg-success-subtle` - 成功背景
- `bg-warning` / `bg-warning-subtle` - 警告背景
- `bg-error` / `bg-error-subtle` - 错误背景
- `bg-info` / `bg-info-subtle` - 信息背景

#### 特殊背景（6 个）
- `bg-overlay` - 遮罩层
- `bg-skeleton` - 骨架屏
- `bg-table-header` - 表头背景
- `bg-table-row-hover` - 表格行悬停
- `bg-table-row-selected` - 表格行选中
- `bg-code-block` - 代码块背景

**详见：** [background-colors.md](./background-colors.md)

---

## 3️⃣ 边框色（Border Colors）

**目的：** 用于分割线、边框、描边

### Token 清单（15 个）

#### 基础边框（5 个）
- `border-primary` - 主要边框
- `border-secondary` - 次要边框
- `border-tertiary` - 三级边框
- `border-inverse` - 反色边框
- `border-transparent` - 透明边框

#### 交互边框（3 个）
- `border-hover` - 悬停边框
- `border-focus` - 聚焦边框
- `border-active` - 激活边框

#### 功能边框（4 个）
- `border-success` - 成功边框
- `border-warning` - 警告边框
- `border-error` - 错误边框
- `border-info` - 信息边框

#### 分割线（3 个）
- `divider-primary` - 主要分割线
- `divider-secondary` - 次要分割线
- `divider-inverse` - 反色分割线

**详见：** [border-colors.md](./border-colors.md)

---

## 4️⃣ 交互色（Interactive Colors）

**目的：** 用于按钮、链接、图标等交互元素

### Token 清单（20 个）

#### 主交互色（4 个）
- `interactive-primary` - 主交互元素（默认）
- `interactive-primary-hover` - 悬停态
- `interactive-primary-active` - 激活态
- `interactive-primary-disabled` - 禁用态

#### 次交互色（4 个）
- `interactive-secondary` - 次要交互元素
- `interactive-secondary-hover`
- `interactive-secondary-active`
- `interactive-secondary-disabled`

#### 危险交互色（4 个）
- `interactive-danger` - 危险操作
- `interactive-danger-hover`
- `interactive-danger-active`
- `interactive-danger-disabled`

#### 幽灵/文本交互色（4 个）
- `interactive-ghost` - 幽灵按钮
- `interactive-ghost-hover`
- `interactive-text` - 文本按钮
- `interactive-text-hover`

#### 图标交互色（4 个）
- `interactive-icon` - 图标默认
- `interactive-icon-hover`
- `interactive-icon-active`
- `interactive-icon-disabled`

**详见：** [interactive-colors.md](./interactive-colors.md)

---

## 5️⃣ 功能色（Functional Colors）

**目的：** 用于成功、警告、错误、信息等功能反馈

### Token 清单（20 个）

每个功能类型 5 个 Token × 4 类 = 20 个

#### 成功色系（5 个）
- `functional-success-text` - 成功文本
- `functional-success-bg` - 成功背景
- `functional-success-bg-subtle` - 极淡成功背景
- `functional-success-border` - 成功边框
- `functional-success-icon` - 成功图标

#### 警告色系（5 个）
- `functional-warning-text`
- `functional-warning-bg`
- `functional-warning-bg-subtle`
- `functional-warning-border`
- `functional-warning-icon`

#### 错误色系（5 个）
- `functional-error-text`
- `functional-error-bg`
- `functional-error-bg-subtle`
- `functional-error-border`
- `functional-error-icon`

#### 信息色系（5 个）
- `functional-info-text`
- `functional-info-bg`
- `functional-info-bg-subtle`
- `functional-info-border`
- `functional-info-icon`

**详见：** [functional-colors.md](./functional-colors.md)

---

## 6️⃣ 装饰色（Decorative Colors）

**目的：** 用于阴影、渐变、骨架屏等视觉装饰

### Token 清单（15 个）

#### 阴影色（6 个）
- `shadow-sm` - 小阴影（rgba(0,0,0,0.05)）
- `shadow-base` - 基础阴影（rgba(0,0,0,0.1)）
- `shadow-md` - 中等阴影（rgba(0,0,0,0.15)）
- `shadow-lg` - 大阴影（rgba(0,0,0,0.2)）
- `shadow-xl` - 超大阴影（rgba(0,0,0,0.25)）
- `shadow-inner` - 内阴影（rgba(0,0,0,0.06)）

#### 渐变色（4 个）
- `gradient-primary` - 主渐变（Blue-500 → Blue-600）
- `gradient-secondary` - 次渐变（Gray-100 → Gray-200）
- `gradient-shimmer` - 骨架屏闪光渐变
- `gradient-glass` - 玻璃态渐变（带透明度）

#### 特殊装饰（5 个）
- `skeleton-base` - 骨架屏基础色
- `skeleton-highlight` - 骨架屏高光色
- `watermark` - 水印颜色（极低透明度）
- `focus-ring` - 聚焦环颜色
- `selection-bg` - 文本选中背景

**详见：** [decorative-colors.md](./decorative-colors.md) 🚧

---

## 7️⃣ 组件色（Component Colors）

**目的：** 为特定组件提供专用色彩 Token

### Token 分类

#### 按钮组件（8 个）
- `button-primary-bg` / `button-primary-text`
- `button-secondary-bg` / `button-secondary-text`
- `button-danger-bg` / `button-danger-text`
- `button-ghost-border` / `button-ghost-text`

#### 表单组件（10 个）
- `input-bg` / `input-border` / `input-text` / `input-placeholder`
- `checkbox-bg` / `checkbox-border` / `checkbox-checked`
- `radio-bg` / `radio-border` / `radio-checked`

#### 导航组件（8 个）
- `nav-bg` / `nav-item-default` / `nav-item-hover` / `nav-item-active`
- `breadcrumb-separator` / `breadcrumb-link`
- `tab-default` / `tab-active`

#### 反馈组件（12 个）
- `toast-success-bg` / `toast-success-border` / `toast-success-icon`
- `toast-error-bg` / `toast-error-border` / `toast-error-icon`
- `tooltip-bg` / `tooltip-text`
- `badge-bg` / `badge-text`
- `tag-bg` / `tag-text`

#### 数据展示组件（12 个）
- `table-header-bg` / `table-header-text` / `table-border`
- `table-row-hover` / `table-row-selected`
- `progress-bg` / `progress-fill`
- `chart-grid` / `chart-axis`
- `avatar-bg` / `avatar-text`
- `skeleton-shimmer`

**详见：** [component-colors.md](./component-colors.md) 🚧

---

## 使用指南

### 1. 选择合适的 Token 层级

```tsx
// ❌ 不好：直接使用基础色板
<div style={{ color: '#0770FA' }}>文本</div>

// ✅ 好：使用语义化 Token
<div style={{ color: 'var(--text-link)' }}>文本</div>

// ✅ 更好：使用组件 Token（如果有）
<Link style={{ color: 'var(--nav-item-active)' }}>链接</Link>
```

### 2. 暗色模式自动切换

```css
:root {
  --text-primary: #171717;
}

[data-theme="dark"] {
  --text-primary: #FAFAFA;
}
```

组件中无需手动判断，直接使用 Token 即可自动适配。

### 3. 功能色优先级

```
1. 使用功能色（functional-*）
   ↓ 如果功能色不合适
2. 使用交互色（interactive-*）
   ↓ 如果交互色不合适
3. 使用基础色（text-*, bg-*, border-*）
   ↓ 如果都不合适
4. 创建新的语义 Token（提 PR）
```

### 4. 对比度要求

- **常规文本**：≥ 4.5:1（WCAG AA）
- **大号文本**：≥ 3:1（WCAG AA）
- **UI 组件**：≥ 3:1（WCAG AA）
- **装饰元素**：无强制要求

---

## Token 导出格式

所有语义色 Token 支持以下格式导出：

### 1. CSS Variables

```css
:root {
  --text-primary: #171717;
  --bg-page: #FFFFFF;
  --border-primary: #E5E5E5;
}
```

### 2. Design Tokens Format (JSON)

```json
{
  "color": {
    "text": {
      "primary": {
        "value": "#171717",
        "type": "color",
        "$extensions": {
          "mode": { "dark": "#FAFAFA" }
        }
      }
    }
  }
}
```

### 3. Tailwind Config

```js
module.exports = {
  theme: {
    extend: {
      colors: {
        'text-primary': 'var(--text-primary)',
        'bg-page': 'var(--bg-page)',
      }
    }
  }
}
```

### 4. TypeScript Types

```typescript
export type SemanticColor =
  | 'text-primary'
  | 'text-secondary'
  | 'bg-page'
  | 'border-primary'
  // ...
```

---

## 下一步

### 待补充文档

- [ ] [decorative-colors.md](./decorative-colors.md) - 装饰色 Token
- [ ] [component-colors.md](./component-colors.md) - 组件色 Token
- [ ] 完整 CSS Variables 导出
- [ ] Design Tokens Format JSON 导出
- [ ] Tailwind CSS 完整配置

### 持续优化

- [ ] 补充更多组件色 Token
- [ ] 添加数据可视化专用色
- [ ] 优化暗色模式对比度
- [ ] 添加高对比度模式支持

---

**文档版本：** v2.0
**最后更新：** 2025-11-16
**负责人：** Design System Team
