# 扩展色板 - 多彩语义色阶

> 基于 HSL 色彩空间生成的 12 色完整色板系统。
> 每个颜色都经过 **科学的亮度和饱和度曲线调整**，确保视觉和谐且符合可访问性标准。

---

## 色板生成原理

### HSL 色彩空间

所有颜色基于 **H（色相）、S（饱和度）、L（亮度）** 三个维度生成：

```
色阶生成公式：
  H (Hue):        保持恒定（定义颜色类别）
  S (Saturation): 浅色降低，深色降低（避免刺眼/脏）
  L (Lightness):  50: 97% → 950: 20%（贝塞尔曲线）
```

### 亮度曲线

| 色阶 | 亮度 L | 用途 |
|-----|--------|------|
| 50  | 97%    | 极浅背景 |
| 100 | 94%    | 浅背景 |
| 200 | 88%    | 边框 |
| 300 | 78%    | 辅助元素 |
| 400 | 68%    | 次要按钮 |
| **500** | **60%** | **主色调（基准）** |
| 600 | 52%    | 主按钮、链接 |
| 700 | 45%    | 悬停状态 |
| 800 | 38%    | 按下状态 |
| 900 | 30%    | 深色文本 |
| 950 | 20%    | 极深背景 |

---

## 完整 12 色色板

### 1. Gray（中性灰） - 基础色

**色相：** 无（灰度）

```
color-gray-50:  #FAFAFA   # 1.04:1
color-gray-100: #F5F5F5   # 1.09:1
color-gray-200: #E5E5E5   # 1.26:1
color-gray-300: #D4D4D4   # 1.48:1
color-gray-400: #A3A3A3   # 2.52:1
color-gray-500: #737373   # 4.74:1 ✅ AA
color-gray-600: #525252   # 7.81:1 ✅ AAA
color-gray-700: #404040   # 10.37:1 ✅ AAA
color-gray-800: #262626   # 15.13:1 ✅ AAA
color-gray-900: #171717   # 17.93:1 ✅ AAA
color-gray-950: #0A0A0A   # 19.8:1 ✅ AAA
```

**用途：** 文本、边框、背景、中性元素

---

### 2. Blue（蓝色） - 主品牌色

**色相：** H = 214°
**用户定义：** `#1D75E8`

```
color-blue-50:  #F5F7FA   # 1.07:1
color-blue-100: #E9EFF7   # 1.16:1
color-blue-200: #CEDEF3   # 1.37:1
color-blue-300: #9DC1F1   # 1.85:1
color-blue-400: #68A4F3   # 2.56:1
color-blue-500: #3B8CF7   # 3.34:1 ⚠️ 主品牌色
color-blue-600: #0770FA   # 4.46:1 ⚠️ 接近 AA
color-blue-700: #0354BD   # 6.98:1 ✅ AA (接近 AAA)
color-blue-800: #02449B   # 9.12:1 ✅ AAA
color-blue-900: #013272   # 12.35:1 ✅ AAA
color-blue-950: #011C40   # 16.92:1 ✅ AAA
```

**用途：** 主要交互元素、链接、强调
**注意：** Blue-600 对比度 4.46:1，略低于 AA 标准 4.5:1，建议文本使用 Blue-700

---

### 3. Purple（紫色） - 创意/高级

**色相：** H = 270°

```
color-purple-50:  #FAF5FF   # 1.07:1
color-purple-100: #F3E8FF   # 1.18:1
color-purple-200: #E9D5FF   # 1.36:1
color-purple-300: #D8B4FE   # 1.77:1
color-purple-400: #C084FC   # 2.64:1
color-purple-500: #A855F7   # 3.96:1 ⚠️ 主紫色
color-purple-600: #9333EA   # 5.38:1 ✅ AA
color-purple-700: #7E22CE   # 6.98:1 ✅ AA (接近 AAA)
color-purple-800: #6B21A8   # 8.72:1 ✅ AAA
color-purple-900: #581C87   # 10.88:1 ✅ AAA
color-purple-950: #3B0764   # 15.0:1 ✅ AAA
```

**用途：** 创意功能、VIP 标识、高级特性

---

### 4. Pink（粉色） - 活力/社交

**色相：** H = 330°

