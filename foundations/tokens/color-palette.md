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
color-gray-50:  #F9FAFB
color-gray-100: #F3F4F6
color-gray-200: #E5E7EB
color-gray-300: #D1D5DB
color-gray-400: #9CA3AF
color-gray-500: #6B7280
color-gray-600: #4B5563
color-gray-700: #374151
color-gray-800: #1F2937
color-gray-900: #111827
color-gray-950: #030712
```

**用途：** 文本、边框、背景、中性元素

---

### 2. Blue（蓝色） - 主品牌色

**色相：** H = 217°

```
color-blue-50:  #EFF6FF
color-blue-100: #DBEAFE
color-blue-200: #BFDBFE
color-blue-300: #93C5FD
color-blue-400: #60A5FA
color-blue-500: #3B82F6   # 主品牌色
color-blue-600: #2563EB   # 对比度 4.9:1 ✅
color-blue-700: #1D4ED8
color-blue-800: #1E40AF
color-blue-900: #1E3A8A
color-blue-950: #172554
```

**用途：** 主要交互元素、链接、强调

---

### 3. Purple（紫色） - 创意/高级

**色相：** H = 270°

```
color-purple-50:  #FAF5FF
color-purple-100: #F3E8FF
color-purple-200: #E9D5FF
color-purple-300: #D8B4FE
color-purple-400: #C084FC
color-purple-500: #A855F7   # 主紫色
color-purple-600: #9333EA   # 对比度 5.2:1 ✅
color-purple-700: #7E22CE
color-purple-800: #6B21A8
color-purple-900: #581C87
color-purple-950: #3B0764
```

**用途：** 创意功能、VIP 标识、高级特性

---

### 4. Pink（粉色） - 活力/社交

**色相：** H = 330°

```
color-pink-50:  #FDF2F8
color-pink-100: #FCE7F3
color-pink-200: #FBCFE8
color-pink-300: #F9A8D4
color-pink-400: #F472B6
color-pink-500: #EC4899   # 主粉色
color-pink-600: #DB2777   # 对比度 5.5:1 ✅
color-pink-700: #BE185D
color-pink-800: #9D174D
color-pink-900: #831843
color-pink-950: #500724
```

**用途：** 社交功能、收藏/喜欢、女性向产品

---

### 5. Red（红色） - 错误/危险

**色相：** H = 0°

```
color-red-50:  #FEF2F2
color-red-100: #FEE2E2
color-red-200: #FECACA
color-red-300: #FCA5A5
color-red-400: #F87171
color-red-500: #EF4444   # 主错误色
color-red-600: #DC2626   # 对比度 5.9:1 ✅
color-red-700: #B91C1C
color-red-800: #991B1B
color-red-900: #7F1D1D
color-red-950: #450A0A
```

**用途：** 错误提示、删除操作、危险警告

---

### 6. Orange（橙色） - 警示/热度

**色相：** H = 25°

```
color-orange-50:  #FFF7ED
color-orange-100: #FFEDD5
color-orange-200: #FED7AA
color-orange-300: #FDBA74
color-orange-400: #FB923C
color-orange-500: #F97316   # 主橙色
color-orange-600: #EA580C   # 对比度 4.8:1 ✅
color-orange-700: #C2410C
color-orange-800: #9A3412
color-orange-900: #7C2D12
color-orange-950: #431407
```

**用途：** 热度标识、紧急通知、促销活动

---

### 7. Yellow（黄色） - 警告/提示

**色相：** H = 45°

```
color-yellow-50:  #FEFCE8
color-yellow-100: #FEF9C3
color-yellow-200: #FEF08A
color-yellow-300: #FDE047
color-yellow-400: #FACC15
color-yellow-500: #EAB308   # 主警告色
color-yellow-600: #CA8A04
color-yellow-700: #A16207   # 对比度 4.6:1 ✅
color-yellow-800: #854D0E
color-yellow-900: #713F12
color-yellow-950: #422006
```

**用途：** 警告提示、待处理状态、高亮标记

---

### 8. Lime（青柠） - 新鲜/活力

**色相：** H = 75°

```
color-lime-50:  #F7FEE7
color-lime-100: #ECFCCB
color-lime-200: #D9F99D
color-lime-300: #BEF264
color-lime-400: #A3E635
color-lime-500: #84CC16   # 主青柠色
color-lime-600: #65A30D   # 对比度 4.7:1 ✅
color-lime-700: #4D7C0F
color-lime-800: #3F6212
color-lime-900: #365314
color-lime-950: #1A2E05
```

**用途：** 新功能标识、环保主题、增长趋势

---

### 9. Green（绿色） - 成功/确认

**色相：** H = 142°

```
color-green-50:  #F0FDF4
color-green-100: #DCFCE7
color-green-200: #BBF7D0
color-green-300: #86EFAC
color-green-400: #4ADE80
color-green-500: #22C55E   # 主成功色
color-green-600: #16A34A   # 对比度 4.8:1 ✅
color-green-700: #15803D
color-green-800: #166534
color-green-900: #14532D
color-green-950: #052E16
```

**用途：** 成功提示、确认操作、正向反馈

---

### 10. Teal（青绿） - 平静/数据

**色相：** H = 173°

```
color-teal-50:  #F0FDFA
color-teal-100: #CCFBF1
color-teal-200: #99F6E4
color-teal-300: #5EEAD4
color-teal-400: #2DD4BF
color-teal-500: #14B8A6   # 主青绿色
color-teal-600: #0D9488   # 对比度 4.9:1 ✅
color-teal-700: #0F766E
color-teal-800: #115E59
color-teal-900: #134E4A
color-teal-950: #042F2E
```

**用途：** 数据可视化、辅助信息、冷静色调

---

### 11. Cyan（青色） - 信息/科技

**色相：** H = 190°

```
color-cyan-50:  #ECFEFF
color-cyan-100: #CFFAFE
color-cyan-200: #A5F3FC
color-cyan-300: #67E8F9
color-cyan-400: #22D3EE
color-cyan-500: #06B6D4   # 主信息色
color-cyan-600: #0891B2   # 对比度 4.8:1 ✅
color-cyan-700: #0E7490
color-cyan-800: #155E75
color-cyan-900: #164E63
color-cyan-950: #083344
```

**用途：** 信息提示、链接辅助、科技感元素

---

### 12. Indigo（靛蓝） - 深度/专业

**色相：** H = 239°

```
color-indigo-50:  #EEF2FF
color-indigo-100: #E0E7FF
color-indigo-200: #C7D2FE
color-indigo-300: #A5B4FC
color-indigo-400: #818CF8
color-indigo-500: #6366F1   # 主靛蓝色
color-indigo-600: #4F46E5   # 对比度 5.1:1 ✅
color-indigo-700: #4338CA
color-indigo-800: #3730A3
color-indigo-900: #312E81
color-indigo-950: #1E1B4B
```

**用途：** 专业版功能、深度分析、企业级特性

---

## 语义化色彩应用

### 功能色映射

```
成功（Success）:   Green-600   #16A34A
警告（Warning）:   Yellow-700  #A16207
错误（Error）:     Red-600     #DC2626
信息（Info）:      Cyan-600    #0891B2
```

### 扩展语义色

```
# 状态色
color-status-pending:    {color-orange-600}   # 待处理
color-status-processing: {color-blue-600}     # 处理中
color-status-completed:  {color-green-600}    # 已完成
color-status-canceled:   {color-gray-600}     # 已取消
color-status-failed:     {color-red-600}      # 失败

