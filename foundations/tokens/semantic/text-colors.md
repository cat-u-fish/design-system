# 文本色 Token 清单

> 所有文字相关的颜色定义，覆盖正文、标题、链接、占位符等所有文本场景。

---

## 完整 Token 清单

### 1. 层级文本色（Hierarchy）

| Token | 浅色模式 | 暗色模式 | 对比度（浅） | 对比度（暗） | 用途 |
|-------|---------|---------|------------|------------|------|
| `text-primary` | Gray-900<br>#171717 | Gray-50<br>#FAFAFA | 15.3:1 ✅ AAA | 14.5:1 ✅ AAA | 正文、标题 |
| `text-secondary` | Gray-600<br>#525252 | Gray-300<br>#D4D4D4 | 8.2:1 ✅ AAA | 9.8:1 ✅ AAA | 次要说明、描述 |
| `text-tertiary` | Gray-500<br>#737373 | Gray-400<br>#A3A3A3 | 5.3:1 ✅ AA | 6.2:1 ✅ AAA | 辅助信息、注释 |
| `text-quaternary` | Gray-400<br>#A3A3A3 | Gray-500<br>#737373 | 2.8:1 ⚠️ | 4.1:1 ⚠️ | 极弱提示（慎用） |
| `text-disabled` | Gray-400<br>#A3A3A3 | Gray-600<br>#525252 | 2.8:1 ⚠️ | 3.1:1 ⚠️ | 禁用文本 |
| `text-inverse` | White<br>#FFFFFF | Gray-900<br>#171717 | - | - | 深色背景上的文字 |
| `text-placeholder` | Gray-400<br>#A3A3A3 | Gray-500<br>#737373 | 2.8:1 ⚠️ | 4.1:1 ⚠️ | 输入框占位符 |

**注意：**
- ⚠️ 标记的 Token 对比度不足 4.5:1，仅用于装饰性或禁用状态，不应传达关键信息

---

### 2. 链接文本色（Link）

| Token | 浅色模式 | 暗色模式 | 对比度（浅） | 对比度（暗） | 用途 |
|-------|---------|---------|------------|------------|------|
| `text-link` | Blue-600<br>#0770FA | Blue-400<br>#68A4F3 | 4.5:1 ✅ AA | 6.3:1 ✅ AAA | 默认链接 |
| `text-link-hover` | Blue-700<br>#1D4ED8 | Blue-300<br>#93C5FD | 6.7:1 ✅ AAA | 8.9:1 ✅ AAA | 链接悬停 |
| `text-link-visited` | Purple-600<br>#9333EA | Purple-400<br>#C084FC | 5.2:1 ✅ AA | 6.5:1 ✅ AAA | 已访问链接 |
| `text-link-active` | Blue-800<br>#1E40AF | Blue-200<br>#BFDBFE | 8.2:1 ✅ AAA | 10.2:1 ✅ AAA | 链接激活（按下） |

---

### 3. 功能反馈文本色（Functional）

| Token | 浅色模式 | 暗色模式 | 对比度（浅） | 对比度（暗） | 用途 |
|-------|---------|---------|------------|------------|------|
| `text-success` | Green-600<br>#008937 | Green-400<br>#66F59F | 4.5:1 ✅ AA | 5.5:1 ✅ AA | 成功提示 |
| `text-warning` | Yellow-700<br>#725400 | Yellow-400<br>#F9D162 | 7.0:1 ✅ AAA | 4.8:1 ✅ AA | 警告提示 |
| `text-error` | Red-600<br>#ED0505 | Red-400<br>#F56666 | 4.5:1 ✅ AA | 4.9:1 ✅ AA | 错误提示 |
| `text-info` | Blue-600<br>#0770FA | Blue-400<br>#68A4F3 | 4.5:1 ✅ AA | 6.3:1 ✅ AAA | 信息提示 |

**关键：**
- Yellow 在浅色模式下必须使用 700 色阶（600 对比度仅 3.2:1 ❌）

---

### 4. 品牌/强调文本色（Brand / Emphasis）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `text-brand` | Blue-600<br>#0770FA | Blue-400<br>#68A4F3 | Logo、品牌口号 |
| `text-emphasis` | Blue-700<br>#1D4ED8 | Blue-300<br>#93C5FD | 需要突出的文本 |
| `text-highlight` | Orange-600<br>#EA580C | Orange-400<br>#FB923C | 高亮标记（如搜索结果） |

---