```
color-pink-50:  #FDF2F8   # 1.09:1
color-pink-100: #FCE7F3   # 1.18:1
color-pink-200: #FBCFE8   # 1.38:1
color-pink-300: #F9A8D4   # 1.81:1
color-pink-400: #F472B6   # 2.65:1
color-pink-500: #EC4899   # 3.53:1 ⚠️ 主粉色
color-pink-600: #DB2777   # 4.6:1 ✅ AA
color-pink-700: #BE185D   # 6.04:1 ✅ AA
color-pink-800: #9D174D   # 7.88:1 ✅ AAA
color-pink-900: #831843   # 9.65:1 ✅ AAA
color-pink-950: #500724   # 15.03:1 ✅ AAA
```

**用途：** 社交功能、收藏/喜欢、女性向产品

---

### 5. Red（红色） - 错误/危险

**色相：** H = 0°
**用户定义：** `#F51D1D`

```
color-red-50:  #FAF4F4   # 1.09:1
color-red-100: #F7E8E8   # 1.19:1
color-red-200: #F4CDCD   # 1.45:1
color-red-300: #F49A9A   # 2.11:1
color-red-400: #F56666   # 3.01:1 ⚠️
color-red-500: #F83A3A   # 3.71:1 ⚠️ 主错误色
color-red-600: #ED0505   # 4.54:1 ✅ AA
color-red-700: #B60202   # 7.0:1 ✅ AAA
color-red-800: #940000   # 9.3:1 ✅ AAA
color-red-900: #6B0000   # 12.92:1 ✅ AAA
color-red-950: #380000   # 17.98:1 ✅ AAA
```

**用途：** 错误提示、删除操作、危险警告

---

### 6. Orange（橙色） - 警示/热度

**色相：** H = 25°

```
color-orange-50:  #FFF7ED   # 1.06:1
color-orange-100: #FFEDD5   # 1.15:1
color-orange-200: #FED7AA   # 1.35:1
color-orange-300: #FDBA74   # 1.69:1
color-orange-400: #FB923C   # 2.26:1
color-orange-500: #F97316   # 2.8:1 主橙色
color-orange-600: #EA580C   # 3.56:1 ⚠️
color-orange-700: #C2410C   # 5.18:1 ✅ AA
color-orange-800: #9A3412   # 7.31:1 ✅ AAA
color-orange-900: #7C2D12   # 9.37:1 ✅ AAA
color-orange-950: #431407   # 15.65:1 ✅ AAA
```

**用途：** 热度标识、紧急通知、促销活动
**注意：** Orange-600 对比度 3.56:1，不达 AA 标准，建议文本使用 Orange-700

---

### 7. Yellow（黄色） - 警告/提示

**色相：** H = 44°
**用户定义：** `#FFBC00`

```
color-yellow-50:  #FBF9F4   # 1.05:1
color-yellow-100: #F8F4E7   # 1.1:1
color-yellow-200: #F6EACB   # 1.2:1
color-yellow-300: #F7DD97   # 1.33:1
color-yellow-400: #F9D162   # 1.47:1
color-yellow-500: #FFC933   # 1.54:1 主警告色
color-yellow-600: #997000   # 4.49:1 ⚠️ 接近 AA（已偏棕色）
color-yellow-700: #725400   # 7.04:1 ✅ AAA（推荐）
color-yellow-800: #664B00   # 8.17:1 ✅ AAA
color-yellow-900: #4C3800   # 11.21:1 ✅ AAA
color-yellow-950: #332500   # 14.94:1 ✅ AAA
```

**用途：** 警告提示、待处理状态、高亮标记
**注意：** 黄色本身亮度高，600 级为达到对比度已偏棕色，建议功能色使用 **Yellow-700**

---

### 8. Lime（青柠） - 新鲜/活力

**色相：** H = 75°

```
color-lime-50:  #F7FEE7   # 1.04:1
color-lime-100: #ECFCCB   # 1.09:1
color-lime-200: #D9F99D   # 1.17:1
color-lime-300: #BEF264   # 1.31:1
color-lime-400: #A3E635   # 1.51:1
color-lime-500: #84CC16   # 1.98:1 主青柠色
color-lime-600: #65A30D   # 3.09:1 ⚠️
color-lime-700: #4D7C0F   # 4.99:1 ✅ AA
color-lime-800: #3F6212   # 7.08:1 ✅ AAA
color-lime-900: #365314   # 8.73:1 ✅ AAA
color-lime-950: #1A2E05   # 14.61:1 ✅ AAA
```

