# 交互色 Token 清单

> 所有可交互元素（按钮、链接、图标等）的颜色定义，覆盖所有交互状态。

---

## 完整 Token 清单

### 1. 主要交互色（Primary Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-primary` | Blue-600<br>#2563EB | Blue-500<br>#3B82F6 | 主按钮默认 |
| `interactive-primary-hover` | Blue-700<br>#1D4ED8 | Blue-400<br>#60A5FA | 主按钮悬停 |
| `interactive-primary-active` | Blue-800<br>#1E40AF | Blue-300<br>#93C5FD | 主按钮按下 |
| `interactive-primary-disabled` | Gray-300<br>#D4D4D4 | Gray-700<br>#404040 | 主按钮禁用 |

---

### 2. 次要交互色（Secondary Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-secondary` | Gray-600<br>#525252 | Gray-400<br>#A3A3A3 | 次按钮默认 |
| `interactive-secondary-hover` | Gray-700<br>#404040 | Gray-300<br>#D4D4D4 | 次按钮悬停 |
| `interactive-secondary-active` | Gray-800<br>#262626 | Gray-200<br>#E5E5E5 | 次按钮按下 |
| `interactive-secondary-disabled` | Gray-300<br>#D4D4D4 | Gray-700<br>#404040 | 次按钮禁用 |

---

### 3. 危险交互色（Danger Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-danger` | Red-600<br>#DC2626 | Red-500<br>#EF4444 | 危险按钮默认 |
| `interactive-danger-hover` | Red-700<br>#B91C1C | Red-400<br>#F87171 | 危险按钮悬停 |
| `interactive-danger-active` | Red-800<br>#991B1B | Red-300<br>#FCA5A5 | 危险按钮按下 |
| `interactive-danger-disabled` | Gray-300<br>#D4D4D4 | Gray-700<br>#404040 | 危险按钮禁用 |

---

### 4. 成功交互色（Success Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-success` | Green-600<br>#16A34A | Green-500<br>#22C55E | 成功按钮默认 |
| `interactive-success-hover` | Green-700<br>#15803D | Green-400<br>#4ADE80 | 成功按钮悬停 |
| `interactive-success-active` | Green-800<br>#166534 | Green-300<br>#86EFAC | 成功按钮按下 |

---

### 5. 图标交互色（Icon Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-icon` | Gray-600<br>#525252 | Gray-400<br>#A3A3A3 | 默认图标 |
| `interactive-icon-hover` | Gray-900<br>#171717 | Gray-200<br>#E5E5E5 | 图标悬停 |
| `interactive-icon-active` | Blue-600<br>#2563EB | Blue-400<br>#60A5FA | 图标激活 |
| `interactive-icon-disabled` | Gray-400<br>#A3A3A3 | Gray-600<br>#525252 | 图标禁用 |

---

### 6. 链接交互色（Link Interactive）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `interactive-link` | Blue-600<br>#2563EB | Blue-400<br>#60A5FA | 链接默认 |
| `interactive-link-hover` | Blue-700<br>#1D4ED8 | Blue-300<br>#93C5FD | 链接悬停 |
| `interactive-link-visited` | Purple-600<br>#9333EA | Purple-400<br>#C084FC | 已访问链接 |
| `interactive-link-active` | Blue-800<br>#1E40AF | Blue-200<br>#BFDBFE | 链接按下 |

---

## CSS Variables 定义

```css
:root {
  /* 主要交互 */
  --interactive-primary: #2563EB;
  --interactive-primary-hover: #1D4ED8;
  --interactive-primary-active: #1E40AF;
  --interactive-primary-disabled: #D4D4D4;
  
  /* 次要交互 */
  --interactive-secondary: #525252;
  --interactive-secondary-hover: #404040;
  
  /* 危险交互 */
  --interactive-danger: #DC2626;
  --interactive-danger-hover: #B91C1C;
  
  /* 图标交互 */
  --interactive-icon: #525252;
  --interactive-icon-hover: #171717;
}

[data-theme="dark"] {
  /* 主要交互 */
  --interactive-primary: #3B82F6;
  --interactive-primary-hover: #60A5FA;
  --interactive-primary-active: #93C5FD;
  --interactive-primary-disabled: #404040;
  
  /* 次要交互 */
  --interactive-secondary: #A3A3A3;
  --interactive-secondary-hover: #D4D4D4;
  
  /* 危险交互 */
  --interactive-danger: #EF4444;
  --interactive-danger-hover: #F87171;
  
  /* 图标交互 */
  --interactive-icon: #A3A3A3;
  --interactive-icon-hover: #E5E5E5;
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

**文档版本：** v1.0
**最后更新：** 2025-11-16