### 5. 特殊场景文本色（Special）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `text-code` | Pink-600<br>#DB2777 | Pink-400<br>#F472B6 | 行内代码 |
| `text-code-keyword` | Purple-600<br>#9333EA | Purple-400<br>#C084FC | 代码关键字 |
| `text-code-string` | Green-600<br>#008937 | Green-400<br>#66F59F | 代码字符串 |
| `text-code-comment` | Gray-500<br>#737373 | Gray-400<br>#A3A3A3 | 代码注释 |
| `text-code-number` | Orange-600<br>#EA580C | Orange-400<br>#FB923C | 代码数字 |

---

## CSS Variables 定义

```css
/* ========== 浅色模式（默认） ========== */
:root {
  /* 层级文本色 */
  --text-primary: #171717;
  --text-secondary: #525252;
  --text-tertiary: #737373;
  --text-quaternary: #A3A3A3;
  --text-disabled: #A3A3A3;
  --text-inverse: #FFFFFF;
  --text-placeholder: #A3A3A3;

  /* 链接文本色 */
  --text-link: #0770FA;
  --text-link-hover: #1D4ED8;
  --text-link-visited: #9333EA;
  --text-link-active: #1E40AF;

  /* 功能反馈文本色 */
  --text-success: #008937;
  --text-warning: #725400;
  --text-error: #ED0505;
  --text-info: #0770FA;

  /* 品牌/强调文本色 */
  --text-brand: #0770FA;
  --text-emphasis: #1D4ED8;
  --text-highlight: #EA580C;

  /* 特殊场景文本色 */
  --text-code: #DB2777;
  --text-code-keyword: #9333EA;
  --text-code-string: #008937;
  --text-code-comment: #737373;
  --text-code-number: #EA580C;
}

/* ========== 暗色模式 ========== */
[data-theme="dark"] {
  /* 层级文本色 */
  --text-primary: #FAFAFA;
  --text-secondary: #D4D4D4;
  --text-tertiary: #A3A3A3;
  --text-quaternary: #737373;
  --text-disabled: #525252;
  --text-inverse: #171717;
  --text-placeholder: #737373;

  /* 链接文本色 */
  --text-link: #60A5FA;
  --text-link-hover: #93C5FD;
  --text-link-visited: #C084FC;
  --text-link-active: #BFDBFE;

  /* 功能反馈文本色 */
  --text-success: #4ADE80;
  --text-warning: #FACC15;
  --text-error: #F87171;
  --text-info: #22D3EE;

  /* 品牌/强调文本色 */
  --text-brand: #60A5FA;
  --text-emphasis: #93C5FD;
  --text-highlight: #FB923C;

  /* 特殊场景文本色 */
  --text-code: #F472B6;
  --text-code-keyword: #C084FC;
  --text-code-string: #4ADE80;
  --text-code-comment: #A3A3A3;
  --text-code-number: #FB923C;
}
```

---

## 使用示例

### HTML + CSS

```html
<h1 class="heading">这是主标题</h1>
<p class="body-text">这是正文内容。</p>
<p class="description">这是次要描述信息。</p>
<a href="#" class="link">这是链接</a>
<p class="error-message">这是错误提示</p>
<code class="inline-code">const x = 10;</code>
```

```css
.heading {
  color: var(--text-primary);
  font-weight: 700;
}

.body-text {
  color: var(--text-primary);
}

.description {
  color: var(--text-secondary);
}

.link {
  color: var(--text-link);
  text-decoration: underline;
}

.link:hover {
  color: var(--text-link-hover);
}

.error-message {
  color: var(--text-error);
}

.inline-code {
  color: var(--text-code);
  background: var(--bg-code);
  padding: 2px 4px;
  border-radius: 4px;
}
```

---

### React + styled-components

```typescript
import styled from 'styled-components';

export const Heading = styled.h1`
  color: var(--text-primary);
  font-size: var(--font-size-2xl);
  font-weight: var(--font-weight-bold);
`;

export const BodyText = styled.p`
  color: var(--text-primary);
  font-size: var(--font-size-base);
  line-height: var(--line-height-normal);
`;

export const Description = styled.p`
  color: var(--text-secondary);
  font-size: var(--font-size-sm);
`;

export const Link = styled.a`
  color: var(--text-link);
  text-decoration: underline;

  &:hover {
    color: var(--text-link-hover);
  }

  &:visited {
    color: var(--text-link-visited);
  }
`;

export const ErrorMessage = styled.p`
  color: var(--text-error);
  font-size: var(--font-size-sm);
`;
```

---

