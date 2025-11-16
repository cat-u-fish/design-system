# Typography 字体系统 Token

> 完整的字体排版系统，基于数学公式生成，确保视觉层级清晰。
> **基于 14px 基础字号和 1.25 模块化比例**

---

## 目录

1. [字体族](#字体族font-family)
2. [字体大小](#字体大小font-size)
3. [字重](#字重font-weight)
4. [行高](#行高line-height)
5. [字距](#字距letter-spacing)
6. [使用示例](#使用示例)

---

## 字体族（Font Family）

### Token 定义

```
font-family-sans:  "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", "Helvetica Neue", Arial, sans-serif
font-family-serif: "Georgia", "Times New Roman", "Cambria", serif
font-family-mono:  "JetBrains Mono", "Fira Code", "SF Mono", "Consolas", "Courier New", monospace
font-family-zh:    "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "微软雅黑", sans-serif
```

### 使用场景

| Token | 用途 | 示例 |
|-------|------|------|
| `font-family-sans` | 正文、标题、UI 文本（默认） | 按钮、表单、卡片 |
| `font-family-serif` | 长文阅读、博客文章 | 文章正文、引用 |
| `font-family-mono` | 代码、数据、表格数字 | 代码块、API 响应 |
| `font-family-zh` | 中文优化（可与 sans 组合） | 中文界面 |

---

## 字体大小（Font Size）

### 生成公式

```
FontSize(n) = 14px × 1.25^n
```

**取整规则：** 四舍五入到最接近的 2px 倍数

### Token 清单

| Token | 公式 | 原始值 | 最终值 | 用途 |
|-------|------|--------|--------|------|
| `font-size-2xs` | 14 × 1.25^(-2) | 8.96px | **10px** | 极小文本、角标 |
| `font-size-xs` | 14 × 1.25^(-1) | 11.2px | **12px** | 辅助信息、标签 |
| `font-size-sm` | 14 × 1.25^0 | 14px | **14px** | B端基准（正文） |
| `font-size-base` | 14 × 1.25^0 | 14px | **14px** | 别名（= sm） |
| `font-size-lg` | 14 × 1.25^1 | 17.5px | **18px** | 小标题 |
| `font-size-xl` | 14 × 1.25^2 | 21.875px | **22px** | 次级标题 |
| `font-size-2xl` | 14 × 1.25^3 | 27.34px | **28px** | 主标题 (H3) |
| `font-size-3xl` | 14 × 1.25^4 | 34.18px | **34px** | 大标题 (H2) |
| `font-size-4xl` | 14 × 1.25^5 | 42.72px | **42px** | 特大标题 (H1) |
| `font-size-5xl` | 14 × 1.25^6 | 53.4px | **54px** | 超大标题（Hero） |

### 为什么选择 14px 和 1.25？

**14px 基础字号：**
- B端最佳信息密度与可读性平衡点
- 标准办公距离（50-70cm）下舒适阅读
- 中文笔画清晰识别的最小尺寸

**1.25 比例（大三度）：**
- 提供清晰的视觉层级（5-6 级）
- 跳跃适中，不浪费空间
- 取整后的值友好（14 → 18 → 22 → 28）

---

## 字重（Font Weight）

```
font-weight-light:      300    # 轻量（装饰性文本）
font-weight-normal:     400    # 正文默认
font-weight-medium:     500    # 强调文本
font-weight-semibold:   600    # 小标题默认
font-weight-bold:       700    # 大标题默认
```

### 使用建议

| 字重 | 用途 | 最小字号 |
|------|------|---------|
| 300 (Light) | 大标题装饰 | ≥ 28px |
| 400 (Normal) | 正文、描述 | ≥ 14px |
| 500 (Medium) | 强调文本、按钮 | ≥ 14px |
| 600 (Semibold) | 小标题、卡片标题 | ≥ 18px |
| 700 (Bold) | 主标题、重要信息 | ≥ 22px |

---

## 行高（Line Height）

### 生成公式

```
LineHeight(像素) = round(字号 × 理想倍数 / 4px) × 4px
LineHeight(无单位) = LineHeight(像素) / 字号
```

**对齐策略：** 所有行高对齐 4px 网格

### Token 清单

```
line-height-none:    1       # 100%（图标、单行文本）
line-height-tight:   1.14    # 114%（大标题：28px → 32px）
line-height-snug:    1.29    # 129%（小标题：22px → 28px）
line-height-normal:  1.43    # 143%（正文：14px → 20px）
line-height-relaxed: 1.71    # 171%（长文：14px → 24px）
line-height-loose:   2       # 200%（超宽松）
```

### 场景映射

| 场景 | 推荐行高 | 理由 |
|-----|---------|------|
| 功能性文本（表格、表单） | `line-height-normal` (1.43) | 紧凑，节省空间 |
| 正文阅读（卡片、描述） | `line-height-normal` (1.43) | 可读性与空间平衡 |
| 长文本（文章、帮助） | `line-height-relaxed` (1.71) | 舒适阅读 |
| 大标题 | `line-height-tight` (1.14) | 视觉冲击 |
| 按钮文本 | `line-height-none` (1) | 垂直居中 |

---

## 字距（Letter Spacing）

```
letter-spacing-tighter:  -0.05em   # 紧缩（大标题）
letter-spacing-tight:    -0.025em  # 轻微紧缩
letter-spacing-normal:   0         # 默认（正文）
letter-spacing-wide:     0.025em   # 轻微宽松
letter-spacing-wider:    0.05em    # 宽松（小字号）
letter-spacing-widest:   0.1em     # 超宽松（全大写）
```

### 使用建议

- **大标题（≥28px）**：`letter-spacing-tighter` 提升紧密感
- **正文（14px）**：`letter-spacing-normal` 保持默认
- **小字号（≤12px）**：`letter-spacing-wider` 提升辨识度
- **全大写文本**：`letter-spacing-widest` 增强可读性

---

## CSS Variables 定义

```css
:root {
  /* 字体族 */
  --font-family-sans: "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  --font-family-serif: "Georgia", "Times New Roman", serif;
  --font-family-mono: "JetBrains Mono", "Fira Code", monospace;
  --font-family-zh: "PingFang SC", "Microsoft YaHei", sans-serif;

  /* 字体大小 */
  --font-size-2xs: 10px;
  --font-size-xs: 12px;
  --font-size-sm: 14px;
  --font-size-base: 14px;
  --font-size-lg: 18px;
  --font-size-xl: 22px;
  --font-size-2xl: 28px;
  --font-size-3xl: 34px;
  --font-size-4xl: 42px;
  --font-size-5xl: 54px;

  /* 字重 */
  --font-weight-light: 300;
  --font-weight-normal: 400;
  --font-weight-medium: 500;
  --font-weight-semibold: 600;
  --font-weight-bold: 700;

  /* 行高 */
  --line-height-none: 1;
  --line-height-tight: 1.14;
  --line-height-snug: 1.29;
  --line-height-normal: 1.43;
  --line-height-relaxed: 1.71;
  --line-height-loose: 2;

  /* 字距 */
  --letter-spacing-tighter: -0.05em;
  --letter-spacing-tight: -0.025em;
  --letter-spacing-normal: 0;
  --letter-spacing-wide: 0.025em;
  --letter-spacing-wider: 0.05em;
  --letter-spacing-widest: 0.1em;
}
```

---

## 使用示例

### 标题层级

```css
h1 {
  font-size: var(--font-size-4xl);      /* 42px */
  font-weight: var(--font-weight-bold);  /* 700 */
  line-height: var(--line-height-tight); /* 1.14 */
  letter-spacing: var(--letter-spacing-tighter);
}

h2 {
  font-size: var(--font-size-3xl);      /* 34px */
  font-weight: var(--font-weight-bold);
  line-height: var(--line-height-tight);
}

h3 {
  font-size: var(--font-size-2xl);      /* 28px */
  font-weight: var(--font-weight-semibold); /* 600 */
  line-height: var(--line-height-snug);  /* 1.29 */
}

body {
  font-size: var(--font-size-base);     /* 14px */
  font-weight: var(--font-weight-normal); /* 400 */
  line-height: var(--line-height-normal); /* 1.43 */
  font-family: var(--font-family-sans);
}
```

### 组件排版

```css
.button {
  font-size: var(--font-size-sm);       /* 14px */
  font-weight: var(--font-weight-medium); /* 500 */
  line-height: var(--line-height-none);  /* 1 */
}

.card-title {
  font-size: var(--font-size-lg);       /* 18px */
  font-weight: var(--font-weight-semibold);
  line-height: var(--line-height-snug);
}

.label {
  font-size: var(--font-size-xs);       /* 12px */
  font-weight: var(--font-weight-medium);
  line-height: var(--line-height-normal);
  letter-spacing: var(--letter-spacing-wider);
}

.code {
  font-family: var(--font-family-mono);
  font-size: var(--font-size-sm);
  line-height: var(--line-height-relaxed);
}
```

---

**相关文档：**
- [Design Token 规范](./README.md) - 总览
- [设计原理](./design-principles.md) - 数学公式推导

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
**维护者：** 设计系统团队
