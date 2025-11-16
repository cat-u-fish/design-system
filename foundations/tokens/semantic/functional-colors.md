# 功能色 Token 清单

> 语义化的功能反馈颜色，用于成功、警告、错误、信息等场景。

---

## 完整 Token 清单

### 1. 成功色系（Success）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-success-text` | Green-600<br>#16A34A | Green-400<br>#4ADE80 | 成功文本 |
| `functional-success-bg` | Green-50<br>#F0FDF4 | Green-950<br>#052E16 | 成功背景 |
| `functional-success-bg-subtle` | Green-50<br>#F0FDF4 | rgba(34,197,94,0.1) | 极淡成功背景 |
| `functional-success-border` | Green-500<br>#22C55E | Green-500<br>#22C55E | 成功边框 |
| `functional-success-icon` | Green-600<br>#16A34A | Green-400<br>#4ADE80 | 成功图标 |

---

### 2. 警告色系（Warning）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-warning-text` | Yellow-700<br>#A16207 | Yellow-400<br>#FACC15 | 警告文本 |
| `functional-warning-bg` | Yellow-50<br>#FEFCE8 | Yellow-950<br>#422006 | 警告背景 |
| `functional-warning-bg-subtle` | Yellow-50<br>#FEFCE8 | rgba(234,179,8,0.1) | 极淡警告背景 |
| `functional-warning-border` | Yellow-500<br>#EAB308 | Yellow-500<br>#EAB308 | 警告边框 |
| `functional-warning-icon` | Yellow-600<br>#CA8A04 | Yellow-400<br>#FACC15 | 警告图标 |

**重要：** Yellow 600 对比度不足，文本必须使用 Yellow-700

---

### 3. 错误色系（Error）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-error-text` | Red-600<br>#DC2626 | Red-400<br>#F87171 | 错误文本 |
| `functional-error-bg` | Red-50<br>#FEF2F2 | Red-950<br>#450A0A | 错误背景 |
| `functional-error-bg-subtle` | Red-50<br>#FEF2F2 | rgba(239,68,68,0.1) | 极淡错误背景 |
| `functional-error-border` | Red-500<br>#EF4444 | Red-500<br>#EF4444 | 错误边框 |
| `functional-error-icon` | Red-600<br>#DC2626 | Red-400<br>#F87171 | 错误图标 |

---

### 4. 信息色系（Info）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-info-text` | Cyan-600<br>#0891B2 | Cyan-400<br>#22D3EE | 信息文本 |
| `functional-info-bg` | Cyan-50<br>#ECFEFF | Cyan-950<br>#083344 | 信息背景 |
| `functional-info-bg-subtle` | Cyan-50<br>#ECFEFF | rgba(6,182,212,0.1) | 极淡信息背景 |
| `functional-info-border` | Cyan-500<br>#06B6D4 | Cyan-500<br>#06B6D4 | 信息边框 |
| `functional-info-icon` | Cyan-600<br>#0891B2 | Cyan-400<br>#22D3EE | 信息图标 |

---

## CSS Variables 定义

```css
:root {
  /* 成功 */
  --functional-success-text: #16A34A;
  --functional-success-bg: #F0FDF4;
  --functional-success-border: #22C55E;
  
  /* 警告 */
  --functional-warning-text: #A16207;
  --functional-warning-bg: #FEFCE8;
  --functional-warning-border: #EAB308;
  
  /* 错误 */
  --functional-error-text: #DC2626;
  --functional-error-bg: #FEF2F2;
  --functional-error-border: #EF4444;
  
  /* 信息 */
  --functional-info-text: #0891B2;
  --functional-info-bg: #ECFEFF;
  --functional-info-border: #06B6D4;
}

[data-theme="dark"] {
  /* 成功 */
  --functional-success-text: #4ADE80;
  --functional-success-bg: #052E16;
  --functional-success-border: #22C55E;
  
  /* 警告 */
  --functional-warning-text: #FACC15;
  --functional-warning-bg: #422006;
  --functional-warning-border: #EAB308;
  
  /* 错误 */
  --functional-error-text: #F87171;
  --functional-error-bg: #450A0A;
  --functional-error-border: #EF4444;
  
  /* 信息 */
  --functional-info-text: #22D3EE;
  --functional-info-bg: #083344;
  --functional-info-border: #06B6D4;
}
```

---

## 使用示例

### 成功提示

```html
<div class="alert alert-success">
  <svg class="icon icon-success"></svg>
  <p class="message">操作成功！</p>
</div>
```

```css
.alert-success {
  background: var(--functional-success-bg);
  border: 1px solid var(--functional-success-border);
  border-radius: var(--radius-lg);
  padding: var(--spacing-4);
}

.alert-success .icon-success {
  color: var(--functional-success-icon);
}

.alert-success .message {
  color: var(--functional-success-text);
}
```

### 表单验证

```html
<div class="form-field form-field-error">
  <input type="email" class="input" />
  <p class="error-message">请输入有效的邮箱地址</p>
</div>
```

```css
.form-field-error .input {
  border-color: var(--functional-error-border);
  background: var(--functional-error-bg-subtle);
}

.form-field-error .input:focus {
  border-color: var(--functional-error-border);
  box-shadow: 0 0 0 3px rgba(239, 68, 68, 0.1);
}

.form-field-error .error-message {
  color: var(--functional-error-text);
  font-size: var(--font-size-sm);
  margin-top: var(--spacing-1);
}
```

---

**相关文档：**
- [语义化色彩总览](../semantic-colors.md)
- [文本色 Token](./text-colors.md)
- [背景色 Token](./background-colors.md)

**文档版本：** v1.0
**最后更新：** 2025-11-16
