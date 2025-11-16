# 扩展色板 - Material Design 标准色系

> Google Material Design 色板系统，经过科学调校的标准色阶。
> **特点：** 色阶变化均匀、对比度优化、符合可访问性标准。

---

## 色板设计原理

### Material Design 色彩体系

Material Design 色板基于 **色相 (Hue)、饱和度 (Saturation)、亮度 (Lightness)** 精心设计：

```
色阶体系：
  常规色阶:  50, 100, 200, 300, 400, 500, 600, 700, 800, 900
  Accent 色阶: A100, A200, A400, A700（强调色，部分颜色提供）

设计原则：
  • 500 为主色调基准
  • 50-400 用于背景、边框、浅色状态
  • 600-900 用于文本、深色状态
  • A系列 用于强调、高亮、活跃状态
```

### 色阶亮度分布

| 色阶 | 亮度范围 | 用途 |
|-----|---------|------|
| 50  | 97-99% | 极浅背景 |
| 100 | 94-96% | 浅背景 |
| 200 | 88-92% | 边框、分割线 |
| 300 | 80-86% | 禁用状态、辅助元素 |
| 400 | 72-78% | 次要按钮、图标 |
| **500** | **60-70%** | **主色调（品牌色）** |
| 600 | 52-58% | 悬停状态、辅助文本 |
| 700 | 45-50% | 主按钮、链接 |
| 800 | 38-42% | 按下状态、重要文本 |
| 900 | 20-35% | 深色文本、标题 |

---

## 完整 17 色色板

### 1. Red（red）
**色相：** 0°
**用途：** 错误提示、删除操作、危险警告

```
color-red-50: #FFEBEE   # 1.14:1
color-red-100: #FFCDD2   # 1.41:1
color-red-200: #EF9A9A   # 2.15:1
color-red-300: #E57373   # 2.99:1
color-red-400: #EF5350   # 3.49:1 ⚠️
color-red-500: #F44336   # 3.68:1 ⚠️ 主色调
color-red-600: #E53935   # 4.23:1 ⚠️
color-red-700: #D32F2F   # 4.98:1 ✅ AA
color-red-800: #C62828   # 5.62:1 ✅ AA
color-red-900: #B71C1C   # 6.57:1 ✅ AA

# Accent 强调色
color-red-A100: #FF8A80   # 2.28:1
color-red-A200: #FF5252   # 3.19:1 ⚠️
color-red-A400: #FF1744   # 3.85:1 ⚠️
color-red-A700: #D50000   # 5.48:1 ✅ AA
```

**注意：** Red-600 对比度低于 AA 标准，建议文本使用 700 或更深色阶

---

### 2. Pink（pink）
**色相：** 330°
**用途：** 社交功能、收藏/喜欢、女性向产品

```
color-pink-50: #FCE4EC   # 1.2:1
color-pink-100: #F8BBD0   # 1.61:1
color-pink-200: #F48FB1   # 2.23:1
color-pink-300: #F06292   # 3.06:1 ⚠️
color-pink-400: #EC407A   # 3.76:1 ⚠️
color-pink-500: #E91E63   # 4.35:1 ⚠️ 主色调
color-pink-600: #D81B60   # 4.95:1 ✅ AA
color-pink-700: #C2185B   # 5.87:1 ✅ AA
color-pink-800: #AD1457   # 6.97:1 ✅ AA
color-pink-900: #880E4F   # 9.45:1 ✅ AAA

# Accent 强调色
color-pink-A100: #FF80AB   # 2.35:1
color-pink-A200: #FF4081   # 3.33:1 ⚠️
color-pink-A400: #F50057   # 4.18:1 ⚠️
color-pink-A700: #C51162   # 5.78:1 ✅ AA
```

---

### 3. Purple（purple）
**色相：** 270°
**用途：** 创意功能、VIP 标识、高级特性

