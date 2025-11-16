# 装饰色 Token 清单

> 用于阴影、渐变、骨架屏、水印等视觉装饰效果的颜色定义。

---

## 完整 Token 清单

### 1. 阴影色系（Shadow）

**设计原则：**
- 使用纯黑色 `#000000` 作为基础，通过透明度控制深浅
- 暗色模式下阴影更深，增强层次感
- 阴影透明度遵循数学公式：`alpha = 0.04 + depth/100`

| Token | 浅色模式 | 暗色模式 | Y轴偏移 | 模糊半径 | 用途 |
|-------|---------|---------|---------|---------|------|
| `shadow-xs` | rgba(0,0,0,0.04) | rgba(0,0,0,0.15) | 1px | 2px | 极小阴影（按钮微凸） |
| `shadow-sm` | rgba(0,0,0,0.05) | rgba(0,0,0,0.2) | 2px | 4px | 小阴影（卡片悬停） |
| `shadow-base` | rgba(0,0,0,0.1) | rgba(0,0,0,0.3) | 4px | 8px | 基础阴影（卡片、下拉） |
| `shadow-md` | rgba(0,0,0,0.15) | rgba(0,0,0,0.4) | 8px | 16px | 中等阴影（模态框） |
| `shadow-lg` | rgba(0,0,0,0.2) | rgba(0,0,0,0.5) | 16px | 32px | 大阴影（抽屉） |
| `shadow-xl` | rgba(0,0,0,0.25) | rgba(0,0,0,0.6) | 24px | 48px | 超大阴影（全屏浮层） |
| `shadow-inner` | rgba(0,0,0,0.06) | rgba(0,0,0,0.2) | inset | - | 内阴影（按下状态） |
| `shadow-outline` | rgba(7,112,250,0.3) | rgba(7,112,250,0.4) | 0px | 0 3px | 聚焦轮廓（蓝色） |

**配套 Box Shadow 值：**

```css
:root {
  /* 基础阴影 */
  --shadow-xs: 0 1px 2px 0 rgba(0, 0, 0, 0.04);
  --shadow-sm: 0 2px 4px 0 rgba(0, 0, 0, 0.05);
  --shadow-base: 0 4px 8px 0 rgba(0, 0, 0, 0.1);
  --shadow-md: 0 8px 16px 0 rgba(0, 0, 0, 0.15);
  --shadow-lg: 0 16px 32px 0 rgba(0, 0, 0, 0.2);
  --shadow-xl: 0 24px 48px 0 rgba(0, 0, 0, 0.25);

  /* 特殊阴影 */
  --shadow-inner: inset 0 2px 4px 0 rgba(0, 0, 0, 0.06);
  --shadow-outline: 0 0 0 3px rgba(7, 112, 250, 0.3);
}

[data-theme="dark"] {
  --shadow-xs: 0 1px 2px 0 rgba(0, 0, 0, 0.15);
  --shadow-sm: 0 2px 4px 0 rgba(0, 0, 0, 0.2);
  --shadow-base: 0 4px 8px 0 rgba(0, 0, 0, 0.3);
  --shadow-md: 0 8px 16px 0 rgba(0, 0, 0, 0.4);
  --shadow-lg: 0 16px 32px 0 rgba(0, 0, 0, 0.5);
  --shadow-xl: 0 24px 48px 0 rgba(0, 0, 0, 0.6);
  --shadow-inner: inset 0 2px 4px 0 rgba(0, 0, 0, 0.2);
  --shadow-outline: 0 0 0 3px rgba(7, 112, 250, 0.4);
}
```

---

### 2. 渐变色系（Gradient）

#### 主渐变

| Token | 浅色模式 | 暗色模式 | 角度 | 用途 |
|-------|---------|---------|-----|------|
| `gradient-primary` | Blue-500 → Blue-600<br>#3B8CF7 → #0770FA | Blue-400 → Blue-500<br>#68A4F3 → #3B8CF7 | 135deg | 主按钮渐变 |
| `gradient-secondary` | Gray-100 → Gray-200<br>#F5F5F5 → #E5E5E5 | Gray-800 → Gray-900<br>#262626 → #171717 | 135deg | 次要背景渐变 |
| `gradient-success` | Green-500 → Green-600<br>#38FA86 → #008937 | Green-400 → Green-500<br>#66F59F → #38FA86 | 135deg | 成功渐变 |
| `gradient-danger` | Red-500 → Red-600<br>#F83A3A → #ED0505 | Red-400 → Red-500<br>#F56666 → #F83A3A | 135deg | 危险操作渐变 |

#### 特殊渐变

