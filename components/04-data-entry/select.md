# Select 选择器

> 下拉选择组件，用于从一组预定义选项中进行单选或多选，支持搜索、分组、远程加载等功能。

---

## 1. 何时使用

### 适用场景

✅ **选项较多** - 5个以上选项，使用下拉节省空间
✅ **单选/多选** - 从列表中选择一个或多个选项
✅ **可搜索** - 选项众多时，支持搜索过滤
✅ **分组选项** - 选项需要分类展示
✅ **远程加载** - 选项需要从服务器动态获取

### 不要使用的场景

❌ **选项少于5个** - 应使用 Radio 或 Checkbox
❌ **日期时间选择** - 应使用 DatePicker/TimePicker
❌ **树形结构** - 应使用 TreeSelect
❌ **级联选择** - 应使用 Cascader
❌ **颜色选择** - 应使用 ColorPicker

### 替代方案

| 场景 | 推荐组件 | 说明 |
|------|---------|------|
| 2-5个选项单选 | `Radio` | 选项可见，操作更快 |
| 2-5个选项多选 | `Checkbox` | 选项可见，操作更快 |
| 树形选择 | `TreeSelect` | 树形结构数据 |
| 级联选择 | `Cascader` | 省市区等级联数据 |
| 日期选择 | `DatePicker` | 日期时间选择 |

---

## 2. 解剖结构（Anatomy）

### 组件拆解

#### 选择器（收起状态）

```
┌─────────────────────────────────────────────┐
│  ┌─────────────────────────────────────┐   │
│  │ 🔍 ┊ Selected Item    │  × │  ⌄  │   │
│  │     Placeholder/Value │ Clear│Arrow│   │
│  └─────────────────────────────────────┘   │
└─────────────────────────────────────────────┘
   ↑    ↑                  ↑   ↑    ↑
   Prefix  Text Area      Clear  Suffix
```

#### 下拉面板（展开状态）

```
┌─────────────────────────────────────────────┐
│ Select Input (同上)                          │
└─────────────────────────────────────────────┘
     ↓ 4px
┌─────────────────────────────────────────────┐
│ ┌─ Search Input (可选) ─────────────────┐   │
│ │ 🔍 Search...                          │   │
│ └───────────────────────────────────────┘   │
│ ┌─ Option List ─────────────────────────┐   │
│ │ ✓ Option 1 (已选中)                   │   │ ← Hover
│ │   Option 2                            │   │
│ │ ┌─ Group Title ─────────────────────┐ │   │
│ │ │   Option 3                        │ │   │
│ │ │   Option 4 (禁用)                 │ │   │
│ │ └───────────────────────────────────┘ │   │
│ │   No Data (无匹配)                    │   │
│ └───────────────────────────────────────┘   │
└─────────────────────────────────────────────┘
```

### 元素说明

#### Select Input 元素

| 元素 | 名称 | 必需 | 说明 |
|------|------|------|------|
| **Container** | 容器 | ✅ | 输入框外层容器 |
| **Prefix Icon** | 前缀图标 | ⚪ 可选 | 左侧图标（如搜索图标） |
| **Text Area** | 文本区域 | ✅ | 显示 Placeholder 或已选值 |
| **Clear Icon** | 清除图标 | ⚪ 可选 | 清除已选值（Hover 显示） |
| **Suffix Arrow** | 下拉箭头 | ✅ | 展开/收起指示器 |
| **Tag Area** | 标签区域 | ⚪ 可选 | 多选时显示已选标签 |

#### Dropdown 元素

| 元素 | 名称 | 必需 | 说明 |
|------|------|------|------|
| **Dropdown Container** | 下拉容器 | ✅ | 下拉面板容器（带阴影） |
| **Search Input** | 搜索框 | ⚪ 可选 | 搜索过滤选项 |
| **Option List** | 选项列表 | ✅ | 滚动列表容器 |
| **Option Item** | 选项 | ✅ | 单个选项 |
| **Checkbox** | 复选框 | ⚪ 可选 | 多选时的复选框 |
| **Checkmark** | 对勾图标 | ⚪ 可选 | 单选时已选标记 |
| **Group Title** | 分组标题 | ⚪ 可选 | 选项分组标题 |
| **Empty State** | 空状态 | ⚪ 可选 | 无选项/无匹配时显示 |

### 层级关系

```
Select (Component)
├─ Select Input (Trigger)
│  ├─ Prefix Icon (Optional)
│  ├─ Text/Tags Area
│  │  ├─ Placeholder Text
│  │  ├─ Single Value
│  │  └─ Multiple Tags (Multiple Mode)
│  ├─ Clear Icon (Optional)
│  └─ Arrow Icon
└─ Dropdown Panel
   ├─ Search Input (Optional)
   └─ Option List
      ├─ Option Group 1
      │  ├─ Group Title
      │  ├─ Option 1
      │  └─ Option 2
      ├─ Option Group 2
      │  └─ ...
      └─ Empty State (No Data)
```

---

## 3. 尺寸与间距