**用途：** 新功能标识、环保主题、增长趋势
**注意：** Lime-600 对比度 3.09:1，不达 AA 标准，建议文本使用 Lime-700

---

### 9. Green（绿色） - 成功/确认

**色相：** H = 144°
**用户定义：** `#009E3E`

```
color-green-50:  #F4FAF7   # 1.06:1
color-green-100: #E8F7EE   # 1.11:1
color-green-200: #CDF4DC   # 1.2:1
color-green-300: #9AF4BE   # 1.31:1
color-green-400: #66F59F   # 1.39:1
color-green-500: #38FA86   # 1.38:1 主成功色
color-green-600: #008937   # 4.53:1 ✅ AA
color-green-700: #006829   # 6.97:1 ✅ AA (接近 AAA)
color-green-800: #006629   # 7.16:1 ✅ AAA
color-green-900: #004C1F   # 10.23:1 ✅ AAA
color-green-950: #003314   # 14.15:1 ✅ AAA
```

**用途：** 成功提示、确认操作、正向反馈

---

### 10. Teal（青绿） - 平静/数据

**色相：** H = 173°

```
color-teal-50:  #F0FDFA   # 1.04:1
color-teal-100: #CCFBF1   # 1.13:1
color-teal-200: #99F6E4   # 1.26:1
color-teal-300: #5EEAD4   # 1.48:1
color-teal-400: #2DD4BF   # 1.86:1
color-teal-500: #14B8A6   # 2.49:1 主青绿色
color-teal-600: #0D9488   # 3.74:1 ⚠️
color-teal-700: #0F766E   # 5.47:1 ✅ AA
color-teal-800: #115E59   # 7.58:1 ✅ AAA
color-teal-900: #134E4A   # 9.48:1 ✅ AAA
color-teal-950: #042F2E   # 14.47:1 ✅ AAA
```

**用途：** 数据可视化、辅助信息、冷静色调
**注意：** Teal-600 对比度 3.74:1，不达 AA 标准，建议文本使用 Teal-700

---

### 11. Cyan（青色） - 信息/科技

**色相：** H = 190°

```
color-cyan-50:  #ECFEFF   # 1.04:1
color-cyan-100: #CFFAFE   # 1.12:1
color-cyan-200: #A5F3FC   # 1.25:1
color-cyan-300: #67E8F9   # 1.45:1
color-cyan-400: #22D3EE   # 1.81:1
color-cyan-500: #06B6D4   # 2.43:1 主信息色
color-cyan-600: #0891B2   # 3.68:1 ⚠️
color-cyan-700: #0E7490   # 5.36:1 ✅ AA
color-cyan-800: #155E75   # 7.27:1 ✅ AAA
color-cyan-900: #164E63   # 9.11:1 ✅ AAA
color-cyan-950: #083344   # 13.4:1 ✅ AAA
```

**用途：** 信息提示、链接辅助、科技感元素
**注意：** Cyan-600 对比度 3.68:1，不达 AA 标准，建议文本使用 Cyan-700

---

### 12. Indigo（靛蓝） - 深度/专业

**色相：** H = 239°

```
color-indigo-50:  #EEF2FF   # 1.12:1
color-indigo-100: #E0E7FF   # 1.23:1
color-indigo-200: #C7D2FE   # 1.49:1
color-indigo-300: #A5B4FC   # 1.99:1
color-indigo-400: #818CF8   # 2.98:1
color-indigo-500: #6366F1   # 4.47:1 ⚠️ 主靛蓝色
color-indigo-600: #4F46E5   # 6.29:1 ✅ AA
color-indigo-700: #4338CA   # 7.9:1 ✅ AAA
color-indigo-800: #3730A3   # 9.93:1 ✅ AAA
color-indigo-900: #312E81   # 11.42:1 ✅ AAA
color-indigo-950: #1E1B4B   # 15.99:1 ✅ AAA
```