### Tailwind CSS 配置

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      textColor: {
        'primary': 'var(--text-primary)',
        'secondary': 'var(--text-secondary)',
        'tertiary': 'var(--text-tertiary)',
        'disabled': 'var(--text-disabled)',
        'inverse': 'var(--text-inverse)',
        'link': 'var(--text-link)',
        'link-hover': 'var(--text-link-hover)',
        'success': 'var(--text-success)',
        'warning': 'var(--text-warning)',
        'error': 'var(--text-error)',
        'info': 'var(--text-info)',
      },
    },
  },
};
```

**使用：**
```html
<h1 class="text-primary font-bold">标题</h1>
<p class="text-secondary">次要文本</p>
<a class="text-link hover:text-link-hover">链接</a>
<p class="text-error">错误提示</p>
```

---

## 最佳实践

### 1. 文本层级使用场景

| Token | 典型场景 | 不建议场景 |
|-------|---------|----------|
| `text-primary` | 正文、标题、重要信息 | 禁用状态 |
| `text-secondary` | 描述、说明、次要信息 | 主标题 |
| `text-tertiary` | 辅助信息、时间戳、元数据 | 关键操作提示 |
| `text-disabled` | 禁用按钮文字、不可操作项 | 正常可读文本 |
| `text-placeholder` | 输入框占位符 | 实际输入内容 |

---

### 2. 避免对比度不足

**❌ 错误：**
```css
/* text-quaternary 对比度仅 2.8:1 */
.important-message {
  color: var(--text-quaternary); /* ❌ 关键信息不应使用 */
}
```

**✅ 正确：**
```css
.important-message {
  color: var(--text-primary); /* ✅ 使用高对比度 */
}

.optional-metadata {
  color: var(--text-tertiary); /* ✅ 非关键信息可用 */
}
```

---

### 3. 链接状态管理

```css
/* 完整的链接状态 */
.link {
  color: var(--text-link);
  text-decoration: underline;
  cursor: pointer;
}

.link:hover {
  color: var(--text-link-hover);
}

.link:visited {
  color: var(--text-link-visited);
}

.link:active {
  color: var(--text-link-active);
}

.link:focus-visible {
  outline: 2px solid var(--border-focus);
  outline-offset: 2px;
}
```

---

### 4. 功能色使用原则

**何时使用：**
- ✅ 表单验证反馈
- ✅ 操作结果提示
- ✅ 状态标识
- ✅ 警示信息

**何时不使用：**
- ❌ 装饰性文本
- ❌ 正文内容
- ❌ 普通标题

---

### 5. 代码高亮建议

```html
<pre><code class="code-block">
  <span class="code-keyword">const</span>
  <span class="code-variable">message</span>
  = <span class="code-string">"Hello World"</span>;
  <span class="code-comment">// This is a comment</span>
</code></pre>
```

```css
.code-block {
  background: var(--bg-code);
  color: var(--text-primary);
  padding: var(--spacing-4);
  border-radius: var(--radius-lg);
}

.code-keyword {
  color: var(--text-code-keyword);
  font-weight: var(--font-weight-semibold);
}

.code-string {
  color: var(--text-code-string);
}

.code-comment {
  color: var(--text-code-comment);
  font-style: italic;
}

.code-number {
  color: var(--text-code-number);
}
```

---

## 对比度验证清单

使用前请确认：

- [ ] 主要文本（text-primary）对比度 ≥ 7:1（AAA 级）
- [ ] 次要文本（text-secondary）对比度 ≥ 7:1（AAA 级）
- [ ] 辅助文本（text-tertiary）对比度 ≥ 4.5:1（AA 级）
- [ ] 链接文本（text-link）对比度 ≥ 4.5:1（AA 级）
- [ ] 功能色文本（error/warning/success）对比度 ≥ 4.5:1（AA 级）
- [ ] 禁用文本（text-disabled）对比度 < 4.5:1（仅装饰，不传达信息）

---

## JSON 格式定义

```json
{
  "text": {
    "primary": {
      "value": "#171717",
      "$extensions": {
        "mode": {
          "dark": "#FAFAFA"
        }
      },
      "type": "color",
      "description": "主要文本，对比度 15.3:1 (AAA)"
    },
    "link": {
      "value": "#0770FA",
      "$extensions": {
        "mode": {
          "dark": "#60A5FA"
        }
      },
      "type": "color",
      "description": "链接文本，对比度 5.3:1 (AA)"
    },
    "error": {
      "value": "#ED0505",
      "$extensions": {
        "mode": {
          "dark": "#F87171"
        }
      },
      "type": "color",
      "description": "错误文本，对比度 5.9:1 (AA)"
    }
  }
}
```

---

**相关文档：**
- [语义化色彩总览](../semantic-colors.md)
- [背景色 Token](./background-colors.md)
- [功能色 Token](./functional-colors.md)

**文档版本：** v1.0
**最后更新：** 2025-11-16
