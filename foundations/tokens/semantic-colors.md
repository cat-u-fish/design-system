# 语义化色彩系统 - 总览

> 将原始色板转化为具有明确语义的 Token 系统，覆盖设计系统中所有色彩使用场景。

---

## 文档结构

本系统将色彩按照**使用场景**分为 7 大类，每类都有独立的详细文档：

### 📝 [1. 文本色（Text Colors）](./semantic/text-colors.md)

**覆盖场景：** 所有文字相关的颜色

- 层级文本（主要/次要/辅助/禁用）
- 功能文本（链接/成功/警告/错误/信息）
- 特殊文本（占位符/反色/代码）

**Token 数量：** ~20 个

---

### 🎨 [2. 背景色（Background Colors）](./semantic/background-colors.md)

**覆盖场景：** 所有背景填充颜色

- 层级背景（页面/容器/悬浮/输入框）
- 功能背景（成功/警告/错误/信息）
- 状态背景（悬停/选中/禁用/骨架屏）
- 特殊背景（遮罩/斑马纹/代码块）

**Token 数量：** ~30 个

---

### 🔲 [3. 边框色（Border Colors）](./semantic/border-colors.md)

**覆盖场景：** 所有边框和分割线颜色

- 层级边框（主要/次要）
- 功能边框（焦点/错误/成功/警告）
- 分割线（水平/垂直/表格内线）

**Token 数量：** ~15 个

---

### 🔘 [4. 交互色（Interactive Colors）](./semantic/interactive-colors.md)

**覆盖场景：** 所有可交互元素的颜色

- 主要交互（Primary）：默认/悬停/激活/禁用
- 次要交互（Secondary）：默认/悬停/激活/禁用
- 危险交互（Danger）：默认/悬停/激活
- 图标交互

**Token 数量：** ~20 个

---

### ⚡ [5. 功能色（Functional Colors）](./semantic/functional-colors.md)

**覆盖场景：** 语义化的功能反馈颜色

- 成功（Success）：文本/背景/边框/图标
- 警告（Warning）：文本/背景/边框/图标
- 错误（Error）：文本/背景/边框/图标
- 信息（Info）：文本/背景/边框/图标

**Token 数量：** ~20 个

---

### 🎭 [6. 装饰色（Decorative Colors）](./semantic/decorative-colors.md)

**覆盖场景：** 视觉增强和辅助元素颜色

- 阴影（Shadow）：各级深度
- 焦点环（Focus Ring）
- 骨架屏（Skeleton）
- 水印（Watermark）
- 渐变（Gradient）

**Token 数量：** ~15 个

---

### 🧩 [7. 组件色（Component Colors）](./semantic/component-colors.md)

**覆盖场景：** 特定组件专属的颜色

- 按钮（Button）
- 表格（Table）
- 导航（Navigation）
- 表单（Form）
- 通知（Notification）
- 标签（Tag/Badge）
- 步骤条（Steps）
- 代码块（Code）
- 日期选择器（DatePicker）
- ...

**Token 数量：** ~50 个

---

## Token 命名规范

### 基本格式

```
{category}-{element}-{variant}-{state}
```

### 示例

```
text-primary                    # 文本-主要
text-link-hover                 # 文本-链接-悬停
bg-error-subtle                 # 背景-错误-淡色
border-input-focus              # 边框-输入框-聚焦
interactive-primary-hover       # 交互-主要-悬停
functional-success-bg           # 功能-成功-背景
decorative-shadow-md            # 装饰-阴影-中等
component-button-primary-bg     # 组件-按钮-主要-背景
```

---

## 色彩架构

### 三层 Token 体系

```
┌─────────────────────────────────────┐
│   原始色板（Primitive Tokens）        │
│   Gray-50~950, Blue-50~950, ...     │
└──────────────┬──────────────────────┘
               ↓ 引用
┌─────────────────────────────────────┐
│   语义 Token（Semantic Tokens）       │
│   text-primary, bg-error, ...       │
└──────────────┬──────────────────────┘
               ↓ 引用
┌─────────────────────────────────────┐
│   组件 Token（Component Tokens）      │
│   button-primary-bg, ...            │
└─────────────────────────────────────┘
```

### 示例映射关系