| Token | 定义 | 用途 |
|-------|------|------|
| `gradient-shimmer` | 90deg, transparent 0%, rgba(255,255,255,0.6) 50%, transparent 100% | 骨架屏闪光动画 |
| `gradient-glass` | 180deg, rgba(255,255,255,0.8) 0%, rgba(255,255,255,0.4) 100% | 玻璃态背景（浅色） |
| `gradient-glass-dark` | 180deg, rgba(0,0,0,0.6) 0%, rgba(0,0,0,0.3) 100% | 玻璃态背景（暗色） |
| `gradient-overlay` | 180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,0.5) 100% | 图片遮罩渐变 |

**CSS 定义：**

```css
:root {
  /* 主渐变 */
  --gradient-primary: linear-gradient(135deg, #3B8CF7 0%, #0770FA 100%);
  --gradient-secondary: linear-gradient(135deg, #F5F5F5 0%, #E5E5E5 100%);
  --gradient-success: linear-gradient(135deg, #38FA86 0%, #008937 100%);
  --gradient-danger: linear-gradient(135deg, #F83A3A 0%, #ED0505 100%);

  /* 特殊渐变 */
  --gradient-shimmer: linear-gradient(
    90deg,
    transparent 0%,
    rgba(255, 255, 255, 0.6) 50%,
    transparent 100%
  );
  --gradient-glass: linear-gradient(
    180deg,
    rgba(255, 255, 255, 0.8) 0%,
    rgba(255, 255, 255, 0.4) 100%
  );
  --gradient-overlay: linear-gradient(
    180deg,
    rgba(0, 0, 0, 0) 0%,
    rgba(0, 0, 0, 0.5) 100%
  );
}

[data-theme="dark"] {
  --gradient-primary: linear-gradient(135deg, #68A4F3 0%, #3B8CF7 100%);
  --gradient-secondary: linear-gradient(135deg, #262626 0%, #171717 100%);
  --gradient-success: linear-gradient(135deg, #66F59F 0%, #38FA86 100%);
  --gradient-danger: linear-gradient(135deg, #F56666 0%, #F83A3A 100%);

  --gradient-glass: linear-gradient(
    180deg,
    rgba(0, 0, 0, 0.6) 0%,
    rgba(0, 0, 0, 0.3) 100%
  );
}
```

---

### 3. 骨架屏色系（Skeleton）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `skeleton-base` | Gray-200<br>#E5E5E5 | Gray-800<br>#262626 | 骨架屏基础色 |
| `skeleton-highlight` | Gray-100<br>#F5F5F5 | Gray-700<br>#404040 | 骨架屏高光色 |
| `skeleton-shimmer` | 见 `gradient-shimmer` | - | 骨架屏闪光渐变 |

**配套动画：**

```css
@keyframes skeleton-shimmer {
  0% {
    background-position: -200% 0;
  }
  100% {
    background-position: 200% 0;
  }
}

.skeleton {
  background: var(--skeleton-base);
  background-image: var(--gradient-shimmer);
  background-size: 200% 100%;
  animation: skeleton-shimmer 2s infinite;
}
```

---

### 4. 特殊装饰色（Special）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `watermark` | rgba(0,0,0,0.03) | rgba(255,255,255,0.05) | 水印颜色（极低透明度） |
| `focus-ring` | rgba(7,112,250,0.3) | rgba(7,112,250,0.4) | 聚焦环颜色（蓝色 Blue-600） |
| `focus-ring-error` | rgba(237,5,5,0.3) | rgba(237,5,5,0.4) | 错误聚焦环（红色 Red-600） |
| `selection-bg` | rgba(7,112,250,0.2) | rgba(7,112,250,0.3) | 文本选中背景 |
| `selection-text` | #171717 | #FAFAFA | 文本选中颜色 |
| `mark-bg` | Yellow-200<br>#F6EACB | Yellow-800<br>#664B00 | 标记/高亮背景（<mark>） |
| `mark-text` | #171717 | #FAFAFA | 标记文本颜色 |

**CSS 定义：**

```css
:root {
  --watermark: rgba(0, 0, 0, 0.03);
  --focus-ring: rgba(7, 112, 250, 0.3);
  --focus-ring-error: rgba(237, 5, 5, 0.3);
  --selection-bg: rgba(7, 112, 250, 0.2);
  --selection-text: #171717;
  --mark-bg: #F6EACB;
  --mark-text: #171717;
}

[data-theme="dark"] {
  --watermark: rgba(255, 255, 255, 0.05);
  --focus-ring: rgba(7, 112, 250, 0.4);
  --focus-ring-error: rgba(237, 5, 5, 0.4);
  --selection-bg: rgba(7, 112, 250, 0.3);
  --selection-text: #FAFAFA;
  --mark-bg: #664B00;
  --mark-text: #FAFAFA;
}

/* 全局文本选中样式 */
::selection {
  background: var(--selection-bg);
  color: var(--selection-text);
}

/* 标记样式 */
mark {
  background: var(--mark-bg);
  color: var(--mark-text);
}
```