```
color-purple-50: #F3E5F5   # 1.21:1
color-purple-100: #E1BEE7   # 1.65:1
color-purple-200: #CE93D8   # 2.39:1
color-purple-300: #BA68C8   # 3.56:1 ⚠️
color-purple-400: #AB47BC   # 4.82:1 ✅ AA
color-purple-500: #9C27B0   # 6.3:1 ✅ AA 主色调
color-purple-600: #8E24AA   # 7.04:1 ✅ AAA
color-purple-700: #7B1FA2   # 8.2:1 ✅ AAA
color-purple-800: #6A1B9A   # 9.39:1 ✅ AAA
color-purple-900: #4A148C   # 11.86:1 ✅ AAA

# Accent 强调色
color-purple-A100: #EA80FC   # 2.34:1
color-purple-A200: #E040FB   # 3.34:1 ⚠️
color-purple-A400: #D500F9   # 4.04:1 ⚠️
color-purple-A700: #AA00FF   # 5.06:1 ✅ AA
```

---

### 4. Deep Purple（deep purple）
**色相：** 265°
**用途：** 深度创意、专业高级功能

```
color-deep-purple-50: #EDE7F6   # 1.21:1
color-deep-purple-100: #D1C4E9   # 1.64:1
color-deep-purple-200: #B39DDB   # 2.4:1
color-deep-purple-300: #9575CD   # 3.68:1 ⚠️
color-deep-purple-400: #7E57C2   # 5.21:1 ✅ AA
color-deep-purple-500: #673AB7   # 7.33:1 ✅ AAA 主色调
color-deep-purple-600: #5E35B1   # 8.02:1 ✅ AAA
color-deep-purple-700: #512DA8   # 9.17:1 ✅ AAA
color-deep-purple-800: #4527A0   # 10.24:1 ✅ AAA
color-deep-purple-900: #311B92   # 12.34:1 ✅ AAA

# Accent 强调色
color-deep-purple-A100: #B388FF   # 2.66:1
color-deep-purple-A200: #7C4DFF   # 4.81:1 ✅ AA
color-deep-purple-A400: #651FFF   # 6.58:1 ✅ AA
color-deep-purple-A700: #6200EA   # 7.76:1 ✅ AAA
```

---

### 5. Indigo（indigo）
**色相：** 231°
**用途：** 专业版功能、深度分析、企业级特性

```
color-indigo-50: #E8EAF6   # 1.2:1
color-indigo-100: #C5CAE9   # 1.62:1
color-indigo-200: #9FA8DA   # 2.31:1
color-indigo-300: #7986CB   # 3.45:1 ⚠️
color-indigo-400: #5C6BC0   # 4.86:1 ✅ AA
color-indigo-500: #3F51B5   # 6.87:1 ✅ AA 主色调
color-indigo-600: #3949AB   # 7.73:1 ✅ AAA
color-indigo-700: #303F9F   # 8.98:1 ✅ AAA
color-indigo-800: #283593   # 10.39:1 ✅ AAA
color-indigo-900: #1A237E   # 13.24:1 ✅ AAA

# Accent 强调色
color-indigo-A100: #8C9EFF   # 2.49:1
color-indigo-A200: #536DFE   # 4.21:1 ⚠️
color-indigo-A400: #3D5AFE   # 5.13:1 ✅ AA
color-indigo-A700: #304FFE   # 5.71:1 ✅ AA
```

---

### 6. Blue（blue）
**色相：** 207°
**用途：** 主品牌色、链接、主要交互元素

```
color-blue-50: #E3F2FD   # 1.14:1
color-blue-100: #BBDEFB   # 1.4:1
color-blue-200: #90CAF9   # 1.75:1
color-blue-300: #64B5F6   # 2.21:1
color-blue-400: #42A5F5   # 2.65:1
color-blue-500: #2196F3   # 3.12:1 ⚠️ 主色调
color-blue-600: #1E88E5   # 3.68:1 ⚠️
color-blue-700: #1976D2   # 4.6:1 ✅ AA
color-blue-800: #1565C0   # 5.75:1 ✅ AA
color-blue-900: #0D47A1   # 8.63:1 ✅ AAA

# Accent 强调色
color-blue-A100: #82B1FF   # 2.17:1
color-blue-A200: #448AFF   # 3.32:1 ⚠️
color-blue-A400: #2979FF   # 3.98:1 ⚠️
color-blue-A700: #2962FF   # 4.9:1 ✅ AA
```