### 3.1 三种尺寸规格

| 尺寸 | 高度 | 水平内边距 | 字号 | 行高 | 图标尺寸 | 使用场景 |
|------|------|-----------|------|------|---------|---------|
| **Large** | `40px` | `12px` | `16px` | `24px` | `20px` | 移动端、强调输入 |
| **Middle** | `32px` | `12px` | `14px` | `22px` | `16px` | 默认尺寸（最常用） |
| **Small** | `24px` | `8px` | `12px` | `20px` | `14px` | 紧凑布局、表格内 |

### 3.2 Select Input 间距

#### 内部间距

```
Large (40px):
┌─12px─┬────┬─8px─┬──────────┬─8px─┬────┬─8px─┬────┬─12px─┐
│      │ 🔍 │     │ Selected │     │ ×  │     │ ⌄  │      │
└──────┴────┴─────┴──────────┴─────┴────┴─────┴────┴──────┘

Middle (32px):
┌─12px─┬────┬─8px─┬──────────┬─8px─┬────┬─4px─┬────┬─12px─┐
│      │ 🔍 │     │ Selected │     │ ×  │     │ ⌄  │      │
└──────┴────┴─────┴──────────┴─────┴────┴─────┴────┴──────┘

Small (24px):
┌─8px──┬────┬─4px─┬──────────┬─4px─┬────┬─4px─┬────┬─8px──┐
│      │ 🔍 │     │ Selected │     │ ×  │     │ ⌄  │      │
└──────┴────┴─────┴──────────┴─────┴────┴─────┴────┴──────┘
```

| 间距类型 | Large | Middle | Small | Token |
|---------|-------|--------|-------|-------|
| 左右内边距 | `12px` | `12px` | `8px` | `spacing-3` / `spacing-2` |
| Prefix-Text 间距 | `8px` | `8px` | `4px` | `spacing-2` / `spacing-1` |
| Text-Clear 间距 | `8px` | `8px` | `4px` | `spacing-2` / `spacing-1` |
| Clear-Arrow 间距 | `8px` | `4px` | `4px` | `spacing-2` / `spacing-1` |

### 3.3 Dropdown 间距

#### Dropdown 与 Input 间距

```
[Select Input]
     ↓ 4px
┌─ Dropdown Panel ─┐
│ ...              │
└──────────────────┘
```

| 属性 | 值 | Token |
|------|-----|-------|
| Input-Dropdown 间距 | `4px` | `spacing-1` |
| Dropdown 最大高度 | `256px` (8个选项) | - |
| Dropdown 最小宽度 | 与 Input 相同 | - |

#### Option 内部间距

```
Large Option (40px):
┌─12px─┬────┬─8px─┬────────────────────┬─12px─┐
│      │ ✓  │     │ Option Text        │      │
└──────┴────┴─────┴────────────────────┴──────┘

Middle Option (32px):
┌─12px─┬────┬─8px─┬────────────────────┬─12px─┐
│      │ ✓  │     │ Option Text        │      │
└──────┴────┴─────┴────────────────────┴──────┘

Small Option (24px):
┌─8px──┬────┬─4px─┬────────────────────┬─8px──┐
│      │ ✓  │     │ Option Text        │      │
└──────┴────┴─────┴────────────────────┴──────┘
```

| 属性 | Large | Middle | Small | Token |
|------|-------|--------|-------|-------|
| Option 高度 | `40px` | `32px` | `24px` | - |
| 水平内边距 | `12px` | `12px` | `8px` | `spacing-3` / `spacing-2` |
| Checkmark-Text 间距 | `8px` | `8px` | `4px` | `spacing-2` / `spacing-1` |

#### 分组间距

```
┌─ Option Group ────────────────┐
│ Group Title (加粗，灰色背景)   │ ← 32px 高度
│   Option 1                    │
│   Option 2                    │
└───────────────────────────────┘
     ↓ 8px (分组间距)
┌─ Option Group ────────────────┐
│ Group Title                   │
│   Option 3                    │
└───────────────────────────────┘
```

| 属性 | 值 | Token |
|------|-----|-------|
| Group Title 高度 | `32px` | - |
| Group Title 内边距 | `8px 12px` | `spacing-2` + `spacing-3` |
| Group 之间间距 | `8px` | `spacing-2` |

### 3.4 多选标签（Tags）间距

```
Multiple Select (已选 3 个):
┌─────────────────────────────────────────┐
│ [Tag1 ×] [Tag2 ×] [Tag3 ×]  ⌄         │
│  ↑ 4px间距                              │
└─────────────────────────────────────────┘
```

| 属性 | 值 | Token |
|------|-----|-------|
| Tag 之间间距 | `4px` | `spacing-1` |
| Tag 高度 | `24px` (Middle 时) | - |
| Tag 内边距 | `0 8px` | `spacing-2` |
| Tag-Arrow 间距 | `8px` | `spacing-2` |

---

## 4. 视觉规范

### 4.1 颜色规范

#### Select Input 颜色

