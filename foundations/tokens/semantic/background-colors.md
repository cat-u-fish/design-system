# 背景色 Token 清单

> 所有背景填充相关的颜色定义，覆盖页面、容器、输入框、状态等所有背景场景。

---

## 完整 Token 清单

### 1. 层级背景色（Hierarchy）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-primary` | White<br>#FFFFFF | Gray-900<br>#171717 | 主背景（页面） |
| `bg-secondary` | Gray-50<br>#FAFAFA | Gray-800<br>#262626 | 次级背景（卡片、面板） |
| `bg-tertiary` | Gray-100<br>#F5F5F5 | Gray-700<br>#404040 | 三级背景（悬浮、下拉） |
| `bg-quaternary` | Gray-200<br>#E5E5E5 | Gray-600<br>#525252 | 四级背景（极少用） |

---

### 2. 输入/表单背景色（Input）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-input` | White<br>#FFFFFF | Gray-800<br>#262626 | 输入框默认背景 |
| `bg-input-hover` | Gray-50<br>#FAFAFA | Gray-700<br>#404040 | 输入框悬停背景 |
| `bg-input-focus` | White<br>#FFFFFF | Gray-800<br>#262626 | 输入框聚焦背景 |
| `bg-input-disabled` | Gray-100<br>#F5F5F5 | Gray-800<br>#262626 | 输入框禁用背景 |
| `bg-input-readonly` | Gray-50<br>#FAFAFA | Gray-700<br>#404040 | 输入框只读背景 |

---

### 3. 状态背景色（State）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-hover` | Gray-50<br>#FAFAFA | Gray-800<br>#262626 | 通用悬停背景 |
| `bg-active` | Gray-100<br>#F5F5F5 | Gray-700<br>#404040 | 通用激活背景 |
| `bg-selected` | Blue-50<br>#F5F7FA | Blue-950<br>#011C40 | 选中项背景 |
| `bg-selected-hover` | Blue-100<br>#E9EFF7 | Blue-900<br>#1E3A8A | 选中项悬停 |
| `bg-disabled` | Gray-100<br>#F5F5F5 | Gray-800<br>#262626 | 禁用背景 |

---

### 4. 功能反馈背景色（Functional）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-success` | Green-50<br>#F4FAF7 | Green-950<br>#003314 | 成功背景（淡绿） |
| `bg-success-subtle` | Green-50<br>#F4FAF7 | rgba(Green-500, 0.1) | 极淡成功背景 |
| `bg-warning` | Yellow-50<br>#FBF9F4 | Yellow-950<br>#332500 | 警告背景（淡黄） |
| `bg-warning-subtle` | Yellow-50<br>#FBF9F4 | rgba(Yellow-500, 0.1) | 极淡警告背景 |
| `bg-error` | Red-50<br>#FAF4F4 | Red-950<br>#380000 | 错误背景（淡红） |
| `bg-error-subtle` | Red-50<br>#FAF4F4 | rgba(Red-500, 0.1) | 极淡错误背景 |
| `bg-info` | Cyan-50<br>#ECFEFF | Cyan-950<br>#083344 | 信息背景（淡蓝） |
| `bg-info-subtle` | Cyan-50<br>#ECFEFF | rgba(Cyan-500, 0.1) | 极淡信息背景 |

---

### 5. 遮罩/覆盖背景色（Overlay）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-overlay` | rgba(0,0,0,0.5) | rgba(0,0,0,0.7) | 模态框遮罩 |
| `bg-overlay-light` | rgba(0,0,0,0.3) | rgba(0,0,0,0.5) | 轻度遮罩 |
| `bg-overlay-heavy` | rgba(0,0,0,0.7) | rgba(0,0,0,0.85) | 重度遮罩 |
| `bg-backdrop-blur` | rgba(255,255,255,0.8) | rgba(17,24,39,0.8) | 毛玻璃遮罩 |

---

### 6. 特殊场景背景色（Special）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-code` | Gray-100<br>#F5F5F5 | Gray-800<br>#262626 | 代码块背景 |
| `bg-code-inline` | Gray-100<br>#F5F5F5 | Gray-800<br>#262626 | 行内代码背景 |
| `bg-skeleton` | Gray-200<br>#E5E5E5 | Gray-700<br>#404040 | 骨架屏背景 |
| `bg-skeleton-shimmer` | Gray-100<br>#F5F5F5 | Gray-600<br>#525252 | 骨架屏动画 |
| `bg-tooltip` | Gray-900<br>#171717 | Gray-700<br>#404040 | 工具提示背景 |
| `bg-popover` | White<br>#FFFFFF | Gray-800<br>#262626 | 气泡卡片背景 |
| `bg-modal` | White<br>#FFFFFF | Gray-800<br>#262626 | 模态框背景 |
| `bg-drawer` | White<br>#FFFFFF | Gray-900<br>#171717 | 抽屉背景 |

---

### 7. 表格背景色（Table）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `bg-table-header` | Gray-50<br>#FAFAFA | Gray-800<br>#262626 | 表头背景 |
| `bg-table-row` | White<br>#FFFFFF | Gray-900<br>#171717 | 表格行默认背景 |
| `bg-table-row-hover` | Gray-50<br>#FAFAFA | Gray-800<br>#262626 | 表格行悬停 |
| `bg-table-row-selected` | Blue-50<br>#F5F7FA | Blue-950<br>#011C40 | 表格行选中 |
| `bg-table-zebra` | Gray-50<br>#FAFAFA | Gray-850<br>rgba(31,41,55,0.5) | 斑马纹（偶数行） |

---

## CSS Variables 定义

```css
:root {
  /* 层级背景 */
  --bg-primary: #FFFFFF;
  --bg-secondary: #FAFAFA;
  --bg-tertiary: #F5F5F5;
  
  /* 输入/表单 */
  --bg-input: #FFFFFF;
  --bg-input-disabled: #F5F5F5;
  
  /* 状态 */
  --bg-hover: #FAFAFA;
  --bg-selected: #F5F7FA;
  
  /* 功能反馈 */
  --bg-success: #F4FAF7;
  --bg-warning: #FBF9F4;
  --bg-error: #FAF4F4;
  --bg-info: #ECFEFF;
  
  /* 遮罩 */
  --bg-overlay: rgba(0,0,0,0.5);
  
  /* 特殊场景 */
  --bg-code: #F5F5F5;
  --bg-tooltip: #171717;
}

[data-theme="dark"] {
  /* 层级背景 */
  --bg-primary: #171717;
  --bg-secondary: #262626;
  --bg-tertiary: #404040;
  
  /* 输入/表单 */
  --bg-input: #262626;
  --bg-input-disabled: #262626;
  
  /* 状态 */
  --bg-hover: #262626;
  --bg-selected: #011C40;
  
  /* 功能反馈 */
  --bg-success: #003314;
  --bg-warning: #332500;
  --bg-error: #380000;
  --bg-info: #083344;
  
  /* 遮罩 */
  --bg-overlay: rgba(0,0,0,0.7);
  
  /* 特殊场景 */
  --bg-code: #262626;
  --bg-tooltip: #404040;
}
```

---

**相关文档：**
- [语义化色彩总览](../semantic-colors.md)
- [文本色 Token](./text-colors.md)
- [边框色 Token](./border-colors.md)

**文档版本：** v1.0
**最后更新：** 2025-11-16