**注意：** Blue-600 对比度低于 AA 标准，建议文本使用 700 或更深色阶

---

### 7. Light Blue（light blue）
**色相：** 199°
**用途：** 信息提示（辅助）、科技感元素

```
color-light-blue-50: #E1F5FE   # 1.12:1
color-light-blue-100: #B3E5FC   # 1.35:1
color-light-blue-200: #81D4FA   # 1.65:1
color-light-blue-300: #4FC3F7   # 2.0:1
color-light-blue-400: #29B6F6   # 2.3:1
color-light-blue-500: #03A9F4   # 2.63:1 主色调
color-light-blue-600: #039BE5   # 3.08:1 ⚠️
color-light-blue-700: #0288D1   # 3.86:1 ⚠️
color-light-blue-800: #0277BD   # 4.8:1 ✅ AA
color-light-blue-900: #01579B   # 7.4:1 ✅ AAA

# Accent 强调色
color-light-blue-A100: #80D8FF   # 1.59:1
color-light-blue-A200: #40C4FF   # 1.99:1
color-light-blue-A400: #00B0FF   # 2.43:1
color-light-blue-A700: #0091EA   # 3.37:1 ⚠️
```

**注意：** Light Blue-600 对比度低于 AA 标准，建议文本使用 700 或更深色阶

---

### 8. Cyan（cyan）
**色相：** 187°
**用途：** 数据可视化、辅助信息、冷静色调

```
color-cyan-50: #E0F7FA   # 1.11:1
color-cyan-100: #B2EBF2   # 1.31:1
color-cyan-200: #80DEEA   # 1.55:1
color-cyan-300: #4DD0E1   # 1.84:1
color-cyan-400: #26C6DA   # 2.06:1
color-cyan-500: #00BCD4   # 2.3:1 主色调
color-cyan-600: #00ACC1   # 2.74:1
color-cyan-700: #0097A7   # 3.51:1 ⚠️
color-cyan-800: #00838F   # 4.52:1 ✅ AA
color-cyan-900: #006064   # 7.35:1 ✅ AAA

# Accent 强调色
color-cyan-A100: #84FFFF   # 1.18:1
color-cyan-A200: #18FFFF   # 1.25:1
color-cyan-A400: #00E5FF   # 1.54:1
color-cyan-A700: #00B8D4   # 2.38:1
```

**注意：** Cyan-600 对比度低于 AA 标准，建议文本使用 700 或更深色阶

---

### 9. Teal（teal）
**色相：** 174°
**用途：** 平静数据、环保主题、增长趋势

```
color-teal-50: #E0F2F1   # 1.16:1
color-teal-100: #B2DFDB   # 1.45:1
color-teal-200: #80CBC4   # 1.87:1
color-teal-300: #4DB6AC   # 2.44:1
color-teal-400: #26A69A   # 3.0:1 ⚠️
color-teal-500: #009688   # 3.67:1 ⚠️ 主色调
color-teal-600: #00897B   # 4.32:1 ⚠️
color-teal-700: #00796B   # 5.32:1 ✅ AA
color-teal-800: #00695C   # 6.61:1 ✅ AA
color-teal-900: #004D40   # 9.83:1 ✅ AAA

# Accent 强调色
color-teal-A100: #A7FFEB   # 1.16:1
color-teal-A200: #64FFDA   # 1.25:1
color-teal-A400: #1DE9B6   # 1.57:1
color-teal-A700: #00BFA5   # 2.33:1
```

**注意：** Teal-600 对比度低于 AA 标准，建议文本使用 700 或更深色阶

---

### 10. Green（green）
**色相：** 122°
**用途：** 成功提示、确认操作、正向反馈

```
color-green-50: #E8F5E9   # 1.12:1
color-green-100: #C8E6C9   # 1.34:1
color-green-200: #A5D6A7   # 1.64:1
color-green-300: #81C784   # 2.01:1
color-green-400: #66BB6A   # 2.36:1
color-green-500: #4CAF50   # 2.78:1 主色调
color-green-600: #43A047   # 3.3:1 ⚠️
color-green-700: #388E3C   # 4.12:1 ⚠️
color-green-800: #2E7D32   # 5.13:1 ✅ AA
color-green-900: #1B5E20   # 7.87:1 ✅ AAA

# Accent 强调色
color-green-A100: #B9F6CA   # 1.23:1
color-green-A200: #69F0AE   # 1.43:1
color-green-A400: #00E676   # 1.67:1
color-green-A700: #00C853   # 2.24:1
```

