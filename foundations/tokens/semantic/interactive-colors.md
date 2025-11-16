# 交互色 Token 清单

> 所有可交互元素（按钮、链接、图标等）的颜色定义，覆盖所有交互状态。
> **基于 Material Design 标准色板系统**

---

## 完整 Token 清单

### 1. 主要交互色（Primary Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-primary` | Blue-700<br>#1976D2 | Blue-500<br>#2196F3 | 主按钮默认 |
| `interactive-primary-hover` | Blue-800<br>#1565C0 | Blue-400<br>#42A5F5 | 主按钮悬停 |
| `interactive-primary-active` | Blue-900<br>#0D47A1 | Blue-300<br>#64B5F6 | 主按钮按下 |
| `interactive-primary-disabled` | Grey-300<br>#E0E0E0 | Grey-700<br>#616161 | 主按钮禁用 |

---

### 2. 次要交互色（Secondary Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-secondary` | Grey-600<br>#757575 | Grey-400<br>#BDBDBD | 次按钮默认 |
| `interactive-secondary-hover` | Grey-700<br>#616161 | Grey-300<br>#E0E0E0 | 次按钮悬停 |
| `interactive-secondary-active` | Grey-800<br>#424242 | Grey-200<br>#EEEEEE | 次按钮按下 |
| `interactive-secondary-disabled` | Grey-300<br>#E0E0E0 | Grey-700<br>#616161 | 次按钮禁用 |

---

### 3. 危险交互色（Danger Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-danger` | Red-700<br>#D32F2F | Red-500<br>#F44336 | 危险按钮默认 |
| `interactive-danger-hover` | Red-800<br>#C62828 | Red-400<br>#EF5350 | 危险按钮悬停 |
| `interactive-danger-active` | Red-900<br>#B71C1C | Red-300<br>#E57373 | 危险按钮按下 |
| `interactive-danger-disabled` | Grey-300<br>#E0E0E0 | Grey-700<br>#616161 | 危险按钮禁用 |

---

### 4. 成功交互色（Success Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-success` | Green-700<br>#388E3C | Green-500<br>#4CAF50 | 成功按钮默认 |
| `interactive-success-hover` | Green-800<br>#2E7D32 | Green-400<br>#66BB6A | 成功按钮悬停 |
| `interactive-success-active` | Green-900<br>#1B5E20 | Green-300<br>#81C784 | 成功按钮按下 |

---

### 5. 图标交互色（Icon Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-icon` | Grey-600<br>#757575 | Grey-400<br>#BDBDBD | 默认图标 |
| `interactive-icon-hover` | Grey-900<br>#212121 | Grey-200<br>#EEEEEE | 图标悬停 |
| `interactive-icon-active` | Blue-700<br>#1976D2 | Blue-300<br>#64B5F6 | 图标激活 |
| `interactive-icon-disabled` | Grey-400<br>#BDBDBD | Grey-600<br>#757575 | 图标禁用 |

---

### 6. 链接交互色（Link Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-link` | Blue-700<br>#1976D2 | Blue-300<br>#64B5F6 | 链接默认 |
| `interactive-link-hover` | Blue-800<br>#1565C0 | Blue-200<br>#90CAF9 | 链接悬停 |
| `interactive-link-visited` | Purple-700<br>#7B1FA2 | Purple-300<br>#BA68C8 | 已访问链接 |
| `interactive-link-active` | Blue-900<br>#0D47A1 | Blue-100<br>#BBDEFB | 链接按下 |

---

## CSS Variables 定义

