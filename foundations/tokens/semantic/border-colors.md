# 边框色 Token 清单

> 所有边框和分割线相关的颜色定义。

---

## 完整 Token 清单

### 1. 层级边框色（Hierarchy）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `border-primary` | Gray-300<br>#D4D4D4 | Gray-700<br>#404040 | 主边框（输入框、卡片） |
| `border-secondary` | Gray-200<br>#E5E5E5 | Gray-800<br>#262626 | 次级边框（表格内线） |
| `border-tertiary` | Gray-100<br>#F5F5F5 | Gray-900<br>#171717 | 三级边框（极弱分割） |

---

### 2. 状态边框色（State）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `border-hover` | Gray-400<br>#A3A3A3 | Gray-600<br>#525252 | 悬停边框 |
| `border-focus` | Blue-500<br>#3B82F6 | Blue-500<br>#3B82F6 | 焦点边框 |
| `border-active` | Blue-600<br>#2563EB | Blue-400<br>#60A5FA | 激活边框 |
| `border-disabled` | Gray-200<br>#E5E5E5 | Gray-800<br>#262626 | 禁用边框 |
| `border-selected` | Blue-600<br>#2563EB | Blue-400<br>#60A5FA | 选中边框 |

---

### 3. 功能反馈边框色（Functional）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `border-success` | Green-500<br>#22C55E | Green-500<br>#22C55E | 成功边框 |
| `border-warning` | Yellow-500<br>#EAB308 | Yellow-500<br>#EAB308 | 警告边框 |
| `border-error` | Red-500<br>#EF4444 | Red-500<br>#EF4444 | 错误边框 |
| `border-info` | Cyan-500<br>#06B6D4 | Cyan-500<br>#06B6D4 | 信息边框 |

**注意：** 功能色边框在浅色/暗色模式保持一致（500 色阶），确保视觉连续性

---

### 4. 分割线（Divider）

| Token | 浅色模式 | 暗色模式 | 用途 |
|-------|---------|---------|------|
| `divider-primary` | Gray-200<br>#E5E5E5 | Gray-700<br>#404040 | 主分割线 |
| `divider-secondary` | Gray-100<br>#F5F5F5 | Gray-800<br>#262626 | 次级分割线 |
| `divider-strong` | Gray-300<br>#D4D4D4 | Gray-600<br>#525252 | 强调分割线 |

---

## CSS Variables 定义

```css
:root {
  /* 层级边框 */
  --border-primary: #D4D4D4;
  --border-secondary: #E5E5E5;
  
  /* 状态边框 */
  --border-hover: #A3A3A3;
  --border-focus: #3B82F6;
  --border-disabled: #E5E5E5;
  
  /* 功能边框 */
  --border-success: #22C55E;
  --border-warning: #EAB308;
  --border-error: #EF4444;
  
  /* 分割线 */
  --divider-primary: #E5E5E5;
}

[data-theme="dark"] {
  /* 层级边框 */
  --border-primary: #404040;
  --border-secondary: #262626;
  
  /* 状态边框 */
  --border-hover: #525252;
  --border-focus: #3B82F6;
  --border-disabled: #262626;
  
  /* 功能边框（保持一致） */
  --border-success: #22C55E;
  --border-warning: #EAB308;
  --border-error: #EF4444;
  
  /* 分割线 */
  --divider-primary: #404040;
}
```

---

**相关文档：**
- [语义化色彩总览](../semantic-colors.md)
- [背景色 Token](./background-colors.md)

**文档版本：** v1.0
**最后更新：** 2025-11-16
