# 背景色 Token 清单

> 所有背景填充相关的颜色定义，覆盖页面、容器、输入框、状态等所有背景场景。
> **基于 Material Design 标准色板系统**

---

## 完整 Token 清单

### 1. 层级背景色（Hierarchy）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-primary` | White<br>#FFFFFF | Grey-900<br>#212121 | 主背景（页面） |
| `bg-secondary` | Grey-50<br>#FAFAFA | Grey-800<br>#424242 | 次级背景（卡片、面板） |
| `bg-tertiary` | Grey-100<br>#F5F5F5 | Grey-700<br>#616161 | 三级背景（悬浮、下拉） |
| `bg-quaternary` | Grey-200<br>#EEEEEE | Grey-600<br>#757575 | 四级背景（极少用） |

---

### 2. 输入/表单背景色（Input）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-input` | White<br>#FFFFFF | Grey-800<br>#424242 | 输入框默认背景 |
| `bg-input-hover` | Grey-50<br>#FAFAFA | Grey-700<br>#616161 | 输入框悬停背景 |
| `bg-input-focus` | White<br>#FFFFFF | Grey-800<br>#424242 | 输入框聚焦背景 |
| `bg-input-disabled` | Grey-100<br>#F5F5F5 | Grey-800<br>#424242 | 输入框禁用背景 |
| `bg-input-readonly` | Grey-50<br>#FAFAFA | Grey-700<br>#616161 | 输入框只读背景 |

---

### 3. 状态背景色（State）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-hover` | Grey-50<br>#FAFAFA | Grey-800<br>#424242 | 通用悬停背景 |
| `bg-active` | Grey-100<br>#F5F5F5 | Grey-700<br>#616161 | 通用激活背景 |
| `bg-selected` | Blue-50<br>#E3F2FD | Blue-900<br>#0D47A1 | 选中项背景 |
| `bg-selected-hover` | Blue-100<br>#BBDEFB | Blue-800<br>#1565C0 | 选中项悬停 |
| `bg-disabled` | Grey-100<br>#F5F5F5 | Grey-800<br>#424242 | 禁用背景 |

---

### 4. 功能反馈背景色（Functional）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-success` | Green-50<br>#E8F5E9 | Green-900<br>#1B5E20 | 成功背景（淡绿） |
| `bg-success-subtle` | Green-50<br>#E8F5E9 | rgba(76,175,80,0.1) | 极淡成功背景 |
| `bg-warning` | Amber-100<br>#FFECB3 | Amber-900<br>#FF6F00 | 警告背景（淡黄，搭配深色文本） |
| `bg-warning-subtle` | Amber-50<br>#FFF8E1 | rgba(255,193,7,0.1) | 极淡警告背景 |
| `bg-error` | Red-50<br>#FFEBEE | Red-900<br>#B71C1C | 错误背景（淡红） |
| `bg-error-subtle` | Red-50<br>#FFEBEE | rgba(244,67,54,0.1) | 极淡错误背景 |
| `bg-info` | Blue-50<br>#E3F2FD | Blue-900<br>#0D47A1 | 信息背景（淡蓝） |
| `bg-info-subtle` | Blue-50<br>#E3F2FD | rgba(33,150,243,0.1) | 极淡信息背景 |

**注意：** 警告色使用 Amber-100 浅色背景，需搭配 Grey-900 深色文本以确保对比度。

---

### 5. 遮罩/覆盖背景色（Overlay）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-overlay` | rgba(0,0,0,0.5) | rgba(0,0,0,0.7) | 模态框遮罩 |
| `bg-overlay-light` | rgba(0,0,0,0.3) | rgba(0,0,0,0.5) | 轻度遮罩 |
| `bg-overlay-heavy` | rgba(0,0,0,0.7) | rgba(0,0,0,0.85) | 重度遮罩 |
| `bg-backdrop-blur` | rgba(255,255,255,0.8) | rgba(17,24,39,0.8) | 毛玻璃遮罩 |

---

### 6. 特殊场景背景色（Special）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-code` | Grey-100<br>#F5F5F5 | Grey-800<br>#424242 | 代码块背景 |
| `bg-code-inline` | Grey-100<br>#F5F5F5 | Grey-800<br>#424242 | 行内代码背景 |
| `bg-skeleton` | Grey-200<br>#EEEEEE | Grey-700<br>#616161 | 骨架屏背景 |
| `bg-skeleton-shimmer` | Grey-100<br>#F5F5F5 | Grey-600<br>#757575 | 骨架屏动画 |
| `bg-tooltip` | Grey-900<br>#212121 | Grey-700<br>#616161 | 工具提示背景 |
| `bg-popover` | White<br>#FFFFFF | Grey-800<br>#424242 | 气泡卡片背景 |
| `bg-modal` | White<br>#FFFFFF | Grey-800<br>#424242 | 模态框背景 |
| `bg-drawer` | White<br>#FFFFFF | Grey-900<br>#212121 | 抽屉背景 |