```css
/* ========== 浅色模式（默认）- Material Design ========== */
:root {
  /* 主要交互 */
  --interactive-primary: #1976D2;           /* Blue-700 */
  --interactive-primary-hover: #1565C0;     /* Blue-800 */
  --interactive-primary-active: #0D47A1;    /* Blue-900 */
  --interactive-primary-disabled: #E0E0E0;  /* Grey-300 */

  /* 次要交互 */
  --interactive-secondary: #757575;         /* Grey-600 */
  --interactive-secondary-hover: #616161;   /* Grey-700 */
  --interactive-secondary-active: #424242;  /* Grey-800 */
  --interactive-secondary-disabled: #E0E0E0;  /* Grey-300 */

  /* 危险交互 */
  --interactive-danger: #D32F2F;            /* Red-700 */
  --interactive-danger-hover: #C62828;      /* Red-800 */
  --interactive-danger-active: #B71C1C;     /* Red-900 */
  --interactive-danger-disabled: #E0E0E0;   /* Grey-300 */

  /* 成功交互 */
  --interactive-success: #388E3C;           /* Green-700 */
  --interactive-success-hover: #2E7D32;     /* Green-800 */
  --interactive-success-active: #1B5E20;    /* Green-900 */

  /* 图标交互 */
  --interactive-icon: #757575;              /* Grey-600 */
  --interactive-icon-hover: #212121;        /* Grey-900 */
  --interactive-icon-active: #1976D2;       /* Blue-700 */
  --interactive-icon-disabled: #BDBDBD;     /* Grey-400 */

  /* 链接交互 */
  --interactive-link: #1976D2;              /* Blue-700 */
  --interactive-link-hover: #1565C0;        /* Blue-800 */
  --interactive-link-visited: #7B1FA2;      /* Purple-700 */
  --interactive-link-active: #0D47A1;       /* Blue-900 */
}

/* ========== 暗色模式 ========== */
[data-theme="dark"] {
  /* 主要交互 */
  --interactive-primary: #2196F3;           /* Blue-500 */
  --interactive-primary-hover: #42A5F5;     /* Blue-400 */
  --interactive-primary-active: #64B5F6;    /* Blue-300 */
  --interactive-primary-disabled: #616161;  /* Grey-700 */

  /* 次要交互 */
  --interactive-secondary: #BDBDBD;         /* Grey-400 */
  --interactive-secondary-hover: #E0E0E0;   /* Grey-300 */
  --interactive-secondary-active: #EEEEEE;  /* Grey-200 */
  --interactive-secondary-disabled: #616161;  /* Grey-700 */

  /* 危险交互 */
  --interactive-danger: #F44336;            /* Red-500 */
  --interactive-danger-hover: #EF5350;      /* Red-400 */
  --interactive-danger-active: #E57373;     /* Red-300 */
  --interactive-danger-disabled: #616161;   /* Grey-700 */

  /* 成功交互 */
  --interactive-success: #4CAF50;           /* Green-500 */
  --interactive-success-hover: #66BB6A;     /* Green-400 */
  --interactive-success-active: #81C784;    /* Green-300 */

  /* 图标交互 */
  --interactive-icon: #BDBDBD;              /* Grey-400 */
  --interactive-icon-hover: #EEEEEE;        /* Grey-200 */
  --interactive-icon-active: #64B5F6;       /* Blue-300 */
  --interactive-icon-disabled: #757575;     /* Grey-600 */

  /* 链接交互 */
  --interactive-link: #64B5F6;              /* Blue-300 */
  --interactive-link-hover: #90CAF9;        /* Blue-200 */
  --interactive-link-visited: #BA68C8;      /* Purple-300 */
  --interactive-link-active: #BBDEFB;       /* Blue-100 */
}
```

---

## 使用示例

### 主按钮

```css
.button-primary {
  background: var(--interactive-primary);
  color: var(--text-inverse);
  border: none;
}

.button-primary:hover {
  background: var(--interactive-primary-hover);
}

.button-primary:active {
  background: var(--interactive-primary-active);
}

.button-primary:disabled {
  background: var(--interactive-primary-disabled);
  cursor: not-allowed;
}
```

### 图标按钮

```css
.icon-button {
  color: var(--interactive-icon);
  background: transparent;
}

.icon-button:hover {
  color: var(--interactive-icon-hover);
  background: var(--bg-hover);
}
```

---

**相关文档：**
- [语义化色彩总览](../semantic-colors.md)
- [组件色 Token](./component-colors.md)
- [色板系统](../color-palette.md) - Material Design 17 色标准色板

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
