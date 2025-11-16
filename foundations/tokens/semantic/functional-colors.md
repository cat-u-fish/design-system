# 功能色 Token 清单

> 语义化的功能反馈颜色，用于成功、警告、错误、信息等场景。

---

## 完整 Token 清单

### 1. 成功色系（Success）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-success-text` | Green-600<br>#008937 | Green-400<br>#66F59F | 成功文本 |
| `functional-success-bg` | Green-50<br>#F4FAF7 | Green-950<br>#003314 | 成功背景 |
| `functional-success-bg-subtle` | Green-50<br>#F4FAF7 | rgba(0,137,55,0.1) | 极淡成功背景 |
| `functional-success-border` | Green-500<br>#38FA86 | Green-500<br>#38FA86 | 成功边框 |
| `functional-success-icon` | Green-600<br>#008937 | Green-400<br>#66F59F | 成功图标 |

---

### 2. 警告色系（Warning）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-warning-text` | Yellow-700<br>#725400 | Yellow-400<br>#F9D162 | 警告文本 |
| `functional-warning-bg` | Yellow-50<br>#FBF9F4 | Yellow-950<br>#332500 | 警告背景 |
| `functional-warning-bg-subtle` | Yellow-50<br>#FBF9F4 | rgba(255,201,51,0.1) | 极淡警告背景 |
| `functional-warning-border` | Yellow-500<br>#FFC933 | Yellow-500<br>#FFC933 | 警告边框 |
| `functional-warning-icon` | Yellow-700<br>#725400 | Yellow-400<br>#F9D162 | 警告图标 |

**重要：** Yellow 600 已偏棕色且对比度勉强达标，文本和图标必须使用 Yellow-700

---

### 3. 错误色系（Error）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-error-text` | Red-600<br>#ED0505 | Red-400<br>#F56666 | 错误文本 |
| `functional-error-bg` | Red-50<br>#FAF4F4 | Red-950<br>#380000 | 错误背景 |
| `functional-error-bg-subtle` | Red-50<br>#FAF4F4 | rgba(237,5,5,0.1) | 极淡错误背景 |
| `functional-error-border` | Red-500<br>#F83A3A | Red-500<br>#F83A3A | 错误边框 |
| `functional-error-icon` | Red-600<br>#ED0505 | Red-400<br>#F56666 | 错误图标 |

---

### 4. 信息色系（Info）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-info-text` | Blue-600<br>#0770FA | Blue-400<br>#68A4F3 | 信息文本 |
| `functional-info-bg` | Blue-50<br>#F5F7FA | Blue-950<br>#011C40 | 信息背景 |
| `functional-info-bg-subtle` | Blue-50<br>#F5F7FA | rgba(7,112,250,0.1) | 极淡信息背景 |
| `functional-info-border` | Blue-500<br>#3B8CF7 | Blue-500<br>#3B8CF7 | 信息边框 |
| `functional-info-icon` | Blue-600<br>#0770FA | Blue-400<br>#68A4F3 | 信息图标 |

---

## CSS Variables 定义

```css
:root {
  /* 成功 */
  --functional-success-text: #008937;    /* Green-600, 4.5:1 ✅ */
  --functional-success-bg: #F4FAF7;      /* Green-50 */
  --functional-success-border: #38FA86;  /* Green-500 */

  /* 警告 */
  --functional-warning-text: #725400;    /* Yellow-700, 7.0:1 ✅ */
  --functional-warning-bg: #FBF9F4;      /* Yellow-50 */
  --functional-warning-border: #FFC933;  /* Yellow-500 */

  /* 错误 */
  --functional-error-text: #ED0505;      /* Red-600, 4.5:1 ✅ */
  --functional-error-bg: #FAF4F4;        /* Red-50 */
  --functional-error-border: #F83A3A;    /* Red-500 */

  /* 信息 */
  --functional-info-text: #0770FA;       /* Blue-600, 4.5:1 ✅ */
  --functional-info-bg: #F5F7FA;         /* Blue-50 */
  --functional-info-border: #3B8CF7;     /* Blue-500 */
}

[data-theme="dark"] {
  /* 成功 */
  --functional-success-text: #66F59F;    /* Green-400 */
  --functional-success-bg: #003314;      /* Green-950 */
  --functional-success-border: #38FA86;  /* Green-500 */

  /* 警告 */
  --functional-warning-text: #F9D162;    /* Yellow-400 */
  --functional-warning-bg: #332500;      /* Yellow-950 */
  --functional-warning-border: #FFC933;  /* Yellow-500 */

  /* 错误 */
  --functional-error-text: #F56666;      /* Red-400 */
  --functional-error-bg: #380000;        /* Red-950 */
  --functional-error-border: #F83A3A;    /* Red-500 */

  /* 信息 */
  --functional-info-text: #68A4F3;       /* Blue-400 */
  --functional-info-bg: #011C40;         /* Blue-950 */
  --functional-info-border: #3B8CF7;     /* Blue-500 */
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