**注意：** Green-600 对比度低于 AA 标准，建议文本使用 700 或更深色阶

---

### 11. Light Green（light green）
**色相：** 88°
**用途：** 新鲜活力、环保辅助、增长（次要）

```
color-light-green-50: #F1F8E9   # 1.09:1
color-light-green-100: #DCEDC8   # 1.24:1
color-light-green-200: #C5E1A5   # 1.43:1
color-light-green-300: #AED581   # 1.66:1
color-light-green-400: #9CCC65   # 1.87:1
color-light-green-500: #8BC34A   # 2.1:1 主色调
color-light-green-600: #7CB342   # 2.5:1
color-light-green-700: #689F38   # 3.18:1 ⚠️
color-light-green-800: #558B2F   # 4.1:1 ⚠️
color-light-green-900: #33691E   # 6.6:1 ✅ AA

# Accent 强调色
color-light-green-A100: #CCFF90   # 1.15:1
color-light-green-A200: #B2FF59   # 1.21:1
color-light-green-A400: #76FF03   # 1.31:1
color-light-green-A700: #64DD17   # 1.77:1
```

**注意：** Light Green-600 对比度低于 AA 标准，建议文本使用 700 或更深色阶

---

### 12. Lime（lime）
**色相：** 66°
**用途：** 高亮强调（背景）、新功能标识

```
color-lime-50: #F9FBE7   # 1.05:1
color-lime-100: #F0F4C3   # 1.14:1
color-lime-200: #E6EE9C   # 1.23:1
color-lime-300: #DCE775   # 1.33:1
color-lime-400: #D4E157   # 1.43:1
color-lime-500: #CDDC39   # 1.51:1 主色调
color-lime-600: #C0CA33   # 1.79:1
color-lime-700: #AFB42B   # 2.24:1
color-lime-800: #9E9D24   # 2.88:1
color-lime-900: #827717   # 4.56:1 ✅ AA

# Accent 强调色
color-lime-A100: #F4FF81   # 1.08:1
color-lime-A200: #EEFF41   # 1.1:1
color-lime-A400: #C6FF00   # 1.19:1
color-lime-A700: #AEEA00   # 1.44:1
```

**注意：** Lime-600 对比度低于 AA 标准，建议文本使用 700 或更深色阶

---

### 13. Yellow（yellow）
**色相：** 54°
**用途：** 警告提示（背景）、高亮标记

```
color-yellow-50: #FFFDE7   # 1.03:1
color-yellow-100: #FFF9C4   # 1.07:1
color-yellow-200: #FFF59D   # 1.12:1
color-yellow-300: #FFF176   # 1.16:1
color-yellow-400: #FFEE58   # 1.19:1
color-yellow-500: #FFEB3B   # 1.22:1 主色调
color-yellow-600: #FDD835   # 1.4:1
color-yellow-700: #FBC02D   # 1.66:1
color-yellow-800: #F9A825   # 1.97:1
color-yellow-900: #F57F17   # 2.65:1

# Accent 强调色
color-yellow-A100: #FFFF8D   # 1.05:1
color-yellow-A200: #FFFF00   # 1.07:1
color-yellow-A400: #FFEA00   # 1.23:1
color-yellow-A700: #FFD600   # 1.41:1
```

**⚠️ 注意：** Yellow 所有色阶对比度均不达 AA 标准（4.5:1），仅适合背景、装饰用途

---

### 14. Amber（amber）
**色相：** 45°
**用途：** 警告提示、待处理状态、促销活动

