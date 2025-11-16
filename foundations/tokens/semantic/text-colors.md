# 文本色 Token 清单

> 所有文字相关的颜色定义，覆盖正文、标题、链接、占位符等所有文本场景。
> **基于 Material Design 标准色板系统**

---

## 完整 Token 清单

### 1. 层级文本色（Hierarchy）

| Token | 浅色模式 | 暗色模式 | 对比度（浅） | 对比度（暗） | 用途 |
|-------|---------|---------|------------|------------|------|
| `text-primary` | Grey-900<br>#212121 | Grey-50<br>#FAFAFA | 16.1:1 ✅ AAA | 18.5:1 ✅ AAA | 正文、标题 |
| `text-secondary` | Grey-600<br>#757575 | Grey-300<br>#E0E0E0 | 4.68:1 ✅ AA | 11.5:1 ✅ AAA | 次要说明、描述 |
| `text-tertiary` | Grey-500<br>#9E9E9E | Grey-400<br>#BDBDBD | 3.15:1 ⚠️ | 7.8:1 ✅ AAA | 辅助信息、注释 |
| `text-quaternary` | Grey-400<br>#BDBDBD | Grey-500<br>#9E9E9E | 2.26:1 ⚠️ | 5.6:1 ✅ AA | 极弱提示（慎用） |
| `text-disabled` | Grey-400<br>#BDBDBD | Grey-600<br>#757575 | 2.26:1 ⚠️ | 3.8:1 ⚠️ | 禁用文本 |
| `text-inverse` | White<br>#FFFFFF | Grey-900<br>#212121 | - | - | 深色背景上的文字 |
| `text-placeholder` | Grey-400<br>#BDBDBD | Grey-500<br>#9E9E9E | 2.26:1 ⚠️ | 5.6:1 ✅ AA | 输入框占位符 |

**注意：**
- ⚠️ 标记的 Token 对比度不足 4.5:1，仅用于装饰性或禁用状态，不应传达关键信息
- Material Design 使用 "Grey" 而非 "Gray"

---

### 2. 链接文本色（Link）

| Token | 浅色模式 | 暗色模式 | 对比度（浅） | 对比度（暗） | 用途 |
|-------|---------|---------|------------|------------|------|
| `text-link` | Blue-700<br>#1976D2 | Blue-300<br>#64B5F6 | 4.6:1 ✅ AA | 7.0:1 ✅ AAA | 默认链接 |
| `text-link-hover` | Blue-800<br>#1565C0 | Blue-200<br>#90CAF9 | 6.03:1 ✅ AA | 10.2:1 ✅ AAA | 链接悬停 |
| `text-link-visited` | Purple-700<br>#7B1FA2 | Purple-300<br>#BA68C8 | 5.45:1 ✅ AA | 6.1:1 ✅ AA | 已访问链接 |
| `text-link-active` | Blue-900<br>#0D47A1 | Blue-100<br>#BBDEFB | 8.59:1 ✅ AAA | 14.4:1 ✅ AAA | 链接激活（按下） |

