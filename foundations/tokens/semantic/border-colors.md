# 边框色 Token 清单

> 所有边框和分割线相关的颜色定义。
> **基于 Material Design 标准色板系统**

---

## 完整 Token 清单

### 1. 层级边框色（Hierarchy）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `border-primary` | Grey-300<br>#E0E0E0 | Grey-700<br>#616161 | 主边框（输入框、卡片） |
| `border-secondary` | Grey-200<br>#EEEEEE | Grey-800<br>#424242 | 次级边框（表格内线） |
| `border-tertiary` | Grey-100<br>#F5F5F5 | Grey-900<br>#212121 | 三级边框（极弱分割） |

---

### 2. 状态边框色（State）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `border-hover` | Grey-400<br>#BDBDBD | Grey-600<br>#757575 | 悬停边框 |
| `border-focus` | Blue-500<br>#2196F3 | Blue-500<br>#2196F3 | 焦点边框 |
| `border-active` | Blue-700<br>#1976D2 | Blue-300<br>#64B5F6 | 激活边框 |
| `border-disabled` | Grey-200<br>#EEEEEE | Grey-800<br>#424242 | 禁用边框 |
| `border-selected` | Blue-700<br>#1976D2 | Blue-300<br>#64B5F6 | 选中边框 |

---

### 3. 功能反馈边框色（Functional）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `border-success` | Green-500<br>#4CAF50 | Green-500<br>#4CAF50 | 成功边框 |
| `border-warning` | Amber-500<br>#FFC107 | Amber-500<br>#FFC107 | 警告边框 |
| `border-error` | Red-500<br>#F44336 | Red-500<br>#F44336 | 错误边框 |
| `border-info` | Blue-500<br>#2196F3 | Blue-500<br>#2196F3 | 信息边框 |

**注意：** 功能色边框在浅色/暗色模式保持一致（500 色阶），确保视觉连续性

---

### 4. 分割线（Divider）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `divider-primary` | Grey-200<br>#EEEEEE | Grey-700<br>#616161 | 主分割线 |
| `divider-secondary` | Grey-100<br>#F5F5F5 | Grey-800<br>#424242 | 次级分割线 |
| `divider-strong` | Grey-300<br>#E0E0E0 | Grey-600<br>#757575 | 强调分割线 |

---

## CSS Variables 定义

```css
/* ========== 浅色模式（默认）- Material Design ========== */
:root {
  /* 层级边框 */
  --border-primary: #E0E0E0;      /* Grey-300 */
  --border-secondary: #EEEEEE;    /* Grey-200 */
  --border-tertiary: #F5F5F5;     /* Grey-100 */

  /* 状态边框 */
  --border-hover: #BDBDBD;        /* Grey-400 */
  --border-focus: #2196F3;        /* Blue-500 */
  --border-active: #1976D2;       /* Blue-700 */
  --border-disabled: #EEEEEE;     /* Grey-200 */
  --border-selected: #1976D2;     /* Blue-700 */

  /* 功能边框 */
  --border-success: #4CAF50;      /* Green-500 */
  --border-warning: #FFC107;      /* Amber-500 */
  --border-error: #F44336;        /* Red-500 */
  --border-info: #2196F3;         /* Blue-500 */

  /* 分割线 */
  --divider-primary: #EEEEEE;     /* Grey-200 */
  --divider-secondary: #F5F5F5;   /* Grey-100 */
  --divider-strong: #E0E0E0;      /* Grey-300 */
}

/* ========== 暗色模式 ========== */
[data-theme="dark"] {
  /* 层级边框 */
  --border-primary: #616161;      /* Grey-700 */
  --border-secondary: #424242;    /* Grey-800 */
  --border-tertiary: #212121;     /* Grey-900 */

  /* 状态边框 */
  --border-hover: #757575;        /* Grey-600 */
  --border-focus: #2196F3;        /* Blue-500 */
  --border-active: #64B5F6;       /* Blue-300 */
  --border-disabled: #424242;     /* Grey-800 */
  --border-selected: #64B5F6;     /* Blue-300 */

  /* 功能边框（保持一致） */
  --border-success: #4CAF50;      /* Green-500 */
  --border-warning: #FFC107;      /* Amber-500 */
  --border-error: #F44336;        /* Red-500 */
  --border-info: #2196F3;         /* Blue-500 */

  /* 分割线 */
  --divider-primary: #616161;     /* Grey-700 */
  --divider-secondary: #424242;   /* Grey-800 */
  --divider-strong: #757575;      /* Grey-600 */
}
```

---

**相关文档：**
- [语义化色彩总览](../semantic-colors.md)
- [背景色 Token](./background-colors.md)
- [色板系统](../color-palette.md) - Material Design 17 色标准色板

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
