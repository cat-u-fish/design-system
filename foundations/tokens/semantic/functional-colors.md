# 功能色 Token 清单

> 语义化的功能反馈颜色，用于成功、警告、错误、信息等场景。
> **基于 Material Design 色板系统**

---

## 完整 Token 清单

### 1. 成功色系（Success）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-success-text` | Green-700<br>#388E3C | Green-300<br>#81C784 | 成功文本 |
| `functional-success-bg` | Green-50<br>#E8F5E9 | Green-900<br>#1B5E20 | 成功背景 |
| `functional-success-bg-subtle` | Green-50<br>#E8F5E9 | rgba(76,175,80,0.1) | 极淡成功背景 |
| `functional-success-border` | Green-500<br>#4CAF50 | Green-500<br>#4CAF50 | 成功边框 |
| `functional-success-icon` | Green-700<br>#388E3C | Green-300<br>#81C784 | 成功图标 |

**对比度：** Green-700 = 5.44:1 ✅ AA

---

### 2. 警告色系（Warning）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-warning-text` | Grey-900<br>#212121 | Amber-100<br>#FFECB3 | 警告文本 |
| `functional-warning-bg` | Amber-100<br>#FFECB3 | Amber-900<br>#FF6F00 | 警告背景 |
| `functional-warning-bg-subtle` | Amber-50<br>#FFF8E1 | rgba(255,193,7,0.1) | 极淡警告背景 |
| `functional-warning-border` | Amber-500<br>#FFC107 | Amber-500<br>#FFC107 | 警告边框 |
| `functional-warning-icon` | Amber-900<br>#FF6F00 | Amber-100<br>#FFECB3 | 警告图标 |

**⚠️ 重要：** Material Design 的黄色/琥珀色系对比度普遍较低，不适合直接用于文本。
因此采用 **深色文本 + 浅色背景** 的反转方案确保可访问性。
- 浅色模式：Grey-900 文本 (16.1:1 ✅ AAA) + Amber-100 背景
- 暗色模式：Amber-100 文本 + Amber-900 背景

---

### 3. 错误色系（Error）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-error-text` | Red-700<br>#D32F2F | Red-300<br>#E57373 | 错误文本 |
| `functional-error-bg` | Red-50<br>#FFEBEE | Red-900<br>#B71C1C | 错误背景 |
| `functional-error-bg-subtle` | Red-50<br>#FFEBEE | rgba(244,67,54,0.1) | 极淡错误背景 |
| `functional-error-border` | Red-500<br>#F44336 | Red-500<br>#F44336 | 错误边框 |
| `functional-error-icon` | Red-700<br>#D32F2F | Red-300<br>#E57373 | 错误图标 |

**对比度：** Red-700 = 4.98:1 ✅ AA

---

### 4. 信息色系（Info）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `functional-info-text` | Blue-700<br>#1976D2 | Blue-300<br>#64B5F6 | 信息文本 |
| `functional-info-bg` | Blue-50<br>#E3F2FD | Blue-900<br>#0D47A1 | 信息背景 |
| `functional-info-bg-subtle` | Blue-50<br>#E3F2FD | rgba(33,150,243,0.1) | 极淡信息背景 |
| `functional-info-border` | Blue-500<br>#2196F3 | Blue-500<br>#2196F3 | 信息边框 |
| `functional-info-icon` | Blue-700<br>#1976D2 | Blue-300<br>#64B5F6 | 信息图标 |

**对比度：** Blue-700 = 4.6:1 ✅ AA

---

## CSS Variables 定义