| 状态 | 背景色 | 边框色 | 文字色 | Token |
|------|--------|--------|--------|-------|
| **Default** | `#FFFFFF` | `#D9D9D9` (Grey 400) | `#000000` | `background-primary` + `border-default` |
| **Hover** | `#FFFFFF` | `#1976D2` (Blue 600) | `#000000` | - + `border-primary` |
| **Focused** | `#FFFFFF` | `#1976D2` | `#000000` | - + `border-primary` |
| **Disabled** | `#F5F5F5` (Grey 100) | `#E0E0E0` (Grey 300) | `#9E9E9E` (Grey 500) | `background-disabled` + `border-disabled` |
| **Error** | `#FFFFFF` | `#D32F2F` (Red 700) | `#000000` | - + `error-primary` |
| **Placeholder** | - | - | `#9E9E9E` (Grey 500) | `text-placeholder` |

#### Dropdown 颜色

| 元素 | 背景色 | 边框 | 阴影 | Token |
|------|--------|------|------|-------|
| **Dropdown Container** | `#FFFFFF` | `1px #F0F0F0` | `0 4px 12px rgba(0,0,0,0.08)` | `background-primary` + `shadow-lg` |
| **Option Default** | 透明 | 无 | 无 | - |
| **Option Hover** | `#F5F5F5` (Grey 100) | 无 | 无 | `background-hover` |
| **Option Selected** | `#E3F2FD` (Blue 50) | 无 | 无 | `background-selected` |
| **Option Disabled** | 透明 | 无 | 无 | - |
| **Group Title** | `#FAFAFA` (Grey 50) | 无 | 无 | `background-secondary` |

#### 图标颜色

| 元素 | 颜色 | Token | 说明 |
|------|------|-------|------|
| Arrow Icon (Default) | `#9E9E9E` (Grey 500) | `icon-secondary` | 默认灰色 |
| Arrow Icon (Open) | `#1976D2` (Blue 600) | `icon-primary` | 展开时变蓝 |
| Clear Icon | `#9E9E9E` (Grey 500) | `icon-secondary` | Hover 时显示 |
| Search Icon | `#9E9E9E` (Grey 500) | `icon-secondary` | 搜索框图标 |
| Checkmark (Selected) | `#1976D2` (Blue 600) | `icon-primary` | 已选对勾 |

### 4.2 文字规范

#### Select Input 文字

| 尺寸 | 字号 | 行高 | 字重 | Token |
|------|------|------|------|-------|
| Large | `16px` | `24px` | `400 Regular` | `font-size-lg` |
| Middle | `14px` | `22px` | `400 Regular` | `font-size-base` |
| Small | `12px` | `20px` | `400 Regular` | `font-size-sm` |

#### Option 文字

| 元素 | 字号 | 行高 | 字重 | 颜色 | Token |
|------|------|------|------|------|-------|
| **Option Text** | `14px` | `22px` | `400 Regular` | `#000000` | `font-size-base` |
| **Option (Disabled)** | `14px` | `22px` | `400 Regular` | `#9E9E9E` | `text-disabled` |
| **Group Title** | `12px` | `20px` | `500 Medium` | `#757575` | `font-size-sm` + `font-weight-medium` |
| **Empty Text** | `14px` | `22px` | `400 Regular` | `#9E9E9E` | `text-tertiary` |

#### 文案规范

| 规则 | 说明 | 示例 |
|------|------|------|
| Placeholder | 提示用户操作 | ✅ 请选择 ❌ 选择一个选项 |
| Option 文字 | 简洁明确，2-20 字符 | ✅ 北京市 ❌ 请选择北京市 |
| Group Title | 分类名称，2-10 字符 | ✅ 热门城市 ❌ 以下是热门城市 |
| Empty Text | 无数据提示 | "无匹配选项" / "暂无数据" |

### 4.3 边框与圆角

#### 边框

| 元素 | 边框宽度 | 边框样式 | Token |
|------|---------|---------|-------|
| Select Input | `1px` | `solid` | `borderWidth-base` |
| Dropdown | `1px` | `solid` | `borderWidth-base` |

#### 圆角

| 元素 | 圆角 | Token |
|------|------|-------|
| Select Input | `4px` | `borderRadius-base` |
| Dropdown | `4px` | `borderRadius-base` |
| Tag | `2px` | `borderRadius-sm` |

### 4.4 阴影

| 元素 | 阴影 | Token | 说明 |
|------|------|-------|------|
| Dropdown | `0 4px 12px rgba(0,0,0,0.08)` | `shadow-lg` | 下拉面板阴影 |
| Dropdown (Hover) | `0 6px 16px rgba(0,0,0,0.12)` | `shadow-xl` | 可选增强效果 |

---

## 5. 组件状态（States）

### 5.1 状态总览

#### Select Input 状态