**用途：** 专业版功能、深度分析、企业级特性

---

## 语义化色彩应用

### 功能色映射

```
成功（Success）:   Green-600   #008937  (对比度 4.53:1 ✅ AA)
警告（Warning）:   Yellow-700  #725400  (对比度 7.04:1 ✅ AAA，600 偏棕色不推荐)
错误（Error）:     Red-600     #ED0505  (对比度 4.54:1 ✅ AA)
信息（Info）:      Blue-700    #0354BD  (对比度 6.98:1 ✅ AA，600 为 4.46:1 略低)
```

### 扩展语义色

```
# 状态色
color-status-pending:    {color-orange-700}   # 待处理（推荐 700，600 不达标）
color-status-processing: #0354BD              # 处理中 (Blue-700，推荐)
color-status-completed:  #008937              # 已完成 (Green-600, 4.53:1 ✅)
color-status-canceled:   {color-gray-600}     # 已取消 (7.81:1 ✅)
color-status-failed:     #ED0505              # 失败 (Red-600, 4.54:1 ✅)

# 优先级色
color-priority-critical:  #ED0505             # 紧急 (Red-600, 4.54:1 ✅)
color-priority-high:      {color-orange-700}  # 高（推荐 700，600 不达标）
color-priority-medium:    #725400             # 中 (Yellow-700, 7.04:1 ✅)
color-priority-low:       {color-gray-600}    # 低 (7.81:1 ✅)

# 数据可视化色（背景/图表用，非文本）
color-chart-1:  #0770FA              # 图表主色 (Blue-600)
color-chart-2:  {color-purple-600}   # 图表辅色 1 (5.38:1 ✅)
color-chart-3:  {color-teal-600}     # 图表辅色 2 (3.74:1 ⚠️ 仅用于图表)
color-chart-4:  {color-orange-600}   # 图表辅色 3 (3.56:1 ⚠️ 仅用于图表)
color-chart-5:  {color-pink-600}     # 图表辅色 4 (4.6:1 ✅)
color-chart-6:  {color-lime-600}     # 图表辅色 5 (3.09:1 ⚠️ 仅用于图表)

# 社交/情感色（图标/装饰用）
color-social-like:      {color-pink-600}     # 喜欢/收藏 (4.6:1 ✅)
color-social-share:     {color-cyan-700}     # 分享（推荐 700）
color-social-comment:   {color-purple-600}   # 评论 (5.38:1 ✅)
color-social-follow:    #0354BD              # 关注 (Blue-700，推荐)
```

---

## 数据可视化专用色板

### 分类色板（Categorical）- 用于离散数据

**8 色方案（高对比度）：**
```
viz-cat-1:  #0770FA   (Blue-600, 4.46:1)
viz-cat-2:  #9333EA   (Purple-600, 5.38:1 ✅)
viz-cat-3:  #008937   (Green-600, 4.53:1 ✅)
viz-cat-4:  #EA580C   (Orange-600, 3.56:1 ⚠️ 仅图表)
viz-cat-5:  #DB2777   (Pink-600, 4.6:1 ✅)
viz-cat-6:  #0891B2   (Cyan-600, 3.68:1 ⚠️ 仅图表)
viz-cat-7:  #65A30D   (Lime-600, 3.09:1 ⚠️ 仅图表)
viz-cat-8:  #4F46E5   (Indigo-600, 6.29:1 ✅)

注意：部分颜色对比度不足用于文本，仅适合图表填充/描边
```

### 连续色板（Sequential）- 用于数值范围

**蓝色渐变（从浅到深）：**
```
viz-seq-blue-1: {color-blue-100}
viz-seq-blue-2: {color-blue-300}
viz-seq-blue-3: {color-blue-500}
viz-seq-blue-4: {color-blue-700}
viz-seq-blue-5: {color-blue-900}
```

### 发散色板（Diverging）- 用于正负值

**红-蓝发散：**
```
viz-div-1: #B60202              # 负极 (Red-700, 7.0:1 ✅)
viz-div-2: #F56666              # (Red-400, 3.01:1)
viz-div-3: {color-gray-200}     # 中性 (1.26:1)
viz-div-4: #68A4F3              # (Blue-400, 2.56:1)
viz-div-5: #0354BD              # 正极 (Blue-700, 6.98:1 ✅)
```