**注意：** Blue-600 (#1E88E5) 对比度仅 3.68:1，不符合 WCAG AA 标准，必须使用 Blue-700。

---

### 3. 功能反馈文本色（Functional）

| Token | 浅色模式 | 暗色模式 | 对比度（浅） | 对比度（暗） | 用途 |
|-------|---------|---------|------------|------------|------|
| `text-success` | Green-700<br>#388E3C | Green-300<br>#81C784 | 5.44:1 ✅ AA | 7.0:1 ✅ AAA | 成功提示 |
| `text-warning` | Grey-900<br>#212121 | Amber-100<br>#FFECB3 | 16.1:1 ✅ AAA | 15.8:1 ✅ AAA | 警告文本（需搭配 Amber-100 背景） |
| `text-error` | Red-700<br>#D32F2F | Red-300<br>#E57373 | 4.98:1 ✅ AA | 6.2:1 ✅ AA | 错误提示 |
| `text-info` | Blue-700<br>#1976D2 | Blue-300<br>#64B5F6 | 4.6:1 ✅ AA | 7.0:1 ✅ AAA | 信息提示 |

**关键：**
- Green-600 对比度仅 3.3:1 ❌，必须使用 Green-700
- Red-600 对比度仅 4.03:1 ⚠️，必须使用 Red-700
- Amber 所有色阶都不符合 AA 标准，警告文本使用 **反转方案**：Grey-900 文本 + Amber-100 背景

---

### 4. 品牌/强调文本色（Brand / Emphasis）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `text-brand` | Blue-700<br>#1976D2 | Blue-300<br>#64B5F6 | Logo、品牌口号 |
| `text-emphasis` | Blue-800<br>#1565C0 | Blue-200<br>#90CAF9 | 需要突出的文本 |
| `text-highlight` | Deep Orange-700<br>#E64A19 | Deep Orange-300<br>#FF8A65 | 高亮标记（如搜索结果） |

---

### 5. 特殊场景文本色（Special）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `text-code` | Pink-700<br>#C2185B | Pink-300<br>#F06292 | 行内代码 |
| `text-code-keyword` | Purple-700<br>#7B1FA2 | Purple-300<br>#BA68C8 | 代码关键字 |
| `text-code-string` | Green-700<br>#388E3C | Green-300<br>#81C784 | 代码字符串 |
| `text-code-comment` | Grey-500<br>#9E9E9E | Grey-400<br>#BDBDBD | 代码注释 |
| `text-code-number` | Deep Orange-700<br>#E64A19 | Deep Orange-300<br>#FF8A65 | 代码数字 |

---

## CSS Variables 定义

```css
/* ========== 浅色模式（默认）- Material Design ========== */
:root {
  /* 层级文本色 */
  --text-primary: #212121;       /* Grey-900, 16.1:1 AAA */
  --text-secondary: #757575;     /* Grey-600, 4.68:1 AA */
  --text-tertiary: #9E9E9E;      /* Grey-500, 3.15:1 */
  --text-quaternary: #BDBDBD;    /* Grey-400, 2.26:1 */
  --text-disabled: #BDBDBD;      /* Grey-400, 2.26:1 */
  --text-inverse: #FFFFFF;
  --text-placeholder: #BDBDBD;   /* Grey-400, 2.26:1 */

  /* 链接文本色 */
  --text-link: #1976D2;          /* Blue-700, 4.6:1 AA */
  --text-link-hover: #1565C0;    /* Blue-800, 6.03:1 AA */
  --text-link-visited: #7B1FA2;  /* Purple-700, 5.45:1 AA */
  --text-link-active: #0D47A1;   /* Blue-900, 8.59:1 AAA */

  /* 功能反馈文本色 */
  --text-success: #388E3C;       /* Green-700, 5.44:1 AA */
  --text-warning: #212121;       /* Grey-900 (配合 Amber-100 背景), 16.1:1 AAA */
  --text-error: #D32F2F;         /* Red-700, 4.98:1 AA */
  --text-info: #1976D2;          /* Blue-700, 4.6:1 AA */

  /* 品牌/强调文本色 */
  --text-brand: #1976D2;         /* Blue-700 */
  --text-emphasis: #1565C0;      /* Blue-800 */
  --text-highlight: #E64A19;     /* Deep Orange-700 */

  /* 特殊场景文本色 */
  --text-code: #C2185B;          /* Pink-700 */
  --text-code-keyword: #7B1FA2;  /* Purple-700 */
  --text-code-string: #388E3C;   /* Green-700 */
  --text-code-comment: #9E9E9E;  /* Grey-500 */
  --text-code-number: #E64A19;   /* Deep Orange-700 */
}

/* ========== 暗色模式 ========== */
[data-theme="dark"] {
  /* 层级文本色 */
  --text-primary: #FAFAFA;       /* Grey-50 */
  --text-secondary: #E0E0E0;     /* Grey-300 */
  --text-tertiary: #BDBDBD;      /* Grey-400 */
  --text-quaternary: #9E9E9E;    /* Grey-500 */
  --text-disabled: #757575;      /* Grey-600 */
  --text-inverse: #212121;       /* Grey-900 */
  --text-placeholder: #9E9E9E;   /* Grey-500 */

  /* 链接文本色 */
  --text-link: #64B5F6;          /* Blue-300 */
  --text-link-hover: #90CAF9;    /* Blue-200 */
  --text-link-visited: #BA68C8;  /* Purple-300 */
  --text-link-active: #BBDEFB;   /* Blue-100 */

  /* 功能反馈文本色 */
  --text-success: #81C784;       /* Green-300 */
  --text-warning: #FFECB3;       /* Amber-100 (配合 Amber-900 背景) */
  --text-error: #E57373;         /* Red-300 */
  --text-info: #64B5F6;          /* Blue-300 */

  /* 品牌/强调文本色 */
  --text-brand: #64B5F6;         /* Blue-300 */
  --text-emphasis: #90CAF9;      /* Blue-200 */
  --text-highlight: #FF8A65;     /* Deep Orange-300 */

  /* 特殊场景文本色 */
  --text-code: #F06292;          /* Pink-300 */
  --text-code-keyword: #BA68C8;  /* Purple-300 */
  --text-code-string: #81C784;   /* Green-300 */
  --text-code-comment: #BDBDBD;  /* Grey-400 */
  --text-code-number: #FF8A65;   /* Deep Orange-300 */
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
      "value": "#212121",
      "$extensions": {
        "mode": {
          "dark": "#FAFAFA"
        }
      },
      "type": "color",
      "description": "主要文本，Material Design Grey-900，对比度 16.1:1 (AAA)"
    },
    "link": {
      "value": "#1976D2",
      "$extensions": {
        "mode": {
          "dark": "#64B5F6"
        }
      },
      "type": "color",
      "description": "链接文本，Material Design Blue-700，对比度 4.6:1 (AA)"
    },
    "error": {
      "value": "#D32F2F",
      "$extensions": {
        "mode": {
          "dark": "#E57373"
        }
      },
      "type": "color",
      "description": "错误文本，Material Design Red-700，对比度 4.98:1 (AA)"
    },
    "success": {
      "value": "#388E3C",
      "$extensions": {
        "mode": {
          "dark": "#81C784"
        }
      },
      "type": "color",
      "description": "成功文本，Material Design Green-700，对比度 5.44:1 (AA)"
    }
  }
}
```

---

**相关文档：**
- [语义化色彩总览](../semantic-colors.md)
- [背景色 Token](./background-colors.md)
- [功能色 Token](./functional-colors.md)
- [色板系统](../color-palette.md) - Material Design 17 色标准色板

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