---

## 使用示例

### 1. 卡片阴影

```html
<div class="card">卡片内容</div>
```

```css
.card {
  background: var(--bg-card);
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-base);
  transition: box-shadow 0.2s;
}

.card:hover {
  box-shadow: var(--shadow-md);
}
```

### 2. 渐变按钮

```html
<button class="button-gradient">渐变按钮</button>
```

```css
.button-gradient {
  background: var(--gradient-primary);
  color: white;
  border: none;
  padding: var(--spacing-3) var(--spacing-6);
  border-radius: var(--radius-md);
  font-weight: 500;
}

.button-gradient:hover {
  filter: brightness(1.1);
}
```

### 3. 骨架屏

```html
<div class="skeleton skeleton-text"></div>
<div class="skeleton skeleton-avatar"></div>
```

```css
.skeleton {
  background: var(--skeleton-base);
  background-image: var(--gradient-shimmer);
  background-size: 200% 100%;
  animation: skeleton-shimmer 2s infinite;
  border-radius: var(--radius-md);
}

.skeleton-text {
  height: 16px;
  margin-bottom: var(--spacing-2);
}

.skeleton-avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
}
```

### 4. 聚焦环

```html
<input type="text" class="input-focus" />
```

```css
.input-focus {
  border: 1px solid var(--border-primary);
  padding: var(--spacing-2) var(--spacing-3);
  border-radius: var(--radius-md);
  outline: none;
  transition: all 0.2s;
}

.input-focus:focus {
  border-color: var(--interactive-primary);
  box-shadow: var(--shadow-outline);
}

/* 错误状态 */
.input-focus.error:focus {
  border-color: var(--functional-error-border);
  box-shadow: 0 0 0 3px var(--focus-ring-error);
}
```

### 5. 玻璃态效果

```html
<div class="glass-card">
  <p>玻璃态卡片</p>
</div>
```

```css
.glass-card {
  background: var(--gradient-glass);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: var(--radius-lg);
  padding: var(--spacing-6);
  box-shadow: var(--shadow-lg);
}
```

### 6. 图片遮罩

```html
<div class="image-overlay">
  <img src="image.jpg" alt="图片" />
  <div class="overlay">
    <h3>标题</h3>
    <p>描述文字</p>
  </div>
</div>
```

```css
.image-overlay {
  position: relative;
  border-radius: var(--radius-lg);
  overflow: hidden;
}

.image-overlay .overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: var(--spacing-6);
  background: var(--gradient-overlay);
  color: white;
}
```

---

## 设计原则

### 1. 阴影层级

```
shadow-xs (1px)   → 按钮微凸
shadow-sm (2px)   → 卡片悬停
shadow-base (4px) → 下拉菜单、卡片
shadow-md (8px)   → 模态框、Popover
shadow-lg (16px)  → 抽屉、侧边栏
shadow-xl (24px)  → 全屏浮层
```

**原则：**
- 阴影不超过 6 级，避免层级混乱
- Y 轴偏移 = 模糊半径 / 2
- 透明度随深度递增

### 2. 渐变角度

- **135deg**：对角渐变（默认），视觉自然
- **90deg**：水平渐变，用于动画
- **180deg**：垂直渐变，用于遮罩

### 3. 骨架屏动画时长

- **2 秒**：标准速度，平衡流畅性和性能
- **1.5 秒**：快速加载场景
- **3 秒**：大数据加载场景

### 4. 聚焦环设计

- **厚度**：3px（符合 WCAG 2.2 Focus Appearance）
- **颜色**：主品牌色 Blue-600，透明度 30-40%
- **错误状态**：Red-600，透明度 30-40%
- **成功状态**：可选，Green-600

---

## Token 总览

| 分类 | Token 数量 | 浅色/暗色 | 完成度 |
|------|----------|----------|-------|
| 阴影色 | 8 | ✅ / ✅ | 100% |
| 渐变色 | 8 | ✅ / ✅ | 100% |
| 骨架屏 | 3 | ✅ / ✅ | 100% |
| 特殊装饰 | 7 | ✅ / ✅ | 100% |
| **合计** | **26** | - | **100%** |

---

**相关文档：**
- [语义化色彩总览](./README.md)
- [背景色 Token](./background-colors.md)
- [功能色 Token](./functional-colors.md)

**文档版本：** v1.0
**最后更新：** 2025-11-16