```css
:root {
  /* 成功 */
  --functional-success-text: #388E3C;    /* Green-700, 5.44:1 ✅ AA */
  --functional-success-bg: #E8F5E9;      /* Green-50 */
  --functional-success-bg-subtle: #E8F5E9;
  --functional-success-border: #4CAF50;  /* Green-500 */
  --functional-success-icon: #388E3C;    /* Green-700 */

  /* 警告（反转方案：深色文本 + 浅色背景） */
  --functional-warning-text: #212121;    /* Grey-900, 16.1:1 ✅ AAA */
  --functional-warning-bg: #FFECB3;      /* Amber-100 */
  --functional-warning-bg-subtle: #FFF8E1;  /* Amber-50 */
  --functional-warning-border: #FFC107;  /* Amber-500 */
  --functional-warning-icon: #FF6F00;    /* Amber-900 */

  /* 错误 */
  --functional-error-text: #D32F2F;      /* Red-700, 4.98:1 ✅ AA */
  --functional-error-bg: #FFEBEE;        /* Red-50 */
  --functional-error-bg-subtle: #FFEBEE;
  --functional-error-border: #F44336;    /* Red-500 */
  --functional-error-icon: #D32F2F;      /* Red-700 */

  /* 信息 */
  --functional-info-text: #1976D2;       /* Blue-700, 4.6:1 ✅ AA */
  --functional-info-bg: #E3F2FD;         /* Blue-50 */
  --functional-info-bg-subtle: #E3F2FD;
  --functional-info-border: #2196F3;     /* Blue-500 */
  --functional-info-icon: #1976D2;       /* Blue-700 */
}

[data-theme="dark"] {
  /* 成功 */
  --functional-success-text: #81C784;    /* Green-300 */
  --functional-success-bg: #1B5E20;      /* Green-900 */
  --functional-success-bg-subtle: rgba(76, 175, 80, 0.1);
  --functional-success-border: #4CAF50;  /* Green-500 */
  --functional-success-icon: #81C784;    /* Green-300 */

  /* 警告（反转方案：浅色文本 + 深色背景） */
  --functional-warning-text: #FFECB3;    /* Amber-100 */
  --functional-warning-bg: #FF6F00;      /* Amber-900 */
  --functional-warning-bg-subtle: rgba(255, 193, 7, 0.1);
  --functional-warning-border: #FFC107;  /* Amber-500 */
  --functional-warning-icon: #FFECB3;    /* Amber-100 */

  /* 错误 */
  --functional-error-text: #E57373;      /* Red-300 */
  --functional-error-bg: #B71C1C;        /* Red-900 */
  --functional-error-bg-subtle: rgba(244, 67, 54, 0.1);
  --functional-error-border: #F44336;    /* Red-500 */
  --functional-error-icon: #E57373;      /* Red-300 */

  /* 信息 */
  --functional-info-text: #64B5F6;       /* Blue-300 */
  --functional-info-bg: #0D47A1;         /* Blue-900 */
  --functional-info-bg-subtle: rgba(33, 150, 243, 0.1);
  --functional-info-border: #2196F3;     /* Blue-500 */
  --functional-info-icon: #64B5F6;       /* Blue-300 */
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

### 警告提示（深色文本 + 浅色背景）

```html
<div class="alert alert-warning">
  <svg class="icon icon-warning"></svg>
  <p class="message">请注意！此操作不可撤销</p>
</div>
```

```css
.alert-warning {
  background: var(--functional-warning-bg);  /* Amber-100 浅色背景 */
  border: 1px solid var(--functional-warning-border);
  border-radius: var(--radius-lg);
  padding: var(--spacing-4);
}

.alert-warning .icon-warning {
  color: var(--functional-warning-icon);  /* Amber-900 深色图标 */
}

.alert-warning .message {
  color: var(--functional-warning-text);  /* Grey-900 深色文本，确保高对比度 */
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
  box-shadow: 0 0 0 3px rgba(244, 67, 54, 0.1);
}

.form-field-error .error-message {
  color: var(--functional-error-text);
  font-size: var(--font-size-sm);
  margin-top: var(--spacing-1);
}
```

---

## 设计说明

### 警告色特殊处理

Material Design 的黄色/琥珀色系天生亮度高，所有色阶对比度都低于 WCAG AA 标准：

| 色系 | 最高对比度 | 最深色阶 |
|------|----------|---------|
| Yellow | 2.65:1 | 900 |
| Amber | 2.79:1 | 900 |
| Orange | 3.63:1 | 900 |

**解决方案：**
1. **采用反转方案**：深色文本（Grey-900） + 浅色背景（Amber-100）
2. **确保对比度**：Grey-900 vs Amber-100 ≈ 13.7:1 ✅ AAA
3. **配合图标**：警告图标使用 Amber-900，增强视觉识别度
4. **暗色模式反转**：浅色文本（Amber-100） + 深色背景（Amber-900）

### 其他功能色

- **成功色**：Green-700 (5.44:1 ✅ AA) - 对比度良好
- **错误色**：Red-700 (4.98:1 ✅ AA) - 对比度良好
- **信息色**：Blue-700 (4.6:1 ✅ AA) - 对比度良好

---

**相关文档：**
- [语义化色彩总览](../semantic-colors.md)
- [色板系统](../color-palette.md)
- [文本色 Token](./text-colors.md)
- [背景色 Token](./background-colors.md)

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