---

### 7. 表格背景色（Table）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-table-header` | Grey-50<br>#FAFAFA | Grey-800<br>#424242 | 表头背景 |
| `bg-table-row` | White<br>#FFFFFF | Grey-900<br>#212121 | 表格行默认背景 |
| `bg-table-row-hover` | Grey-50<br>#FAFAFA | Grey-800<br>#424242 | 表格行悬停 |
| `bg-table-row-selected` | Blue-50<br>#E3F2FD | Blue-900<br>#0D47A1 | 表格行选中 |
| `bg-table-zebra` | Grey-50<br>#FAFAFA | rgba(66,66,66,0.5) | 斑马纹（偶数行） |

---

## CSS Variables 定义

```css
/* ========== 浅色模式（默认）- Material Design ========== */
:root {
  /* 层级背景 */
  --bg-primary: #FFFFFF;
  --bg-secondary: #FAFAFA;        /* Grey-50 */
  --bg-tertiary: #F5F5F5;         /* Grey-100 */
  --bg-quaternary: #EEEEEE;       /* Grey-200 */

  /* 输入/表单 */
  --bg-input: #FFFFFF;
  --bg-input-hover: #FAFAFA;
  --bg-input-disabled: #F5F5F5;
  --bg-input-readonly: #FAFAFA;

  /* 状态 */
  --bg-hover: #FAFAFA;            /* Grey-50 */
  --bg-active: #F5F5F5;           /* Grey-100 */
  --bg-selected: #E3F2FD;         /* Blue-50 */
  --bg-selected-hover: #BBDEFB;   /* Blue-100 */
  --bg-disabled: #F5F5F5;

  /* 功能反馈 */
  --bg-success: #E8F5E9;          /* Green-50 */
  --bg-warning: #FFECB3;          /* Amber-100 （搭配 Grey-900 文本） */
  --bg-error: #FFEBEE;            /* Red-50 */
  --bg-info: #E3F2FD;             /* Blue-50 */

  /* 遮罩 */
  --bg-overlay: rgba(0,0,0,0.5);

  /* 特殊场景 */
  --bg-code: #F5F5F5;             /* Grey-100 */
  --bg-skeleton: #EEEEEE;         /* Grey-200 */
  --bg-tooltip: #212121;          /* Grey-900 */
  --bg-popover: #FFFFFF;
  --bg-modal: #FFFFFF;
}

/* ========== 暗色模式 ========== */
[data-theme="dark"] {
  /* 层级背景 */
  --bg-primary: #212121;          /* Grey-900 */
  --bg-secondary: #424242;        /* Grey-800 */
  --bg-tertiary: #616161;         /* Grey-700 */
  --bg-quaternary: #757575;       /* Grey-600 */

  /* 输入/表单 */
  --bg-input: #424242;            /* Grey-800 */
  --bg-input-hover: #616161;
  --bg-input-disabled: #424242;
  --bg-input-readonly: #616161;

  /* 状态 */
  --bg-hover: #424242;            /* Grey-800 */
  --bg-active: #616161;           /* Grey-700 */
  --bg-selected: #0D47A1;         /* Blue-900 */
  --bg-selected-hover: #1565C0;   /* Blue-800 */
  --bg-disabled: #424242;

  /* 功能反馈 */
  --bg-success: #1B5E20;          /* Green-900 */
  --bg-warning: #FF6F00;          /* Amber-900 （搭配 Amber-100 文本） */
  --bg-error: #B71C1C;            /* Red-900 */
  --bg-info: #0D47A1;             /* Blue-900 */

  /* 遮罩 */
  --bg-overlay: rgba(0,0,0,0.7);

  /* 特殊场景 */
  --bg-code: #424242;             /* Grey-800 */
  --bg-skeleton: #616161;         /* Grey-700 */
  --bg-tooltip: #616161;          /* Grey-700 */
  --bg-popover: #424242;
  --bg-modal: #424242;
}
```

---

**相关文档：**
- [语义化色彩总览](../semantic-colors.md)
- [文本色 Token](./text-colors.md)
- [边框色 Token](./border-colors.md)
- [色板系统](../color-palette.md) - Material Design 17 色标准色板

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