```
原始 Token:
  color-gray-900: #111827
  color-blue-600: #2563EB
  color-red-50:   #FEF2F2

      ↓

语义 Token:
  text-primary:      {color-gray-900}
  interactive-primary: {color-blue-600}
  bg-error-subtle:   {color-red-50}

      ↓

组件 Token:
  button-primary-bg:     {interactive-primary}
  input-error-bg:        {bg-error-subtle}
  table-header-text:     {text-primary}
```

---

## 暗色模式支持

所有语义 Token 都支持暗色模式，通过覆盖底层映射实现：

```css
/* 浅色模式 */
:root {
  --text-primary: #111827;           /* Gray-900 */
  --bg-primary: #FFFFFF;
  --interactive-primary: #2563EB;    /* Blue-600 */
}

/* 暗色模式 */
[data-theme="dark"] {
  --text-primary: #F9FAFB;           /* Gray-50 */
  --bg-primary: #111827;             /* Gray-900 */
  --interactive-primary: #3B82F6;    /* Blue-500 */
}
```

**完整映射表请查看：** [暗色模式文档](../dark-mode.md)

---

## 使用原则

### 1. 优先使用语义 Token

```
✅ 推荐：
.text {
  color: var(--text-primary);
}

❌ 不推荐：
.text {
  color: #111827;  /* 硬编码 */
  color: var(--color-gray-900);  /* 直接使用原始 Token */
}
```

### 2. 层级使用规则

| 层级 | 使用场景 | 示例 |
|-----|---------|------|
| **原始 Token** | 仅在定义语义 Token 时使用 | `text-primary: {color-gray-900}` |
| **语义 Token** | 通用场景（90%） | `color: var(--text-primary)` |
| **组件 Token** | 组件内部专属（10%） | `color: var(--button-primary-text)` |

### 3. 避免过度抽象

**❌ 过度：**
```
button-submit-enabled-hover-bg-light-mode
```

**✅ 合理：**
```
button-primary-hover-bg
```

---

## Token 总量统计

| 分类 | Token 数量 | 浅色模式值 | 暗色模式值 |
|-----|-----------|----------|-----------|
| 文本色 | 20 | 20 | 20 |
| 背景色 | 30 | 30 | 30 |
| 边框色 | 15 | 15 | 15 |
| 交互色 | 20 | 20 | 20 |
| 功能色 | 20 | 20 | 20 |
| 装饰色 | 15 | 15 | 15 |
| 组件色 | 50 | 50 | 50 |
| **合计** | **170** | **170** | **170** |

---

## 快速开始

### 1. 查看分类文档

根据您的需求，查看对应的分类文档：

- 设计文本样式 → [文本色文档](./semantic/text-colors.md)
- 设计卡片背景 → [背景色文档](./semantic/background-colors.md)
- 设计按钮 → [交互色文档](./semantic/interactive-colors.md) + [组件色文档](./semantic/component-colors.md)
- 设计错误提示 → [功能色文档](./semantic/functional-colors.md)

### 2. 集成到项目

**CSS Variables 方式：**
```css
@import './tokens/semantic-colors.css';

.my-component {
  color: var(--text-primary);
  background: var(--bg-primary);
  border: 1px solid var(--border-primary);
}
```

**JavaScript/TypeScript 方式：**
```typescript
import { semanticColors } from './tokens/semantic-colors';

const MyButton = styled.button`
  background: ${semanticColors.interactive.primary.default};
  color: ${semanticColors.text.inverse};
`;
```

### 3. Figma 使用

1. 安装 [Tokens Studio](https://www.figma.com/community/plugin/843461159747178978)
2. 导入 `semantic-colors.json`
3. 使用语义化 Token 名称设计

---

## 后续计划

- [ ] 输出完整的 CSS Variables 文件
- [ ] 输出完整的 JSON 文件（Design Tokens Format）
- [ ] 输出 Tailwind CSS 配置
- [ ] 输出 TypeScript 类型定义
- [ ] 创建自动验证脚本（对比度检查）
- [ ] 创建 Figma 插件集成方案

---

## 相关文档

- [Design Token 规范](../README.md) - 总览和基础概念
- [设计原理](../design-principles.md) - 数学公式和设计哲学
- [扩展色板](../color-palette.md) - 12 色完整原始色板
- [暗色模式](../dark-mode.md) - 暗色模式完整映射

---

**文档版本：** v1.0
**最后更新：** 2025-11-16
**维护者：** 设计系统团队