---

## 色彩对比度表

### 文本色（白色背景）对比度验证

| 颜色 | 600 色阶对比度 | 700 色阶对比度 | 推荐用途 |
|-----|--------------|--------------|---------|
| Gray | 7.81:1 ✅ AAA | 10.37:1 ✅ AAA | 常规文本 |
| Blue | 4.46:1 ⚠️ 接近 AA | 6.98:1 ✅ AA | 链接文本（推荐 700） |
| Purple | 5.38:1 ✅ AA | 6.98:1 ✅ AA | 创意文本 |
| Pink | 4.6:1 ✅ AA | 6.04:1 ✅ AA | 强调文本 |
| Red | 4.54:1 ✅ AA | 7.0:1 ✅ AAA | 错误文本 |
| Orange | 3.56:1 ❌ | 5.18:1 ✅ AA | 警示文本（推荐 700） |
| Yellow | 4.49:1 ⚠️ 已偏棕 | 7.04:1 ✅ AAA | 警告文本（推荐 700） |
| Lime | 3.09:1 ❌ | 4.99:1 ✅ AA | 新鲜文本（推荐 700） |
| Green | 4.53:1 ✅ AA | 6.97:1 ✅ AA | 成功文本 |
| Teal | 3.74:1 ❌ | 5.47:1 ✅ AA | 数据文本（推荐 700） |
| Cyan | 3.68:1 ❌ | 5.36:1 ✅ AA | 信息文本（推荐 700） |
| Indigo | 6.29:1 ✅ AA | 7.9:1 ✅ AAA | 专业文本 |

**规则：**
- ✅ AA 标准：对比度 ≥ 4.5:1（常规文本）
- ✅ AAA 标准：对比度 ≥ 7.0:1（确保所有用户可读）
- ⚠️ 接近但未达标：建议升级到 700 色阶
- ❌ 不达标：必须使用 700 或更深色阶
- 🎯 **Blue、Green、Red 已更新为用户定义的功能色**
- 📊 **实际测量值：部分 600 色阶未达 AA 标准，请优先使用 700 色阶作为文本色**

---

## 使用原则

### 1. 主色选择

**建议配置：**
```
主品牌色:      Blue（最常见）/ Indigo（专业）/ Purple（创意）
成功色:        Green
警告色:        Yellow-700（注意必须用 700）
错误色:        Red
信息色:        Cyan / Blue
```

### 2. 色彩层级

```
50-200:   背景色、边框色
300-400:  悬停状态、辅助元素
500:      主色调基准（视觉识别）
600:      文本色、主按钮（确保对比度）
700-900:  深色状态、深色模式
```

### 3. 避免滥用

**❌ 不要：**
- 在同一页面使用超过 3 种主色
- 用彩色作为大面积背景（除非品牌需要）
- 忽略对比度要求

**✅ 推荐：**
- 90% 使用 Gray（中性）
- 8% 使用 Blue（主色）
- 2% 使用功能色（Red/Green/Yellow）

---

## JSON 格式示例

```json
{
  "color": {
    "purple": {
      "50": { "value": "#FAF5FF", "type": "color" },
      "100": { "value": "#F3E8FF", "type": "color" },
      "500": { "value": "#A855F7", "type": "color", "description": "主紫色" },
      "600": { "value": "#9333EA", "type": "color", "description": "文本用，对比度 5.2:1" }
    },
    "status": {
      "pending": {
        "value": "{color.orange.600}",
        "type": "color",
        "description": "待处理状态"
      }
    }
  }
}
```

---

## 工具推荐

### 颜色生成工具
- [UI Colors](https://uicolors.app/) - 自动生成完整色阶
- [Leonardo](https://leonardocolor.io/) - 基于对比度生成色板
- [Coolors](https://coolors.co/) - 配色方案生成

### 对比度检查
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Figma Plugin: Stark](https://www.figma.com/community/plugin/732603254453395948)

---

**文档版本：** v1.0
**最后更新：** 2025-11-16
**相关文档：** [Design Token 规范](./README.md) | [设计原理](./design-principles.md)