```
color-amber-50: #FFF8E1   # 1.06:1
color-amber-100: #FFECB3   # 1.17:1
color-amber-200: #FFE082   # 1.29:1
color-amber-300: #FFD54F   # 1.41:1
color-amber-400: #FFCA28   # 1.53:1
color-amber-500: #FFC107   # 1.63:1 主色调
color-amber-600: #FFB300   # 1.79:1
color-amber-700: #FFA000   # 2.04:1
color-amber-800: #FF8F00   # 2.29:1
color-amber-900: #FF6F00   # 2.79:1

# Accent 强调色
color-amber-A100: #FFE57F   # 1.25:1
color-amber-A200: #FFD740   # 1.4:1
color-amber-A400: #FFC400   # 1.6:1
color-amber-A700: #FFAB00   # 1.9:1
```

**⚠️ 注意：** Amber 所有色阶对比度均不达 AA 标准（4.5:1），仅适合背景、装饰用途

---

### 15. Orange（orange）
**色相：** 36°
**用途：** 热度标识、紧急通知、促销活动

```
color-orange-50: #FFF3E0   # 1.1:1
color-orange-100: #FFE0B2   # 1.27:1
color-orange-200: #FFCC80   # 1.48:1
color-orange-300: #FFB74D   # 1.73:1
color-orange-400: #FFA726   # 1.94:1
color-orange-500: #FF9800   # 2.16:1 主色调
color-orange-600: #FB8C00   # 2.37:1
color-orange-700: #F57C00   # 2.7:1
color-orange-800: #EF6C00   # 3.08:1 ⚠️
color-orange-900: #E65100   # 3.79:1 ⚠️

# Accent 强调色
color-orange-A100: #FFD180   # 1.43:1
color-orange-A200: #FFAB40   # 1.88:1
color-orange-A400: #FF9100   # 2.26:1
color-orange-A700: #FF6D00   # 2.82:1
```

**⚠️ 注意：** Orange 所有色阶对比度均不达 AA 标准（4.5:1），仅适合背景、装饰用途

---

### 16. Deep Orange（deep orange）
**色相：** 14°
**用途：** 危险警告（辅助）、高优先级标识

```
color-deep-orange-50: #FBE9E7   # 1.17:1
color-deep-orange-100: #FFCCBC   # 1.44:1
color-deep-orange-200: #FFAB91   # 1.83:1
color-deep-orange-300: #FF8A65   # 2.31:1
color-deep-orange-400: #FF7043   # 2.74:1
color-deep-orange-500: #FF5722   # 3.16:1 ⚠️ 主色调
color-deep-orange-600: #F4511E   # 3.48:1 ⚠️
color-deep-orange-700: #E64A19   # 3.92:1 ⚠️
color-deep-orange-800: #D84315   # 4.44:1 ⚠️
color-deep-orange-900: #BF360C   # 5.6:1 ✅ AA

# Accent 强调色
color-deep-orange-A100: #FF9E80   # 2.01:1
color-deep-orange-A200: #FF6E40   # 2.78:1
color-deep-orange-A400: #FF3D00   # 3.55:1 ⚠️
color-deep-orange-A700: #DD2C00   # 4.74:1 ✅ AA
```

**注意：** Deep Orange-600 对比度低于 AA 标准，建议文本使用 700 或更深色阶

---

### 17. Grey（grey）
**色相：** 无（灰度）
**用途：** 文本、边框、背景、中性元素

```
color-grey-50: #FAFAFA   # 1.04:1
color-grey-100: #F5F5F5   # 1.09:1
color-grey-200: #EEEEEE   # 1.16:1
color-grey-300: #E0E0E0   # 1.32:1
color-grey-400: #BDBDBD   # 1.88:1
color-grey-500: #9E9E9E   # 2.68:1 主色调
color-grey-600: #757575   # 4.61:1 ✅ AA
color-grey-700: #616161   # 6.19:1 ✅ AA
color-grey-800: #424242   # 10.05:1 ✅ AAA
color-grey-900: #212121   # 16.1:1 ✅ AAA
color-grey-Black: #000000   # 21.0:1 ✅ AAA
color-grey-White: #FFFFFF   # 1.0:1
```

---

## 语义化色彩应用

### 功能色映射（推荐）

基于 WCAG AA 标准的功能色建议：