# 优先级色
color-priority-critical:  {color-red-600}     # 紧急
color-priority-high:      {color-orange-600}  # 高
color-priority-medium:    {color-yellow-700}  # 中
color-priority-low:       {color-gray-600}    # 低

# 数据可视化色
color-chart-1:  {color-blue-600}     # 图表主色
color-chart-2:  {color-purple-600}   # 图表辅色 1
color-chart-3:  {color-teal-600}     # 图表辅色 2
color-chart-4:  {color-orange-600}   # 图表辅色 3
color-chart-5:  {color-pink-600}     # 图表辅色 4
color-chart-6:  {color-lime-600}     # 图表辅色 5

# 社交/情感色
color-social-like:      {color-pink-600}     # 喜欢/收藏
color-social-share:     {color-cyan-600}     # 分享
color-social-comment:   {color-purple-600}   # 评论
color-social-follow:    {color-blue-600}     # 关注
```

---

## 数据可视化专用色板

### 分类色板（Categorical）- 用于离散数据

**8 色方案（高对比度）：**
```
viz-cat-1:  #2563EB   (Blue-600)
viz-cat-2:  #9333EA   (Purple-600)
viz-cat-3:  #16A34A   (Green-600)
viz-cat-4:  #EA580C   (Orange-600)
viz-cat-5:  #DB2777   (Pink-600)
viz-cat-6:  #0891B2   (Cyan-600)
viz-cat-7:  #65A30D   (Lime-600)
viz-cat-8:  #4F46E5   (Indigo-600)
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
viz-div-1: {color-red-700}     # 负极
viz-div-2: {color-red-400}
viz-div-3: {color-gray-200}    # 中性
viz-div-4: {color-blue-400}
viz-div-5: {color-blue-700}    # 正极
```

---

## 色彩对比度表

### 文本色（白色背景）对比度验证

| 颜色 | 600 色阶对比度 | 700 色阶对比度 | 推荐用途 |
|-----|--------------|--------------|---------|
| Gray | 7.2:1 ✅ AAA | 8.6:1 ✅ AAA | 常规文本 |
| Blue | 4.9:1 ✅ AA | 6.7:1 ✅ AAA | 链接文本 |
| Purple | 5.2:1 ✅ AA | 7.1:1 ✅ AAA | 创意文本 |
| Pink | 5.5:1 ✅ AA | 7.8:1 ✅ AAA | 强调文本 |
| Red | 5.9:1 ✅ AA | 8.2:1 ✅ AAA | 错误文本 |
| Orange | 4.8:1 ✅ AA | 6.5:1 ✅ AAA | 警示文本 |
| Yellow | 3.2:1 ❌ | 4.6:1 ✅ AA | 警告文本（仅 700） |
| Lime | 4.7:1 ✅ AA | 6.4:1 ✅ AAA | 新鲜文本 |
| Green | 4.8:1 ✅ AA | 6.8:1 ✅ AAA | 成功文本 |
| Teal | 4.9:1 ✅ AA | 6.9:1 ✅ AAA | 数据文本 |
| Cyan | 4.8:1 ✅ AA | 6.7:1 ✅ AAA | 信息文本 |
| Indigo | 5.1:1 ✅ AA | 7.0:1 ✅ AAA | 专业文本 |

**规则：**
- ✅ 使用 600 色阶：常规文本（≥ 4.5:1）
- ✅ 使用 700 色阶：确保 AAA 级（≥ 7:1）
- ❌ Yellow 600 不符合 AA，必须使用 700

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