| 状态 | 触发条件 | 视觉变化 | 交互能力 |
|------|---------|---------|---------|
| **Default** | 默认 | 灰色边框 | ✅ 可点击 |
| **Hover** | 鼠标悬停 | 边框变蓝 | ✅ 可点击 |
| **Focused (Open)** | 点击展开 | 边框蓝色，箭头旋转180° | ✅ 可选择选项 |
| **Disabled** | `disabled={true}` | 灰色背景，不可交互 | ❌ 不可点击 |
| **Error** | 验证失败 | 红色边框 | ✅ 可点击 |
| **Loading** | 加载选项 | 显示 Loading 图标 | ⚪ 部分功能 |

#### Option 状态

| 状态 | 视觉变化 | 说明 |
|------|---------|------|
| **Default** | 透明背景 | 默认选项 |
| **Hover** | 灰色背景 (#F5F5F5) | 鼠标悬停 |
| **Selected** | 蓝色背景 (#E3F2FD) + ✓ 对勾 | 已选中 |
| **Disabled** | 灰色文字，不可点击 | 禁用选项 |

### 5.2 交互行为

#### 展开/收起

```
点击 Input → 展开 Dropdown
  ├─ 箭头图标旋转 180°
  ├─ 边框变蓝
  └─ 显示 Dropdown (带动画)

点击选项 → 收起 Dropdown (单选)
  ├─ 更新 Input 显示值
  ├─ 箭头恢复 0°
  └─ 隐藏 Dropdown (带动画)

点击外部 → 收起 Dropdown
```

#### 搜索过滤

```
输入搜索词 → 实时过滤选项
  ├─ 高亮匹配文字
  ├─ 隐藏不匹配选项
  └─ 显示 "无匹配" (无结果时)

清空搜索 → 恢复所有选项
```

#### 多选操作

```
点击选项 → 添加/移除选中
  ├─ 不收起 Dropdown
  ├─ 添加/移除 Tag
  ├─ 显示/隐藏 Checkmark
  └─ 更新选中计数

点击 Tag × → 移除选中
  ├─ 移除对应 Tag
  └─ 更新 Dropdown 选中状态

点击 Clear × → 清空所有选中
```

### 5.3 键盘操作

| 按键 | 行为 | 说明 |
|------|------|------|
| `Tab` | 聚焦到 Select | 键盘导航 |
| `Enter` / `Space` | 展开/收起 Dropdown | 激活选择器 |
| `↑` / `↓` | 高亮上/下选项 | 键盘选择 |
| `Enter` | 选中当前高亮选项 | 确认选择 |
| `Esc` | 收起 Dropdown | 取消操作 |
| `Backspace` | 删除最后一个 Tag | 多选模式 |
| `A-Z` | 跳转到首字母匹配选项 | 快速定位 |

### 5.4 动画效果

| 动画 | 时长 | 缓动函数 | Token |
|------|------|---------|-------|
| Dropdown 展开/收起 | `200ms` | `cubic-bezier(0.4, 0, 0.2, 1)` | `duration-short` |
| 箭头旋转 | `200ms` | `cubic-bezier(0.4, 0, 0.2, 1)` | `duration-short` |
| Option Hover | `100ms` | `cubic-bezier(0.4, 0, 0.2, 1)` | `duration-fastest` |
| Tag 添加/删除 | `150ms` | `cubic-bezier(0.4, 0, 0.2, 1)` | `duration-fast` |

---

## 6. 组件变体（Figma Variants）

### 6.1 Variants 属性配置

| 属性名 | 属性值 | 默认值 | 说明 |
|--------|--------|--------|------|
| **Mode** | Single / Multiple / Tags | `Single` | 选择模式 |
| **Size** | Large / Middle / Small | `Middle` | 尺寸 |
| **State** | Default / Hover / Focused / Disabled / Error | `Default` | 状态 |
| **Searchable** | True / False | `False` | 是否可搜索 |
| **Clearable** | True / False | `False` | 是否可清除 |
| **Loading** | True / False | `False` | 加载状态 |

### 6.2 Variants 命名规范

```
格式：Mode / Size / State

示例：
- Single / Middle / Default
- Multiple / Large / Focused
- Tags / Small / Disabled
```

### 6.3 变体决策树

```
选择 Mode
  ├─ Single:    单选（默认）
  ├─ Multiple:  多选（显示复选框）
  └─ Tags:      多选标签模式

选择 Size
  ├─ Large:     移动端、强调输入
  ├─ Middle:    默认（90% 场景）
  └─ Small:     紧凑布局

选择功能
  ├─ Searchable:  选项多（>10个）
  ├─ Clearable:   允许清空选择
  └─ Loading:     远程加载数据
```

---

## 7. Figma Auto Layout 配置

### 7.1 Select Input 设置

```
Frame 名称: Select/Single/Middle/Default

Auto Layout:
├─ Direction: Horizontal (→)
├─ Spacing: 8px (元素间距)
├─ Padding: 12px (左右)
├─ Alignment:
│  ├─ Horizontal: Space between
│  └─ Vertical: Center
└─ Resizing:
   ├─ Horizontal: Fill container (默认) / Fixed
   └─ Vertical: Fixed (32px)

子元素:
├─ Prefix Icon (Optional, 16×16px)
├─ Text/Tags Area (Fill)
├─ Clear Icon (Optional, 16×16px)
└─ Arrow Icon (16×16px, Rotate 180° when open)
```

### 7.2 Dropdown 设置

```
Frame 名称: Select Dropdown

Auto Layout:
├─ Direction: Vertical (↓)
├─ Spacing: 0px (选项间无间距)
├─ Padding: 4px (上下)
├─ Max Height: 256px (8个选项)
├─ Overflow: Scroll (垂直滚动)
└─ Resizing:
   ├─ Horizontal: Fixed (与 Input 同宽)
   └─ Vertical: Hug contents (最大 256px)

效果:
├─ Shadow: 0 4px 12px rgba(0,0,0,0.08)
├─ Border: 1px solid #F0F0F0
└─ Border Radius: 4px
```

### 7.3 Option Item 设置

```
Frame 名称: Option/Default

Auto Layout:
├─ Direction: Horizontal (→)
├─ Spacing: 8px (Checkmark-Text 间距)
├─ Padding: 12px (左右)
├─ Height: 32px (Fixed)
└─ Resizing:
   ├─ Horizontal: Fill container
   └─ Vertical: Fixed

子元素:
├─ Checkmark Icon (Optional, 16×16px)
└─ Option Text (Fill, Truncate)
```

### 7.4 多选标签设置

```
Frame 名称: Select/Multiple/Tags

Auto Layout (Tags Container):
├─ Direction: Horizontal (→)
├─ Spacing: 4px (Tag 间距)
├─ Padding: 4px
├─ Wrap: True (自动换行)
└─ Resizing: Fill container

Tag (子元素):
├─ Height: 24px
├─ Padding: 0 8px
├─ Background: #F0F0F0
└─ Border Radius: 2px
```

---

## 8. Design Token 完整映射表

### 8.1 颜色 Token

| 元素 | Token 变量 | 亮色模式 | 暗色模式 |
|------|-----------|---------|---------|
| Input 背景 | `select-bg` | `{color.white}` #FFFFFF | `{color.grey.900}` #212121 |
| Input 边框 - Default | `select-border` | `{color.grey.400}` #D9D9D9 | `{color.grey.600}` #757575 |
| Input 边框 - Hover | `select-border-hover` | `{color.blue.600}` #1976D2 | `{color.blue.500}` #2196F3 |
| Input 边框 - Focused | `select-border-focused` | `{color.blue.600}` #1976D2 | `{color.blue.500}` #2196F3 |
| Input 边框 - Error | `select-border-error` | `{color.red.700}` #D32F2F | `{color.red.500}` #F44336 |
| Input 文字 | `select-text` | `{color.grey.900}` #212121 | `{color.grey.100}` #F5F5F5 |
| Placeholder | `select-placeholder` | `{color.grey.500}` #9E9E9E | `{color.grey.500}` #9E9E9E |
| Disabled 背景 | `select-disabled-bg` | `{color.grey.100}` #F5F5F5 | `{color.grey.800}` #424242 |
| Disabled 文字 | `select-disabled-text` | `{color.grey.500}` #9E9E9E | `{color.grey.600}` #757575 |
| Arrow Icon | `select-arrow-color` | `{color.grey.500}` #9E9E9E | `{color.grey.400}` #BDBDBD |
| Arrow Icon (Open) | `select-arrow-color-open` | `{color.blue.600}` #1976D2 | `{color.blue.500}` #2196F3 |
| Dropdown 背景 | `select-dropdown-bg` | `{color.white}` #FFFFFF | `{color.grey.800}` #424242 |
| Option 背景 - Hover | `select-option-hover-bg` | `{color.grey.100}` #F5F5F5 | `{color.grey.700}` #616161 |
| Option 背景 - Selected | `select-option-selected-bg` | `{color.blue.50}` #E3F2FD | `{color.blue.900}` #0D47A1 |
| Option 文字 | `select-option-text` | `{color.grey.900}` #212121 | `{color.grey.100}` #F5F5F5 |
| Option 文字 - Disabled | `select-option-disabled-text` | `{color.grey.500}` #9E9E9E | `{color.grey.600}` #757575 |
| Checkmark 颜色 | `select-checkmark-color` | `{color.blue.600}` #1976D2 | `{color.blue.400}` #42A5F5 |
| Group Title 背景 | `select-group-bg` | `{color.grey.50}` #FAFAFA | `{color.grey.800}` #424242 |
| Group Title 文字 | `select-group-text` | `{color.grey.600}` #757575 | `{color.grey.400}` #BDBDBD |

### 8.2 间距 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| Large 水平内边距 | `spacing-3` | `12px` |
| Middle 水平内边距 | `spacing-3` | `12px` |
| Small 水平内边距 | `spacing-2` | `8px` |
| Prefix-Text 间距 | `spacing-2` | `8px` |
| Text-Clear 间距 | `spacing-2` | `8px` |
| Clear-Arrow 间距 | `spacing-1` | `4px` |
| Input-Dropdown 间距 | `spacing-1` | `4px` |
| Option 内边距 | `spacing-3` | `12px` |
| Tag 间距 | `spacing-1` | `4px` |
| Tag 内边距 | `spacing-2` | `8px` |

### 8.3 文字 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| Large 字号 | `font-size-lg` | `16px` |
| Middle 字号 | `font-size-base` | `14px` |
| Small 字号 | `font-size-sm` | `12px` |
| Option 字号 | `font-size-base` | `14px` |
| Group Title 字号 | `font-size-sm` | `12px` |
| 字重 | `font-weight-regular` | `400` |
| Group Title 字重 | `font-weight-medium` | `500` |

### 8.4 其他 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| 圆角 | `borderRadius-base` | `4px` |
| Tag 圆角 | `borderRadius-sm` | `2px` |
| 边框宽度 | `borderWidth-base` | `1px` |
| Dropdown 阴影 | `shadow-lg` | `0 4px 12px rgba(0,0,0,0.08)` |
| 展开动画时长 | `duration-short` | `200ms` |
| Hover 动画时长 | `duration-fastest` | `100ms` |

---

## 9. 设计最佳实践

### 9.1 Do's（推荐做法）

#### ✅ 合理选择选择器类型

```
✅ 正确：
5个以内选项 → 使用 Radio
[◉ 选项1]  [○ 选项2]  [○ 选项3]

5个以上选项 → 使用 Select
[请选择  ⌄]

❌ 错误：
3个选项还用 Select → 操作繁琐
```

#### ✅ 提供搜索功能（选项多时）

```
✅ 正确：
50+ 城市选项 → 可搜索 Select
┌─────────────────────┐
│ 🔍 输入城市名搜索... │
│ ┌─ 搜索结果 ───────┐ │
│ │ 北京市           │ │
│ │ 北海市           │ │
│ └─────────────────┘ │
└─────────────────────┘

❌ 错误：
50+ 选项不可搜索 → 用户难以找到
```

#### ✅ 明确的空状态提示

```
✅ 正确：
无匹配选项时显示：
┌─────────────────┐
│ 🔍 搜索...      │
│ ┌─────────────┐ │
│ │ 无匹配选项  │ │
│ │ 请重新输入  │ │
│ └─────────────┘ │
└─────────────────┘

❌ 错误：
空白 Dropdown → 用户困惑
```

#### ✅ 分组组织（选项多时）

```
✅ 正确：
┌─ 热门城市 ──────┐
│ 北京            │
│ 上海            │
├─ 所有城市 ──────┤
│ 安徽省          │
│ 北京市          │
└─────────────────┘

❌ 错误：
所有城市平铺 → 难以查找
```

#### ✅ 合理的默认值

```
✅ 正确：
地区选择默认：当前定位城市
语言选择默认：系统语言

❌ 错误：
强制用户每次都选择
```

### 9.2 Don'ts（不推荐做法）

#### ❌ Placeholder 文案不清晰

```
❌ 错误：
[选择  ⌄]  ← 选择什么？

✅ 正确：
[请选择城市  ⌄]  ← 明确说明
```

#### ❌ 选项文字过长

```
❌ 错误：
选项：北京市朝阳区建国路XX号XX大厦XX层  ← 文字溢出

✅ 正确：
选项：北京市朝阳区
提示：完整地址在 Tooltip 中显示
```

#### ❌ 禁用选项不明显

```
❌ 错误：
禁用选项与正常选项颜色相同 → 用户点击后才发现不可选

✅ 正确：
禁用选项：灰色文字 + 不可点击光标
```

#### ❌ 多选标签过多导致输入框过高

```
❌ 错误：
[Tag1 ×] [Tag2 ×] [Tag3 ×]
[Tag4 ×] [Tag5 ×] [Tag6 ×]  ← 输入框高度失控
[Tag7 ×] [Tag8 ×]

✅ 正确（方案1）：
[已选择 8 项  ⌄]  ← 折叠显示

✅ 正确（方案2）：
[Tag1 ×] [Tag2 ×] +6  ⌄  ← 显示前2个 + 计数
```

### 9.3 常见场景最佳实践

#### 单选（基础）

```tsx
<Select placeholder="请选择城市" style={{ width: 200 }}>
  <Option value="beijing">北京</Option>
  <Option value="shanghai">上海</Option>
  <Option value="guangzhou">广州</Option>
</Select>
```

#### 可搜索（选项多）

```tsx
<Select
  showSearch
  placeholder="搜索城市"
  optionFilterProp="children"
  filterOption={(input, option) =>
    option.children.toLowerCase().includes(input.toLowerCase())
  }
>
  {cities.map(city => (
    <Option key={city.code} value={city.code}>
      {city.name}
    </Option>
  ))}
</Select>
```

#### 分组选项

```tsx
<Select placeholder="选择城市">
  <OptGroup label="热门城市">
    <Option value="beijing">北京</Option>
    <Option value="shanghai">上海</Option>
  </OptGroup>
  <OptGroup label="所有城市">
    <Option value="anhui">安徽</Option>
    <Option value="fujian">福建</Option>
  </OptGroup>
</Select>
```

#### 多选

```tsx
<Select
  mode="multiple"
  placeholder="选择多个城市"
  maxTagCount={2}
  maxTagPlaceholder={omittedValues => `+${omittedValues.length}`}
>
  <Option value="beijing">北京</Option>
  <Option value="shanghai">上海</Option>
  <Option value="guangzhou">广州</Option>
</Select>
```

#### 远程搜索

```tsx
<Select
  showSearch
  placeholder="搜索用户"
  filterOption={false}
  onSearch={handleSearch}
  loading={loading}
  notFoundContent={loading ? <Spin size="small" /> : '无匹配用户'}
>
  {users.map(user => (
    <Option key={user.id} value={user.id}>
      {user.name}
    </Option>
  ))}
</Select>
```

### 9.4 可访问性最佳实践

#### ✅ ARIA 属性

```html
<div
  role="combobox"
  aria-expanded="true"
  aria-haspopup="listbox"
  aria-labelledby="select-label"
  aria-controls="select-dropdown"
>
  <span id="select-label">选择城市</span>
  <input aria-autocomplete="list" />
</div>

<ul id="select-dropdown" role="listbox">
  <li role="option" aria-selected="true">北京</li>
  <li role="option" aria-selected="false">上海</li>
</ul>
```

#### ✅ 键盘导航

```
Tab:       聚焦到 Select
Enter:     展开 Dropdown
↑/↓:       高亮上/下选项
Enter:     选中当前高亮选项
Esc:       收起 Dropdown
A-Z:       跳转到首字母匹配
```

#### ✅ 屏幕阅读器

```html
<!-- 明确选中状态 -->
<li role="option" aria-selected="true">
  北京 (已选中)
</li>

<!-- 禁用选项提示 -->
<li role="option" aria-disabled="true">
  上海 (不可选)
</li>

<!-- 分组标题 -->
<div role="group" aria-labelledby="group-title">
  <div id="group-title">热门城市</div>
  <li role="option">北京</li>
</div>
```

---

## 10. 代码示例（组件 API）

### 10.1 基础用法

```tsx
import { Select } from 'your-design-system';
const { Option } = Select;

// 基础单选
<Select placeholder="请选择" style={{ width: 200 }}>
  <Option value="option1">选项1</Option>
  <Option value="option2">选项2</Option>
  <Option value="option3">选项3</Option>
</Select>

// 带默认值
<Select defaultValue="option1">
  <Option value="option1">选项1</Option>
  <Option value="option2">选项2</Option>
</Select>

// 禁用状态
<Select disabled placeholder="禁用状态">
  <Option value="option1">选项1</Option>
</Select>
```

### 10.2 尺寸

```tsx
<Select size="large" placeholder="Large">
  <Option value="1">选项1</Option>
</Select>

<Select size="middle" placeholder="Middle（默认）">
  <Option value="1">选项1</Option>
</Select>

<Select size="small" placeholder="Small">
  <Option value="1">选项1</Option>
</Select>
```

### 10.3 可搜索

```tsx
<Select
  showSearch
  placeholder="搜索选项"
  optionFilterProp="children"
  filterOption={(input, option) =>
    option.children.toLowerCase().includes(input.toLowerCase())
  }
>
  <Option value="beijing">北京</Option>
  <Option value="shanghai">上海</Option>
  <Option value="guangzhou">广州</Option>
  <Option value="shenzhen">深圳</Option>
</Select>
```

### 10.4 多选

```tsx
// 基础多选
<Select mode="multiple" placeholder="选择多项">
  <Option value="1">选项1</Option>
  <Option value="2">选项2</Option>
  <Option value="3">选项3</Option>
</Select>

// 限制显示标签数量
<Select
  mode="multiple"
  maxTagCount={2}
  maxTagPlaceholder={omitted => `+${omitted.length} 项`}
>
  <Option value="1">选项1</Option>
  <Option value="2">选项2</Option>
  <Option value="3">选项3</Option>
</Select>

// Tags 模式（可输入）
<Select mode="tags" placeholder="输入标签">
  <Option value="tag1">标签1</Option>
  <Option value="tag2">标签2</Option>
</Select>
```

### 10.5 分组

```tsx
<Select placeholder="选择城市">
  <OptGroup label="热门城市">
    <Option value="beijing">北京</Option>
    <Option value="shanghai">上海</Option>
    <Option value="guangzhou">广州</Option>
  </OptGroup>
  <OptGroup label="其他城市">
    <Option value="chengdu">成都</Option>
    <Option value="hangzhou">杭州</Option>
  </OptGroup>
</Select>
```

### 10.6 远程搜索

```tsx
function RemoteSelect() {
  const [data, setData] = useState([]);
  const [loading, setLoading] = useState(false);

  const handleSearch = async (value) => {
    setLoading(true);
    const result = await fetchUsers(value);
    setData(result);
    setLoading(false);
  };

  return (
    <Select
      showSearch
      placeholder="搜索用户"
      filterOption={false}
      onSearch={handleSearch}
      loading={loading}
      notFoundContent={loading ? <Spin /> : '无匹配用户'}
    >
      {data.map(user => (
        <Option key={user.id} value={user.id}>
          {user.name}
        </Option>
      ))}
    </Select>
  );
}
```

### 10.7 自定义渲染

```tsx
// 自定义 Option 内容
<Select placeholder="选择用户">
  {users.map(user => (
    <Option key={user.id} value={user.id}>
      <div style={{ display: 'flex', alignItems: 'center' }}>
        <Avatar src={user.avatar} size="small" />
        <span style={{ marginLeft: 8 }}>{user.name}</span>
      </div>
    </Option>
  ))}
</Select>

// 自定义下拉渲染
<Select
  dropdownRender={menu => (
    <>
      {menu}
      <Divider style={{ margin: '8px 0' }} />
      <Button type="text" icon={<PlusIcon />} block>
        添加新项
      </Button>
    </>
  )}
>
  <Option value="1">选项1</Option>
</Select>
```

### 10.8 完整 API

```typescript
interface SelectProps<T = any> {
  // 基础属性
  value?: T;                                    // 当前选中值
  defaultValue?: T;                             // 默认选中值
  placeholder?: string;                         // 占位文字
  disabled?: boolean;                           // 禁用状态

  // 模式
  mode?: 'multiple' | 'tags';                   // 多选/标签模式

  // 尺寸
  size?: 'large' | 'middle' | 'small';          // 尺寸

  // 搜索
  showSearch?: boolean;                         // 可搜索
  filterOption?: boolean | ((input, option) => boolean); // 过滤函数
  optionFilterProp?: string;                    // 过滤的 Option 属性

  // 清除
  allowClear?: boolean;                         // 可清除

  // 多选配置
  maxTagCount?: number;                         // 最多显示标签数
  maxTagPlaceholder?: (omitted) => ReactNode;   // 超出标签占位符
  maxTagTextLength?: number;                    // 标签文字最大长度

  // 下拉配置
  dropdownStyle?: CSSProperties;                // 下拉样式
  dropdownClassName?: string;                   // 下拉类名
  dropdownRender?: (menu) => ReactNode;         // 自定义下拉渲染

  // 加载
  loading?: boolean;                            // 加载状态
  notFoundContent?: ReactNode;                  // 无数据时内容

  // 事件
  onChange?: (value: T, option) => void;        // 值变化回调
  onSearch?: (value: string) => void;           // 搜索回调
  onSelect?: (value: T, option) => void;        // 选中回调
  onDeselect?: (value: T, option) => void;      // 取消选中回调
  onDropdownVisibleChange?: (open: boolean) => void; // 下拉展开/收起

  // 其他
  autoFocus?: boolean;                          // 自动聚焦
  autoClearSearchValue?: boolean;               // 选中后清空搜索值
  virtual?: boolean;                            // 虚拟滚动
  listHeight?: number;                          // 下拉列表高度
}

// Option Props
interface OptionProps {
  value: any;                                   // 选项值
  disabled?: boolean;                           // 禁用
  children?: ReactNode;                         // 显示内容
  className?: string;
  style?: CSSProperties;
}

// OptGroup Props
interface OptGroupProps {
  label: ReactNode;                             // 分组标题
  children?: ReactNode;                         // 子选项
}
```

---

## 11. 相关资源

### 组件依赖

| 组件 | 说明 |
|------|------|
| Dropdown | 下拉容器 |
| Input | 搜索输入框 |
| Checkbox | 多选模式复选框 |
| Tag | 多选标签 |
| Spin | 加载状态 |

### 相关组件

| 组件 | 使用场景 |
|------|---------|
| Radio | 2-5个选项单选 |
| Checkbox | 2-5个选项多选 |
| TreeSelect | 树形结构选择 |
| Cascader | 级联选择 |
| AutoComplete | 自动补全输入 |

### Design Token 文档

- [tokens.json](../../../foundations/tokens/tokens.json) - 完整 Token 定义
- [semantic-colors.json](../../../foundations/tokens/semantic-colors.json) - 语义色定义
- [交互色规范](../../../foundations/colors.md) - 交互色使用指南

### 设计资源

- [Ant Design Select](https://ant.design/components/select-cn/)
- [Material Design Menus](https://m3.material.io/components/menus/overview)
- [ARIA Combobox Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/combobox/)

---

## 12. 更新日志

| 版本 | 日期 | 更新内容 |
|------|------|---------|
| v1.0 | 2025-11-19 | 初始版本，完整的 Select 组件设计规范 |

---

**文档版本：** v1.0
**最后更新：** 2025-11-19
**维护者：** 设计系统团队
**审核状态：** ✅ 已完成

> **参考样板：** Input, Table
> **优先级：** P0
> **复杂度：** ⭐⭐⭐ 高