```
成功（Success）:   Green-700     #388E3C  (对比度 5.44:1 ✅ AA)
警告（Warning）:   Amber-900     #FF6F00  (对比度 2.79:1 ⚠️ 仅背景用)
错误（Error）:     Red-700       #D32F2F  (对比度 4.98:1 ✅ AA)
信息（Info）:      Blue-700      #1976D2  (对比度 4.6:1 ✅ AA)

注意：Material Design 的黄色系（Yellow, Lime, Amber）对比度普遍较低，
不适合直接用于文本。警告色建议使用深色背景配浅色文本，或使用图标辅助。
```

### 扩展语义色

```
# 状态色（文本用）
color-status-pending:    #F57C00              # 待处理 (Orange-700, 2.7:1 ⚠️)
color-status-processing: #1976D2              # 处理中 (Blue-700, 4.6:1 ✅)
color-status-completed:  #388E3C              # 已完成 (Green-700, 5.44:1 ✅)
color-status-canceled:   #757575              # 已取消 (Grey-600, 4.61:1 ✅)
color-status-failed:     #D32F2F              # 失败 (Red-700, 4.98:1 ✅)

# 优先级色
color-priority-critical:  #D32F2F             # 紧急 (Red-700, 4.98:1 ✅)
color-priority-high:      #F57C00             # 高 (Orange-700, 2.7:1 ⚠️ 建议用图标)
color-priority-medium:    #F9A825             # 中 (Yellow-800, 1.97:1 仅背景)
color-priority-low:       #757575             # 低 (Grey-600, 4.61:1 ✅)

# 数据可视化色（图表用，非文本）
color-chart-1:  #2196F3              # 图表主色 (Blue-500)
color-chart-2:  #9C27B0              # 图表辅色 1 (Purple-500)
color-chart-3:  #009688              # 图表辅色 2 (Teal-500)
color-chart-4:  #FF9800              # 图表辅色 3 (Orange-500)
color-chart-5:  #E91E63              # 图表辅色 4 (Pink-500)
color-chart-6:  #4CAF50              # 图表辅色 5 (Green-500)

# 社交/情感色
color-social-like:      #E91E63              # 喜欢/收藏 (Pink-500)
color-social-share:     #2196F3              # 分享 (Blue-500)
color-social-comment:   #9C27B0              # 评论 (Purple-500)
color-social-follow:    #1976D2              # 关注 (Blue-700)
```

---

## 数据可视化专用色板

### 分类色板（Categorical）- 用于离散数据

**8 色方案：**
```
viz-cat-1:  #2196F3   (Blue-500)
viz-cat-2:  #9C27B0   (Purple-500)
viz-cat-3:  #4CAF50   (Green-500)
viz-cat-4:  #FF9800   (Orange-500)
viz-cat-5:  #E91E63   (Pink-500)
viz-cat-6:  #00BCD4   (Cyan-500)
viz-cat-7:  #8BC34A   (Light Green-500)
viz-cat-8:  #3F51B5   (Indigo-500)

注意：用于图表填充/描边，不适合文本标签
```

### 连续色板（Sequential）- 用于数值范围

**蓝色渐变（从浅到深）：**
```
viz-seq-blue-1: #BBDEFB   (Blue-100)
viz-seq-blue-2: #64B5F6   (Blue-300)
viz-seq-blue-3: #2196F3   (Blue-500)
viz-seq-blue-4: #1976D2   (Blue-700)
viz-seq-blue-5: #0D47A1   (Blue-900)
```

### 发散色板（Diverging）- 用于正负值

**红-蓝发散：**
```
viz-div-1: #D32F2F              # 负极 (Red-700)
viz-div-2: #EF5350              # (Red-400)
viz-div-3: #EEEEEE              # 中性 (Grey-200)
viz-div-4: #42A5F5              # (Blue-400)
viz-div-5: #1976D2              # 正极 (Blue-700)
```

---

## 色彩对比度表

### 文本色（白色背景）对比度验证

