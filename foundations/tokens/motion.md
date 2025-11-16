# Motion 动效系统 Token

> 统一的动画和过渡系统，提升用户体验的流畅性和愉悦感。
> **基于物理曲线和标准时长**

---

## 目录

1. [动画时长](#动画时长duration)
2. [缓动函数](#缓动函数easing)
3. [语义化过渡](#语义化过渡semantic-transitions)
4. [动画预设](#动画预设animation-presets)
5. [使用示例](#使用示例)

---

## 动画时长（Duration）

### Token 定义

```
duration-instant:  0ms       # 无动画（即时响应）
duration-fast:     100ms     # 快速（状态切换、图标旋转）
duration-base:     200ms     # 基础（按钮悬停、颜色变化，推荐）
duration-slow:     300ms     # 慢速（抽屉展开、下拉菜单）
duration-slower:   500ms     # 更慢（页面转场、大型动画）
```

### 使用建议

| 时长 | 适用场景 | 示例 |
|-----|---------|------|
| **0ms** | 禁用动画、打印模式 | `prefers-reduced-motion` |
| **100ms** | 微交互、即时反馈 | 复选框勾选、图标旋转 |
| **200ms** | 标准交互（最常用） | 按钮悬停、下拉展开 |
| **300ms** | 复杂过渡 | 抽屉滑入、模态框淡入 |
| **500ms** | 页面级动画 | 路由切换、大型面板 |

**原则：** 越小的元素，动画时长越短

---

## 缓动函数（Easing）

### 标准缓动曲线

```
ease-linear:      cubic-bezier(0, 0, 1, 1)           # 匀速（罕用）
ease-in:          cubic-bezier(0.4, 0, 1, 1)         # 加速（元素离开）
ease-out:         cubic-bezier(0, 0, 0.2, 1)         # 减速（元素进入，推荐）
ease-in-out:      cubic-bezier(0.4, 0, 0.2, 1)       # 先加速后减速（中性）
ease-bounce:      cubic-bezier(0.68, -0.55, 0.265, 1.55)  # 弹性（特殊效果）
```

### 使用场景

| 缓动函数 | 用途 | 物理隐喻 |
|---------|------|---------|
| `ease-in` | 元素离开屏幕 | 物体加速离开视野 |
| `ease-out` | 元素进入屏幕（推荐） | 物体从远处减速停靠 |
| `ease-in-out` | 元素位置变化 | 物体从一处移动到另一处 |
| `ease-linear` | 旋转、进度条 | 机械运动 |
| `ease-bounce` | 成功反馈、特殊效果 | 弹性材质 |

**Material Design 推荐：** 大部分场景使用 `ease-out`（`cubic-bezier(0, 0, 0.2, 1)`）

---

## 语义化过渡（Semantic Transitions）

### 预定义组合

```
transition-base:     all {duration-base} {ease-out}
transition-colors:   color, background-color, border-color {duration-base} {ease-out}
transition-opacity:  opacity {duration-base} {ease-in-out}
transition-transform: transform {duration-base} {ease-out}
transition-shadow:   box-shadow {duration-base} {ease-out}
```

### 展开定义

```css
--transition-base:      all 200ms cubic-bezier(0, 0, 0.2, 1);
--transition-colors:    color 200ms cubic-bezier(0, 0, 0.2, 1),
                        background-color 200ms cubic-bezier(0, 0, 0.2, 1),
                        border-color 200ms cubic-bezier(0, 0, 0.2, 1);
--transition-opacity:   opacity 200ms cubic-bezier(0.4, 0, 0.2, 1);
--transition-transform: transform 200ms cubic-bezier(0, 0, 0.2, 1);
--transition-shadow:    box-shadow 200ms cubic-bezier(0, 0, 0.2, 1);
```

---

## 动画预设（Animation Presets）

### 淡入淡出（Fade）

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes fadeOut {
  from { opacity: 1; }
  to { opacity: 0; }
}

.fade-in {
  animation: fadeIn var(--duration-base) var(--ease-out);
}
```

### 滑入滑出（Slide）

```css
@keyframes slideInRight {
  from { transform: translateX(100%); }
  to { transform: translateX(0); }
}

@keyframes slideOutLeft {
  from { transform: translateX(0); }
  to { transform: translateX(-100%); }
}

.slide-in-right {
  animation: slideInRight var(--duration-slow) var(--ease-out);
}
```

### 缩放（Scale）

```css
@keyframes scaleIn {
  from { transform: scale(0.9); opacity: 0; }
  to { transform: scale(1); opacity: 1; }
}

.scale-in {
  animation: scaleIn var(--duration-base) var(--ease-out);
}
```

### 脉冲（Pulse）

```css
@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.5; }
}

.pulse {
  animation: pulse var(--duration-slower) var(--ease-in-out) infinite;
}
```

---

## CSS Variables 定义

```css
:root {
  /* 动画时长 */
  --duration-instant: 0ms;
  --duration-fast: 100ms;
  --duration-base: 200ms;
  --duration-slow: 300ms;
  --duration-slower: 500ms;

  /* 缓动函数 */
  --ease-linear: cubic-bezier(0, 0, 1, 1);
  --ease-in: cubic-bezier(0.4, 0, 1, 1);
  --ease-out: cubic-bezier(0, 0, 0.2, 1);
  --ease-in-out: cubic-bezier(0.4, 0, 0.2, 1);
  --ease-bounce: cubic-bezier(0.68, -0.55, 0.265, 1.55);

  /* 语义化过渡 */
  --transition-base: all 200ms cubic-bezier(0, 0, 0.2, 1);
  --transition-colors: color 200ms cubic-bezier(0, 0, 0.2, 1),
                       background-color 200ms cubic-bezier(0, 0, 0.2, 1),
                       border-color 200ms cubic-bezier(0, 0, 0.2, 1);
  --transition-opacity: opacity 200ms cubic-bezier(0.4, 0, 0.2, 1);
  --transition-transform: transform 200ms cubic-bezier(0, 0, 0.2, 1);
  --transition-shadow: box-shadow 200ms cubic-bezier(0, 0, 0.2, 1);
}

/* 尊重用户偏好：禁用动画 */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## 使用示例

### 按钮悬停

```css
.button {
  transition: var(--transition-colors);
}

.button:hover {
  background-color: var(--interactive-primary-hover);
}
```

### 模态框动画

```css
.modal {
  animation: scaleIn var(--duration-slow) var(--ease-out);
}

.modal-backdrop {
  animation: fadeIn var(--duration-base) var(--ease-out);
}
```

### 抽屉滑入

```css
.drawer {
  transition: transform var(--duration-slow) var(--ease-out);
}

.drawer.open {
  transform: translateX(0);
}

.drawer.closed {
  transform: translateX(100%);
}
```

### 加载动画

```css
.spinner {
  animation: spin var(--duration-slower) var(--ease-linear) infinite;
}

@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}
```

---

## 无障碍支持

### 尊重用户偏好

```css
/* 用户设置了减少动效 */
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

### JavaScript 检测

```javascript
const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)');

if (prefersReducedMotion.matches) {
  // 禁用复杂动画
  document.body.classList.add('no-animations');
}
```

---

**相关文档：**
- [Design Token 规范](./README.md) - 总览
- [Opacity Token](./README.md#11-opacity透明度) - 透明度系统

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
**维护者：** 设计系统团队
