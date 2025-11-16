# 暗色模式 - 完整色彩映射

> 基于科学的视觉感知原理和可访问性标准设计的暗色模式系统。
> 暗色模式不是简单的"颜色反转"，而是一套独立的、经过优化的色彩体系。

---

## 目录

1. [设计原理](#设计原理)
2. [完整 Token 映射表](#完整-token-映射表)
3. [色彩调整规则](#色彩调整规则)
4. [对比度验证](#对比度验证)
5. [实现方式](#实现方式)

---

## 设计原理

### 为什么暗色模式不是简单反转？

**❌ 错误做法：**
```
浅色模式：白色背景 + 黑色文字
暗色模式：黑色背景 + 白色文字  ← 太刺眼！
```

**✅ 正确做法：**
```
浅色模式：白色背景 (#FFFFFF) + 深灰文字 (#111827)
暗色模式：深灰背景 (#111827) + 浅灰文字 (#F9FAFB)
```

### 暗色模式的核心原则

#### 1. 降低对比度（60-80%）

**原因：** 在暗环境中，极高对比度（纯黑+纯白）会导致：
- 视觉疲劳（光晕效应）
- 文本边缘模糊
- 阅读困难

**解决方案：**
```
浅色模式对比度：16.2:1 (#111827 on #FFFFFF)
暗色模式对比度：14.5:1 (#F9FAFB on #111827)  ← 略低但更舒适
```

#### 2. 提升表面亮度（避免纯黑）

**问题：** 纯黑背景 (#000000) 会导致：
- 屏幕发光效应（Blooming）
- 缺乏空间层次
- OLED 烧屏风险

**解决方案：**
```
主背景：#111827 (Gray-900) 而非 #000000
次级背景：#1F2937 (Gray-800) 提升表面
```

#### 3. 降低饱和度（彩色）

**原因：** 暗背景上的高饱和度颜色会：
- 过于刺眼
- 视觉震动（Vibration）
- 失去品牌感

**解决方案：**
```
浅色模式：Blue-600 (#2563EB, S=91%)
暗色模式：Blue-400 (#60A5FA, S=90%) ← 亮度提高，饱和度略降
```

---

## 完整 Token 映射表

### 文本色（Text Colors）

| Token | 浅色模式 | 暗色模式 | 对比度（暗） | 说明 |
|-------|---------|---------|------------|------|
| `color-text-primary` | Gray-900<br>#111827 | Gray-50<br>#F9FAFB | 14.5:1 ✅ AAA | 主文本 |
| `color-text-secondary` | Gray-600<br>#4B5563 | Gray-300<br>#D1D5DB | 9.8:1 ✅ AAA | 次要文本 |
| `color-text-tertiary` | Gray-500<br>#6B7280 | Gray-400<br>#9CA3AF | 6.2:1 ✅ AAA | 辅助文本 |
| `color-text-disabled` | Gray-400<br>#9CA3AF | Gray-600<br>#4B5563 | 3.1:1 ⚠️ | 禁用文本 |
| `color-text-inverse` | White<br>#FFFFFF | Gray-900<br>#111827 | - | 反色文本 |
| `color-text-link` | Blue-600<br>#2563EB | Blue-400<br>#60A5FA | 6.8:1 ✅ AAA | 链接文本 |
| `color-text-link-hover` | Blue-700<br>#1D4ED8 | Blue-300<br>#93C5FD | 8.9:1 ✅ AAA | 链接悬停 |
| `color-text-error` | Red-600<br>#DC2626 | Red-400<br>#F87171 | 5.2:1 ✅ AA | 错误文本 |
| `color-text-success` | Green-600<br>#16A34A | Green-400<br>#4ADE80 | 5.8:1 ✅ AA | 成功文本 |
| `color-text-warning` | Yellow-700<br>#A16207 | Yellow-400<br>#FACC15 | 4.9:1 ✅ AA | 警告文本 |

**规律：**
- 文本色从深向浅移动（900 → 50, 600 → 300）
- 确保暗色模式对比度 ≥ 4.5:1（AA级）

---

### 背景色（Background Colors）

| Token | 浅色模式 | 暗色模式 | 说明 |
|-------|---------|---------|------|
| `color-bg-primary` | White<br>#FFFFFF | Gray-900<br>#111827 | 主背景 |
| `color-bg-secondary` | Gray-50<br>#F9FAFB | Gray-800<br>#1F2937 | 次级背景（卡片） |
| `color-bg-tertiary` | Gray-100<br>#F3F4F6 | Gray-700<br>#374151 | 三级背景（悬浮） |
| `color-bg-overlay` | rgba(0,0,0,0.5) | rgba(0,0,0,0.7) | 遮罩层（加深） |
| `color-bg-disabled` | Gray-100<br>#F3F4F6 | Gray-800<br>#1F2937 | 禁用背景 |
| `color-bg-error` | Red-50<br>#FEF2F2 | Red-950<br>#450A0A | 错误背景 |
| `color-bg-success` | Green-50<br>#F0FDF4 | Green-950<br>#052E16 | 成功背景 |
| `color-bg-warning` | Yellow-50<br>#FEFCE8 | Yellow-950<br>#422006 | 警告背景 |
| `color-bg-info` | Cyan-50<br>#ECFEFF | Cyan-950<br>#083344 | 信息背景 |

**规律：**
- 主背景：White → Gray-900（深灰，非纯黑）
- 次级背景：向浅色移动（800, 700）形成层次
- 彩色背景：使用 950 超深色（避免刺眼）

---

### 边框色（Border Colors）

| Token | 浅色模式 | 暗色模式 | 说明 |
|-------|---------|---------|------|
| `color-border-primary` | Gray-300<br>#D1D5DB | Gray-700<br>#374151 | 主边框 |
| `color-border-secondary` | Gray-200<br>#E5E7EB | Gray-800<br>#1F2937 | 次级边框 |
| `color-border-focus` | Blue-500<br>#3B82F6 | Blue-500<br>#3B82F6 | 焦点边框（不变） |
| `color-border-error` | Red-500<br>#EF4444 | Red-500<br>#EF4444 | 错误边框 |
| `color-border-success` | Green-500<br>#22C55E | Green-500<br>#22C55E | 成功边框 |

**规律：**
- 中性边框：300/200 → 700/800（反转）
- 功能色边框：保持 500 不变（视觉连续性）

---

### 交互色（Interactive Colors）

| Token | 浅色模式 | 暗色模式 | 说明 |
|-------|---------|---------|------|
| `color-interactive-primary` | Blue-600<br>#2563EB | Blue-500<br>#3B82F6 | 主交互元素 |
| `color-interactive-primary-hover` | Blue-700<br>#1D4ED8 | Blue-400<br>#60A5FA | 悬停 |
| `color-interactive-primary-active` | Blue-800<br>#1E40AF | Blue-300<br>#93C5FD | 按下 |
| `color-interactive-primary-disabled` | Gray-300<br>#D1D5DB | Gray-700<br>#374151 | 禁用 |
| `color-interactive-secondary` | Gray-600<br>#4B5563 | Gray-400<br>#9CA3AF | 次要交互 |
| `color-interactive-secondary-hover` | Gray-700<br>#374151 | Gray-300<br>#D1D5DB | 悬停 |
| `color-interactive-secondary-active` | Gray-800<br>#1F2937 | Gray-200<br>#E5E7EB | 按下 |

**规律：**
- 主交互：600 → 500（略提亮）
- 悬停/按下：向浅色方向移动
- 确保暗色背景上可见

---

### 阴影（Shadows）

**问题：** 传统阴影（黑色）在暗色模式下会：
- 消失（黑背景 + 黑阴影 = 不可见）
- 失去深度感

**解决方案：提升表面亮度（Elevation）**

| Token | 浅色模式 | 暗色模式 |
|-------|---------|---------|
| `shadow-xs` | 0 1px 2px rgba(0,0,0,0.05) | 0 1px 3px rgba(0,0,0,0.3) |
| `shadow-sm` | 0 2px 4px rgba(0,0,0,0.06) | 0 2px 8px rgba(0,0,0,0.4) |
| `shadow-base` | 0 4px 8px rgba(0,0,0,0.08) | 0 4px 12px rgba(0,0,0,0.5) |
| `shadow-md` | 0 8px 16px rgba(0,0,0,0.12) | 0 8px 20px rgba(0,0,0,0.6) |
| `shadow-lg` | 0 16px 32px rgba(0,0,0,0.16) | 0 16px 32px rgba(0,0,0,0.7) |

**额外技巧：组合表面提升**
```css
/* 暗色模式：阴影 + 背景提亮 */
.card-dark {
  background: #1F2937; /* 比主背景 #111827 亮 */
  box-shadow: 0 4px 12px rgba(0,0,0,0.5);
}
```

---

### 透明度（Opacity）

| Token | 浅色模式 | 暗色模式 | 说明 |
|-------|---------|---------|------|
| `opacity-backdrop` | 0.5 | 0.7 | 遮罩层（暗色模式加深） |
| `opacity-hover` | 0.8 | 0.9 | 悬停（暗色模式减淡） |
| `opacity-disabled` | 0.5 | 0.5 | 禁用（不变） |

---

## 色彩调整规则

### 规则 1: 亮度反转 + 保持对比度

**公式：**
```
浅色模式文本：  L = 10-30% (深色)
暗色模式文本：  L = 90-97% (浅色)

浅色模式背景：  L = 97-100% (浅色)
暗色模式背景：  L = 10-20% (深色)
```

**对比度要求：**
- 浅色模式：≥ 4.5:1
- 暗色模式：≥ 4.5:1（同样严格）

---

### 规则 2: 饱和度调整

**彩色元素（品牌色、功能色）：**

| 浅色模式 | 暗色模式 | 调整 |
|---------|---------|------|
| 600 级（L=52%, S=92%） | 400 级（L=68%, S=90%） | 亮度 ↑16%, 饱和度 ↓2% |
| 700 级（L=45%, S=90%） | 300 级（L=78%, S=85%） | 亮度 ↑33%, 饱和度 ↓5% |

**原因：** 暗背景会放大饱和度感知，需要降低 2-5% 饱和度。

---

### 规则 3: 层级反转

**浅色模式（由浅到深）：**
```
主背景 (#FFFFFF) → 次级 (#F9FAFB) → 三级 (#F3F4F6)
```

**暗色模式（由深到浅）：**
```
主背景 (#111827) → 次级 (#1F2937) → 三级 (#374151)
```

**视觉效果：** 浅色"凹陷"，暗色"凸起"

---

## 对比度验证

### 暗色模式对比度表

**文本 on 主背景（#111827）：**

| 文本色 | 颜色值 | 对比度 | 等级 | 用途 |
|-------|--------|-------|------|------|
| Gray-50 | #F9FAFB | 14.5:1 | AAA ✅ | 主文本 |
| Gray-100 | #F3F4F6 | 13.8:1 | AAA ✅ | 主文本 |
| Gray-200 | #E5E7EB | 12.1:1 | AAA ✅ | 强调文本 |
| Gray-300 | #D1D5DB | 9.8:1 | AAA ✅ | 次要文本 |
| Gray-400 | #9CA3AF | 6.2:1 | AAA ✅ | 辅助文本 |
| Gray-500 | #6B7280 | 4.1:1 | ⚠️ 略低 | ❌ 不推荐 |
| Blue-400 | #60A5FA | 6.8:1 | AAA ✅ | 链接文本 |
| Red-400 | #F87171 | 5.2:1 | AA ✅ | 错误文本 |
| Green-400 | #4ADE80 | 5.8:1 | AA ✅ | 成功文本 |

**结论：**
- ✅ 使用 50-400 色阶作为文本色
- ❌ 避免使用 500 及以下（对比度不足）

---

### 彩色背景 on 主背景（#111827）

| 背景色 | 颜色值 | 边缘对比度 | 是否可辨识 |
|-------|--------|-----------|----------|
| Blue-950 | #172554 | 1.3:1 | ✅ 可见 |
| Red-950 | #450A0A | 1.5:1 | ✅ 可见 |
| Green-950 | #052E16 | 1.2:1 | ⚠️ 较弱 |

**建议：** 彩色背景使用 950 色阶 + 边框辅助

---

## 实现方式

### 方式 1: CSS Variables（推荐）

```css
/* 定义浅色模式（默认） */
:root {
  --color-text-primary: #111827;
  --color-text-secondary: #4B5563;
  --color-bg-primary: #FFFFFF;
  --color-bg-secondary: #F9FAFB;
  --color-border-primary: #D1D5DB;
  --color-interactive-primary: #2563EB;
  --shadow-base: 0 4px 8px rgba(0, 0, 0, 0.08);
}

/* 定义暗色模式 */
[data-theme="dark"] {
  --color-text-primary: #F9FAFB;
  --color-text-secondary: #D1D5DB;
  --color-bg-primary: #111827;
  --color-bg-secondary: #1F2937;
  --color-border-primary: #374151;
  --color-interactive-primary: #3B82F6;
  --shadow-base: 0 4px 12px rgba(0, 0, 0, 0.5);
}

/* 使用 */
.card {
  background-color: var(--color-bg-primary);
  color: var(--color-text-primary);
  border: 1px solid var(--color-border-primary);
  box-shadow: var(--shadow-base);
}
```

---

### 方式 2: Tailwind CSS Dark Mode

**配置 `tailwind.config.js`：**
```javascript
module.exports = {
  darkMode: 'class', // 或 'media'
  theme: {
    extend: {
      colors: {
        // 不需要单独配置，Tailwind 内置暗色变体
      },
    },
  },
};
```

**使用：**
```html
<!-- 自动切换 -->
<div class="bg-white dark:bg-gray-900 text-gray-900 dark:text-gray-50">
  <h1 class="text-blue-600 dark:text-blue-400">标题</h1>
  <p class="text-gray-600 dark:text-gray-300">正文内容</p>
</div>
```

---

### 方式 3: JavaScript 主题切换

```javascript
// 主题切换逻辑
function toggleTheme() {
  const root = document.documentElement;
  const currentTheme = root.getAttribute('data-theme');
  const newTheme = currentTheme === 'dark' ? 'light' : 'dark';

  root.setAttribute('data-theme', newTheme);
  localStorage.setItem('theme', newTheme);
}

// 初始化主题（根据用户偏好）
function initTheme() {
  const savedTheme = localStorage.getItem('theme');
  const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
  const theme = savedTheme || (prefersDark ? 'dark' : 'light');

  document.documentElement.setAttribute('data-theme', theme);
}

// 页面加载时初始化
initTheme();
```

---

### 方式 4: 响应系统偏好

```css
/* 自动响应系统深色模式 */
@media (prefers-color-scheme: dark) {
  :root {
    --color-text-primary: #F9FAFB;
    --color-bg-primary: #111827;
    /* ... 其他暗色变量 */
  }
}
```

---

## 特殊场景处理

### 1. 图片和图标

**问题：** 深色背景上，浅色图片会过于刺眼

**解决方案：**
```css
/* 暗色模式：降低图片亮度 */
[data-theme="dark"] img {
  opacity: 0.9;
  filter: brightness(0.9);
}

/* 图标：使用语义色而非固定颜色 */
.icon-primary {
  color: var(--color-interactive-primary); /* 自动适配 */
}
```

---

### 2. 代码块

**浅色模式：**
```css
.code-block-light {
  background: #F3F4F6; /* Gray-100 */
  color: #1F2937;      /* Gray-800 */
  border: 1px solid #E5E7EB;
}
```

**暗色模式：**
```css
.code-block-dark {
  background: #1F2937; /* Gray-800 */
  color: #E5E7EB;      /* Gray-200 */
  border: 1px solid #374151;
}
```

---

### 3. 表单输入框

**问题：** 暗色模式下，白色输入框很突兀

**解决方案：**
```css
/* 浅色模式 */
.input-light {
  background: #FFFFFF;
  border: 1px solid #D1D5DB;
  color: #111827;
}

/* 暗色模式 */
.input-dark {
  background: #1F2937; /* 比主背景亮 */
  border: 1px solid #374151;
  color: #F9FAFB;
}
```

---

### 4. 表格斑马纹

**浅色模式：**
```css
.table-row:nth-child(even) {
  background: #F9FAFB; /* Gray-50 */
}
```

**暗色模式：**
```css
[data-theme="dark"] .table-row:nth-child(even) {
  background: #1F2937; /* Gray-800 */
}
```

---

## 完整 JSON Token 定义

```json
{
  "color": {
    "text": {
      "primary": {
        "value": "#111827",
        "$extensions": {
          "mode": {
            "dark": "#F9FAFB"
          }
        }
      },
      "secondary": {
        "value": "#4B5563",
        "$extensions": {
          "mode": {
            "dark": "#D1D5DB"
          }
        }
      }
    },
    "bg": {
      "primary": {
        "value": "#FFFFFF",
        "$extensions": {
          "mode": {
            "dark": "#111827"
          }
        }
      },
      "secondary": {
        "value": "#F9FAFB",
        "$extensions": {
          "mode": {
            "dark": "#1F2937"
          }
        }
      }
    }
  }
}
```

---

## 设计检查清单

**实施暗色模式前，确保：**

- [ ] 所有文本色对比度 ≥ 4.5:1（AA 级）
- [ ] 避免使用纯黑 (#000000) 作为主背景
- [ ] 彩色元素饱和度降低 2-5%
- [ ] 阴影加深（alpha 提高 2-3 倍）
- [ ] 表面层级明确（主背景 < 次级 < 三级）
- [ ] 交互元素在暗色背景上可见
- [ ] 测试所有功能色（成功/警告/错误）
- [ ] 图片和图标不会过亮
- [ ] 提供主题切换按钮
- [ ] 记住用户偏好（localStorage）

---

## 参考资源

### 设计指南
- [Material Design - Dark Theme](https://m3.material.io/styles/color/dark-theme/overview)
- [Apple Human Interface Guidelines - Dark Mode](https://developer.apple.com/design/human-interface-guidelines/dark-mode)
- [Tailwind CSS - Dark Mode](https://tailwindcss.com/docs/dark-mode)

### 工具
- [Dark Mode Converter](https://colorffy.com/dark-theme-generator)
- [Contrast Checker for Dark Mode](https://webaim.org/resources/contrastchecker/)

---

**文档版本：** v1.0
**最后更新：** 2025-11-16
**相关文档：** [Design Token 规范](./README.md) | [扩展色板](./color-palette.md)