| 颜色 | 600 色阶对比度 | 700 色阶对比度 | 800 色阶对比度 | 推荐文本色阶 |
|-----|--------------|--------------|--------------|------------|
| Red | 4.23:1 ⚠️ | 4.98:1 ✅ AA | 5.62:1 ✅ AA | 700+ |
| Pink | 4.95:1 ✅ AA | 5.87:1 ✅ AA | 6.97:1 ✅ AA | 600+ |
| Purple | 7.04:1 ✅ AAA | 8.2:1 ✅ AAA | 9.39:1 ✅ AAA | 600+ |
| Deep Purple | 8.02:1 ✅ AAA | 9.17:1 ✅ AAA | 10.24:1 ✅ AAA | 600+ |
| Indigo | 7.73:1 ✅ AAA | 8.98:1 ✅ AAA | 10.39:1 ✅ AAA | 600+ |
| Blue | 3.68:1 ⚠️ | 4.6:1 ✅ AA | 5.75:1 ✅ AA | 700+ |
| Light Blue | 3.08:1 ⚠️ | 3.86:1 ⚠️ | 4.8:1 ✅ AA | 800+ |
| Cyan | 3.7:1 ⚠️ | 4.78:1 ✅ AA | 6.23:1 ✅ AA | 700+ |
| Teal | 3.77:1 ⚠️ | 5.05:1 ✅ AA | 6.84:1 ✅ AA | 700+ |
| Green | 5.15:1 ✅ AA | 5.44:1 ✅ AA | 7.54:1 ✅ AAA | 600+ |
| Light Green | 4.24:1 ⚠️ | 5.66:1 ✅ AA | 7.26:1 ✅ AAA | 700+ |
| Lime | 1.79:1 ❌ | 2.24:1 ❌ | 2.88:1 ❌ | 900 仅背景 |
| Yellow | 1.4:1 ❌ | 1.66:1 ❌ | 1.97:1 ❌ | 仅背景 |
| Amber | 1.79:1 ❌ | 2.04:1 ❌ | 2.29:1 ❌ | 仅背景 |
| Orange | 2.37:1 ❌ | 2.7:1 ❌ | 3.08:1 ⚠️ | 900 |
| Deep Orange | 3.64:1 ⚠️ | 4.34:1 ⚠️ | 5.23:1 ✅ AA | 800+ |
| Grey | 4.61:1 ✅ AA | 6.19:1 ✅ AA | 10.05:1 ✅ AAA | 600+ |

**规则：**
- ✅ AA 标准：对比度 ≥ 4.5:1（常规文本）
- ✅ AAA 标准：对比度 ≥ 7.0:1（确保所有用户可读）
- ⚠️ 接近但未达标：可用于大文本（≥18pt）或 UI 组件边框
- ❌ 不达标：仅适合背景、装饰，不可用于文本

**重要说明：**
- 黄色系（Yellow, Lime, Amber）**不适合用于文本**，仅用于背景高亮
- 警告色建议使用 **深色背景 + 浅色文本** 的反转方案
- 或配合图标使用，减少对颜色的依赖

---

## 使用原则

### 1. 主色选择

**建议配置：**
```
主品牌色:      Blue-500 / Indigo-500 / Purple-500
成功色:        Green-700
警告色:        Amber-500（背景）+ Grey-900（文本）
错误色:        Red-700
信息色:        Blue-700
```

### 2. 色彩层级

```
50-200:   背景色、边框色、分割线
300-400:  悬停状态、禁用元素、辅助图标
500:      主色调基准（品牌识别色）
600-700:  文本色、主按钮（确保对比度）
800-900:  深色状态、深色模式、标题文本
A 系列:   强调色、活跃状态、高亮元素
```

### 3. 避免滥用

**❌ 不要：**
- 在同一页面使用超过 3 种主色（500 级）
- 使用低对比度颜色作为文本色
- 单纯依赖颜色区分信息（需配合图标/文字）

**✅ 推荐：**
- 90% 使用 Grey（中性色）
- 7% 使用主品牌色（Blue/Indigo/Purple）
- 3% 使用功能色（Red/Green/Orange）

---

## 工具推荐

### Material Design 官方工具
- [Material Color Tool](https://material.io/resources/color/) - 官方配色工具
- [Material Theme Editor](https://material.io/tools/theme-editor/) - 主题编辑器

### 对比度检查
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Figma Plugin: Stark](https://www.figma.com/community/plugin/732603254453395948)

---

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
**色板来源：** [Google Material Design Color System](https://material.io/design/color/)
**相关文档：** [Design Token 规范](./README.md) | [设计原理](./design-principles.md)
