# Button 按钮

> 触发操作的交互元素，是用户与系统交互的最基础组件。

---

## 1. 何时使用

### 适用场景

✅ **提交表单** - 保存、提交、确认等操作
✅ **触发操作** - 删除、编辑、新增、导出等
✅ **页面导航** - 跳转到其他页面或视图
✅ **对话框交互** - 弹窗中的确认/取消按钮
✅ **工具栏操作** - 顶部操作栏的批量操作按钮

### 不要使用的场景

❌ **纯文字链接** - 应使用 Link 组件
❌ **页内锚点跳转** - 应使用 Anchor 组件
❌ **导航菜单** - 应使用 Menu 组件
❌ **标签切换** - 应使用 Tabs 组件

### 替代方案

| 场景 | 推荐组件 | 说明 |
|------|---------|------|
| 页面内跳转 | `Link` | 文字链接，无背景 |
| 下拉操作菜单 | `Dropdown` | 多个操作收纳到下拉菜单 |
| 分段选择器 | `Segmented` | 互斥的选项切换 |
| 悬浮按钮 | `FloatButton` | 固定位置的快捷操作 |

---

## 2. 解剖结构（Anatomy）

### 组件拆解

```
┌─────────────────────────────────┐
│  ┌─────┬─────────────┬─────┐   │ ← Container (Auto Layout)
│  │     │             │     │   │
│  │ 图标 │  按钮文字    │ 图标 │   │
│  │     │             │     │   │
│  └─────┴─────────────┴─────┘   │
└─────────────────────────────────┘
   ↑     ↑             ↑
   8px   Spacing       8px
         (可变)
```

### 元素说明

| 元素 | 名称 | 必需 | 说明 |
|------|------|------|------|
| Container | 容器 | ✅ | 包含所有子元素，定义背景、边框、圆角 |
| Text | 文字 | ✅ | 按钮文案（2-6 个字符） |
| Icon Left | 左侧图标 | ⚪ 可选 | 辅助说明操作类型 |
| Icon Right | 右侧图标 | ⚪ 可选 | 通常用于下拉箭头 |
| Loading Icon | 加载图标 | ⚪ 可选 | 替换左侧图标或单独显示 |

### 层级关系

```
Button (Component)
├─ Container (Frame)
│  ├─ Icon Left (Optional)
│  ├─ Text (Required)
│  └─ Icon Right (Optional)
```

---

## 3. 尺寸与间距

### 3.1 三种尺寸规格

| 尺寸 | 高度 | 水平内边距 | 字号 | 行高 | 图标尺寸 | 使用场景 |
|------|------|-----------|------|------|---------|---------|
| **Large** | `40px` | `16px` | `16px` | `24px` | `20px` | 主要操作、表单提交 |
| **Middle** | `32px` | `12px` | `14px` | `20px` | `16px` | 默认尺寸，最常用 |
| **Small** | `24px` | `8px` | `12px` | `16px` | `14px` | 次要操作、紧凑布局 |

### 3.2 间距规范（基于 4px 网格）

#### 内部间距（Padding）

```
Large:   ┌─16px─┬──────┬─16px─┐
         │ Icon │ 8px  │ Text │
         └──────┴──────┴──────┘

Middle:  ┌─12px─┬──────┬─12px─┐
         │ Icon │ 8px  │ Text │
         └──────┴──────┴──────┘

Small:   ┌─8px──┬──────┬─8px──┐
         │ Icon │ 4px  │ Text │
         └──────┴──────┴──────┘
```

#### 图标与文字间距

| 尺寸 | 图标-文字间距 | Token |
|------|-------------|-------|
| Large | `8px` | `spacing-2` |
| Middle | `8px` | `spacing-2` |
| Small | `4px` | `spacing-1` |

#### 按钮间距

```
水平排列：
[Button] ─12px─ [Button] ─12px─ [Button]  ← 主次按钮
[Button] ─8px─  [Button]                   ← 同等级按钮

垂直排列：
[Button]
   ↓ 12px
[Button]
```

### 3.3 最小点击区域

| 平台 | 最小尺寸 | 说明 |
|------|---------|------|
| 桌面端 | `32×32px` | Middle 尺寸满足 |
| 移动端 | `44×44px` | 需使用 Large 尺寸 |

### 3.4 宽度规则

| 类型 | 宽度 | Figma 设置 |
|------|------|-----------|
| 默认 | 自适应内容 | `Hug contents` |
| 块级按钮 | 100% 父容器 | `Fill container` |
| 固定宽度 | 自定义（如 120px） | `Fixed` |

**最小宽度：**
- Large: `80px`
- Middle: `64px`
- Small: `48px`

---

## 4. 视觉规范

### 4.1 颜色规范（Design Token 映射）

#### Primary 主按钮

| 状态 | 背景色 | 文字色 | 边框 | Token |
|------|--------|--------|------|-------|
| **Default** | `#1976D2` (Blue 600) | `#FFFFFF` (White) | 无 | `interactive-primary` |
| **Hover** | `#1565C0` (Blue 700) | `#FFFFFF` | 无 | `interactive-primary-hover` |
| **Active** | `#0D47A1` (Blue 900) | `#FFFFFF` | 无 | `interactive-primary-active` |
| **Focus** | `#1976D2` + Ring | `#FFFFFF` | `3px #90CAF9` | `interactive-primary` + `focus-ring` |
| **Disabled** | `#E0E0E0` (Grey 300) | `#9E9E9E` (Grey 500) | 无 | `interactive-disabled` |
| **Loading** | `#1976D2` | `#FFFFFF` | 无 | `interactive-primary` |

**Design Token 映射：**
```json
{
  "button-primary-bg-default": "{semantic.interactive.primary}",
  "button-primary-bg-hover": "{semantic.interactive.primary-hover}",
  "button-primary-bg-active": "{semantic.interactive.primary-active}",
  "button-primary-text": "{semantic.text.inverse}",
  "button-disabled-bg": "{semantic.interactive.disabled}",
  "button-disabled-text": "{semantic.text.disabled}"
}
```

#### Secondary 次按钮（Default）

| 状态 | 背景色 | 文字色 | 边框 | Token |
|------|--------|--------|------|-------|
| **Default** | `#FFFFFF` | `#212121` (Grey 900) | `1px #BDBDBD` | `background-primary` + `border-default` |
| **Hover** | `#FAFAFA` (Grey 50) | `#212121` | `1px #1976D2` | `background-hover` + `border-primary` |
| **Active** | `#F5F5F5` (Grey 100) | `#212121` | `1px #1976D2` | `background-active` + `border-primary` |
| **Focus** | `#FFFFFF` + Ring | `#212121` | `1px #BDBDBD` + `3px #90CAF9` | 同上 + `focus-ring` |
| **Disabled** | `#FAFAFA` | `#9E9E9E` | `1px #E0E0E0` | `interactive-disabled` |

#### Dashed 虚线按钮

| 状态 | 背景色 | 文字色 | 边框 | 用途 |
|------|--------|--------|------|------|
| **Default** | 透明 | `#757575` (Grey 600) | `1px dashed #BDBDBD` | 添加、上传等次要操作 |
| **Hover** | `#FAFAFA` | `#1976D2` | `1px dashed #1976D2` | - |

#### Danger 危险按钮

| 状态 | 背景色 | 文字色 | 边框 | 用途 |
|------|--------|--------|------|------|
| **Default** | `#D32F2F` (Red 700) | `#FFFFFF` | 无 | 删除、清空等危险操作 |
| **Hover** | `#C62828` (Red 800) | `#FFFFFF` | 无 | - |
| **Active** | `#B71C1C` (Red 900) | `#FFFFFF` | 无 | - |

#### Ghost 幽灵按钮

| 状态 | 背景色 | 文字色 | 边框 | 用途 |
|------|--------|--------|------|------|
| **Default** | 透明 | `#1976D2` | `1px #1976D2` | 深色背景上使用 |
| **Hover** | `rgba(25, 118, 210, 0.08)` | `#1565C0` | `1px #1565C0` | - |

#### Text 文字按钮

| 状态 | 背景色 | 文字色 | 边框 | 用途 |
|------|--------|--------|------|------|
| **Default** | 透明 | `#1976D2` | 无 | 最弱化的操作 |
| **Hover** | `rgba(25, 118, 210, 0.08)` | `#1565C0` | 无 | - |

### 4.2 文字规范

#### 字体样式

| 尺寸 | 字号 | 行高 | 字重 | Token |
|------|------|------|------|-------|
| Large | `16px` | `24px` | `500 Medium` | `font-size-base-lg` |
| Middle | `14px` | `20px` | `500 Medium` | `font-size-base` |
| Small | `12px` | `16px` | `500 Medium` | `font-size-base-sm` |

#### 文案规范

| 规则 | 说明 | 示例 |
|------|------|------|
| 字数 | 2-6 个字符（中文）<br>2-10 个字符（英文） | ✅ 提交、保存、确定<br>❌ 确认要删除这个项目吗 |
| 措辞 | 使用动词，明确操作 | ✅ 提交表单<br>❌ 点击这里 |
| 大小写 | 英文使用 Sentence case | ✅ Submit form<br>❌ SUBMIT FORM |
| 省略号 | 操作会打开新窗口/弹窗时添加 | "更多..." |

### 4.3 图标规范

#### 图标尺寸

| 按钮尺寸 | 图标尺寸 | Token |
|---------|---------|-------|
| Large | `20px` | `icon-size-lg` |
| Middle | `16px` | `icon-size-base` |
| Small | `14px` | `icon-size-sm` |

#### 图标颜色

- 跟随文字颜色（同一 Token）
- Loading 图标：使用 currentColor 继承

#### 图标位置

```
[🔍 搜索]     ← 左侧图标：说明操作类型
[下载 ⬇]     ← 右侧图标：辅助信息（如下拉箭头）
[⊕]          ← 纯图标按钮：图标居中
```

### 4.4 其他视觉元素

#### 圆角

| 尺寸 | 圆角 | Token | 说明 |
|------|------|-------|------|
| Large | `4px` | `borderRadius-base` | 默认圆角 |
| Middle | `4px` | `borderRadius-base` | 默认圆角 |
| Small | `4px` | `borderRadius-base` | 默认圆角 |
| Round | `32px` | `borderRadius-round` | 圆角按钮 |
| Circle | `50%` | `borderRadius-circle` | 圆形按钮（纯图标） |

#### 边框

| 类型 | 边框宽度 | 边框样式 | Token |
|------|---------|---------|-------|
| Primary | 无 | - | - |
| Secondary | `1px` | `solid` | `borderWidth-base` |
| Dashed | `1px` | `dashed` | `borderWidth-base` |
| Ghost | `1px` | `solid` | `borderWidth-base` |

#### 阴影

| 类型 | 阴影 | 使用场景 |
|------|------|---------|
| 默认 | 无 | 大部分按钮无阴影 |
| 悬浮按钮 | `0 4px 8px rgba(0,0,0,0.12)` | FloatButton |
| Hover（可选） | `0 2px 4px rgba(0,0,0,0.08)` | 可选的 Hover 效果 |

#### Focus Ring

| 属性 | 值 | Token |
|------|-----|-------|
| 宽度 | `3px` | `focus-ring-width` |
| 颜色 | `#90CAF9` (Blue 200, 60% opacity) | `focus-ring-color` |
| 偏移 | `2px` | `focus-ring-offset` |
| 样式 | `solid` | - |

```css
/* Focus Ring 实现 */
.button:focus {
  outline: 3px solid rgba(144, 202, 249, 0.6);
  outline-offset: 2px;
}
```

---

## 5. 组件状态（States）

### 5.1 状态总览

| 状态 | 触发条件 | 视觉变化 | 交互能力 |
|------|---------|---------|---------|
| **Default** | 默认 | 正常颜色 | ✅ 可点击 |
| **Hover** | 鼠标悬停 | 背景变深/边框高亮 | ✅ 可点击 |
| **Active** | 鼠标按下 | 背景进一步加深 | ✅ 可点击 |
| **Focus** | 键盘 Tab 聚焦 | 显示 Focus Ring | ✅ 可点击（Enter 触发） |
| **Disabled** | `disabled={true}` | 灰色，透明度 40% | ❌ 不可点击 |
| **Loading** | `loading={true}` | 显示 Loading 图标 | ❌ 不可点击 |

### 5.2 状态优先级

```
Disabled > Loading > Focus > Active > Hover > Default
```

**说明：**
- Disabled 和 Loading 状态下，忽略所有其他状态
- Focus 状态可以与 Hover/Active 叠加

### 5.3 状态详解

#### Default（默认态）

```
视觉：正常颜色
光标：pointer
动画：无
```

#### Hover（悬停态）

```
视觉：
- Primary: 背景从 Blue 600 → Blue 700
- Secondary: 背景从 White → Grey 50，边框从 Grey → Blue
光标：pointer
过渡：all 0.2s cubic-bezier(0.4, 0, 0.2, 1)
```

#### Active（激活态）

```
视觉：背景进一步加深
光标：pointer
持续时间：鼠标按下期间
```

#### Focus（聚焦态）

```
视觉：显示 3px 蓝色 Focus Ring
触发：键盘 Tab 导航
键盘操作：
- Enter: 触发点击
- Space: 触发点击
- Tab: 移动到下一个可聚焦元素
```

#### Disabled（禁用态）

```
视觉：
- 背景：Grey 300 (#E0E0E0)
- 文字：Grey 500 (#9E9E9E)
- 透明度：40%
光标：not-allowed
交互：所有事件被禁用
```

#### Loading（加载态）

```
视觉：
- 显示 Loading 图标（旋转动画）
- 保持原有颜色
- 文字可选显示（"提交中..." 或隐藏）
光标：not-allowed
交互：所有点击事件被阻止
动画：Loading 图标 360° 旋转，1s 匀速
```

### 5.4 状态转换动画

| 转换 | 过渡时间 | 缓动函数 | Token |
|------|---------|---------|-------|
| Default ↔ Hover | `200ms` | `cubic-bezier(0.4, 0, 0.2, 1)` | `duration-short` |
| Hover ↔ Active | `100ms` | `cubic-bezier(0.4, 0, 0.2, 1)` | `duration-fastest` |
| 任意 → Disabled | `0ms` | - | 立即切换 |
| 任意 → Loading | `0ms` | - | 立即切换 |

---

## 6. 组件变体（Figma Variants）

### 6.1 Variants 属性配置

在 Figma 中创建 Button 组件时，设置以下 Variant 属性：

| 属性名 | 属性值 | 默认值 | 说明 |
|--------|--------|--------|------|
| **Type** | Primary / Secondary / Dashed / Danger / Ghost / Text | `Primary` | 按钮类型 |
| **Size** | Large / Middle / Small | `Middle` | 按钮尺寸 |
| **State** | Default / Hover / Active / Focus / Disabled / Loading | `Default` | 交互状态 |
| **Icon** | None / Left / Right / Only | `None` | 图标位置 |
| **Shape** | Default / Round / Circle | `Default` | 形状 |

### 6.2 Variants 组合数量

```
总组合数 = 6 (Type) × 3 (Size) × 6 (State) × 4 (Icon) × 3 (Shape)
         = 1,296 个组合（理论值）
```

**实际建议：**
- 只创建常用组合（约 200 个）
- 使用 Figma Variables 动态控制颜色
- Shape=Circle 时自动隐藏 Text

### 6.3 命名规范

```
格式：Type / Size / State / Icon

示例：
- Primary / Large / Default / None
- Secondary / Middle / Hover / Left
- Danger / Small / Disabled / None
```

### 6.4 Variants 决策树

```
选择 Type
  ├─ Primary:    主要操作、表单提交
  ├─ Secondary:  次要操作
  ├─ Dashed:     添加、上传类操作
  ├─ Danger:     删除、清空等危险操作
  ├─ Ghost:      深色背景使用
  └─ Text:       最弱化操作

选择 Size
  ├─ Large:      移动端、主要 CTA
  ├─ Middle:     默认（90% 场景）
  └─ Small:      紧凑布局、表格内操作

选择 Icon
  ├─ None:       纯文字按钮
  ├─ Left:       图标说明操作类型
  ├─ Right:      下拉箭头、外部链接
  └─ Only:       工具栏、纯图标按钮

选择 Shape
  ├─ Default:    默认（99% 场景）
  ├─ Round:      特殊强调
  └─ Circle:     纯图标按钮（Icon Only）
```

---

## 7. Figma Auto Layout 配置

### 7.1 Container 设置

```
Frame 名称: Button/Primary/Large/Default/None

Auto Layout:
├─ Direction: Horizontal (→)
├─ Spacing: 8px (图标与文字间距)
├─ Padding:
│  ├─ Large:  16px (左右)
│  ├─ Middle: 12px (左右)
│  └─ Small:  8px (左右)
├─ Alignment:
│  ├─ Horizontal: Center
│  └─ Vertical: Center
└─ Resizing:
   ├─ Horizontal: Hug contents (默认) / Fill container (块级按钮)
   └─ Vertical: Fixed (40px / 32px / 24px)
```

### 7.2 Icon 设置

```
Icon Frame:
├─ Size: 20×20px / 16×16px / 14×14px (根据按钮尺寸)
├─ Constraints: Center
└─ Resizing: Fixed
```

### 7.3 Text 设置

```
Text Layer:
├─ Font: Inter / PingFang SC
├─ Weight: 500 (Medium)
├─ Size: 16px / 14px / 12px (根据按钮尺寸)
├─ Line height: 24px / 20px / 16px
├─ Alignment: Center
└─ Resizing: Hug contents
```

### 7.4 响应式配置

**实现块级按钮（宽度 100%）：**
1. 选中 Button Frame
2. Resizing → Horizontal: **Fill container**

**实现固定宽度按钮：**
1. Resizing → Horizontal: **Fixed**
2. 手动设置宽度（如 120px）

---

## 8. Design Token 完整映射表

### 8.1 颜色 Token

| 元素 | Token 变量 | 亮色模式 | 暗色模式 |
|------|-----------|---------|---------|
| Primary 背景 - Default | `button-primary-bg` | `{color.blue.600}` #1976D2 | `{color.blue.700}` #1565C0 |
| Primary 背景 - Hover | `button-primary-bg-hover` | `{color.blue.700}` #1565C0 | `{color.blue.800}` #0D47A1 |
| Primary 背景 - Active | `button-primary-bg-active` | `{color.blue.900}` #0D47A1 | `{color.blue.900}` #0D47A1 |
| Primary 文字 | `button-primary-text` | `{color.grey.50}` #FAFAFA | `{color.grey.50}` #FAFAFA |
| Secondary 背景 - Default | `button-secondary-bg` | `{color.grey.50}` #FAFAFA | `{color.grey.800}` #424242 |
| Secondary 背景 - Hover | `button-secondary-bg-hover` | `{color.grey.100}` #F5F5F5 | `{color.grey.700}` #616161 |
| Secondary 文字 | `button-secondary-text` | `{color.grey.900}` #212121 | `{color.grey.50}` #FAFAFA |
| Secondary 边框 - Default | `button-secondary-border` | `{color.grey.400}` #BDBDBD | `{color.grey.600}` #757575 |
| Secondary 边框 - Hover | `button-secondary-border-hover` | `{color.blue.600}` #1976D2 | `{color.blue.500}` #2196F3 |
| Danger 背景 - Default | `button-danger-bg` | `{color.red.700}` #D32F2F | `{color.red.800}` #C62828 |
| Danger 背景 - Hover | `button-danger-bg-hover` | `{color.red.800}` #C62828 | `{color.red.900}` #B71C1C |
| Danger 文字 | `button-danger-text` | `{color.grey.50}` #FAFAFA | `{color.grey.50}` #FAFAFA |
| Disabled 背景 | `button-disabled-bg` | `{color.grey.300}` #E0E0E0 | `{color.grey.700}` #616161 |
| Disabled 文字 | `button-disabled-text` | `{color.grey.500}` #9E9E9E | `{color.grey.500}` #9E9E9E |
| Focus Ring | `focus-ring-color` | `{color.blue.200}` #90CAF9 (60%) | `{color.blue.300}` #64B5F6 |

### 8.2 间距 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| Large 水平内边距 | `spacing-4` | `16px` |
| Middle 水平内边距 | `spacing-3` | `12px` |
| Small 水平内边距 | `spacing-2` | `8px` |
| 图标文字间距 (L/M) | `spacing-2` | `8px` |
| 图标文字间距 (S) | `spacing-1` | `4px` |
| 按钮间距（主次） | `spacing-3` | `12px` |
| 按钮间距（同级） | `spacing-2` | `8px` |

### 8.3 文字 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| Large 字号 | `font-size-lg` | `16px` |
| Middle 字号 | `font-size-base` | `14px` |
| Small 字号 | `font-size-sm` | `12px` |
| 字重 | `font-weight-medium` | `500` |
| Large 行高 | `line-height-lg` | `24px` |
| Middle 行高 | `line-height-base` | `20px` |
| Small 行高 | `line-height-sm` | `16px` |

### 8.4 圆角 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| 默认圆角 | `borderRadius-base` | `4px` |
| 圆角按钮 | `borderRadius-round` | `32px` |
| 圆形按钮 | `borderRadius-circle` | `50%` |

### 8.5 边框 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| 边框宽度 | `borderWidth-base` | `1px` |
| Focus Ring 宽度 | `focus-ring-width` | `3px` |
| Focus Ring 偏移 | `focus-ring-offset` | `2px` |

### 8.6 动画 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| Hover 过渡时间 | `duration-short` | `200ms` |
| Active 过渡时间 | `duration-fastest` | `100ms` |
| 缓动函数 | `ease-in-out` | `cubic-bezier(0.4, 0, 0.2, 1)` |
| Loading 旋转时间 | `duration-slow` | `1000ms` |

---

## 9. 设计最佳实践

### 9.1 Do's（推荐做法）

#### ✅ 合理的按钮层级

```
┌──────────────────────────────────┐
│                                  │
│  [提交]  [取消]                  │  ← Primary + Secondary
│                                  │
└──────────────────────────────────┘
```

**说明：**
- 主要操作使用 Primary
- 次要操作使用 Secondary 或 Text
- 一个视图中最多 1 个 Primary 按钮

#### ✅ 清晰的文案

```
✅ 保存草稿      ❌ 点击这里
✅ 删除项目      ❌ 确定
✅ 导出 Excel    ❌ 导出
```

#### ✅ 合理的图标使用

```
✅ [🔍 搜索]     ← 图标辅助说明
✅ [下载 ⬇]     ← 右侧箭头表示下拉
✅ [➕]          ← 纯图标按钮（配 Tooltip）
```

#### ✅ 响应式布局

```
桌面端（宽屏）：
[搜索] [筛选] [导出] [新建]

移动端（窄屏）：
[搜索]
[新建]          ← 只保留主要操作
```

#### ✅ 加载状态

```
点击前:  [提交表单]
点击后:  [⊙ 提交中...]  ← 显示 Loading，禁用点击
完成:    [✓ 已提交]     ← 短暂显示成功状态（可选）
```

### 9.2 Don'ts（不推荐做法）

#### ❌ 过多 Primary 按钮

```
❌ 错误：
┌──────────────────────────────────┐
│  [提交] [保存] [导出] [删除]     │  ← 4 个 Primary
└──────────────────────────────────┘

✅ 正确：
┌──────────────────────────────────┐
│  [提交] 保存 导出 删除           │  ← 1 个 Primary + 3 个 Text/Link
└──────────────────────────────────┘
```

#### ❌ 文案过长

```
❌ 错误：[确认要删除这个项目吗]  ← 10 个字
✅ 正确：[删除]                 ← 2 个字（用 Modal 确认详情）
```

#### ❌ 图标与文字不匹配

```
❌ 错误：[❌ 提交]   ← 错误图标表示提交
✅ 正确：[✓ 提交]   ← 或不用图标
```

#### ❌ 尺寸混用

```
❌ 错误：
[Large 提交] [Small 取消]  ← 主次按钮尺寸不一致

✅ 正确：
[Middle 提交] [Middle 取消]  ← 尺寸统一
```

#### ❌ 禁用态不明显

```
❌ 错误：
Disabled 背景：#E0E0E0 (仅比 Default 浅一点)

✅ 正确：
Disabled 背景：#E0E0E0 + 透明度 40% + 不可点击光标
```

### 9.3 常见场景最佳实践

#### 表单提交

```
┌─────────────────────────┐
│  姓名: [________]       │
│  邮箱: [________]       │
│                         │
│  [提交]  取消           │  ← Primary + Text
└─────────────────────────┘
```

#### 对话框

```
┌─────────────────────────┐
│  确认删除？             │
│  删除后无法恢复         │
│                         │
│      [取消]  [删除]     │  ← Secondary + Danger
└─────────────────────────┘
```

#### 工具栏（批量操作）

```
┌─────────────────────────────────┐
│  [新建] [导入] [导出] | [删除]  │  ← Primary + Secondary × 3 + Danger
└─────────────────────────────────┘
```

#### 表格内操作

```
│ 姓名   │ 操作              │
│ 张三   │ 编辑 删除         │  ← Small Text Button
│ 李四   │ 编辑 删除         │
```

#### 移动端底部操作栏

```
┌───────────────────┐
│                   │
│                   │
│                   │
├───────────────────┤
│  [立即购买]       │  ← Large + Fill container
└───────────────────┘
```

### 9.4 可访问性最佳实践

#### ✅ 键盘导航

```html
<button
  tabindex="0"
  aria-label="提交表单"
  role="button"
>
  提交
</button>
```

**键盘操作：**
- `Tab`: 聚焦到按钮
- `Enter` / `Space`: 触发点击
- `Shift + Tab`: 反向聚焦

#### ✅ 屏幕阅读器

```html
<!-- 纯图标按钮必须有 aria-label -->
<button aria-label="删除项目">
  <TrashIcon />
</button>

<!-- Loading 状态 -->
<button aria-busy="true" aria-label="提交中">
  <LoadingIcon /> 提交中...
</button>

<!-- Disabled 状态 -->
<button disabled aria-disabled="true">
  提交
</button>
```

#### ✅ 颜色对比度

| 按钮类型 | 背景色 | 文字色 | 对比度 | WCAG |
|---------|--------|--------|--------|------|
| Primary | #1976D2 | #FFFFFF | 7.2:1 | ✅ AAA |
| Secondary | #FFFFFF | #212121 | 16.1:1 | ✅ AAA |
| Danger | #D32F2F | #FFFFFF | 6.8:1 | ✅ AAA |
| Disabled | #E0E0E0 | #9E9E9E | 2.9:1 | ⚠️ 禁用态豁免 |

#### ✅ Focus Ring 可见性

```
Focus Ring 必须满足：
- 宽度 ≥ 2px（推荐 3px）
- 与背景对比度 ≥ 3:1
- 偏移 ≥ 2px（避免被边框遮挡）
```

---

## 10. 代码示例（组件 API）

### 10.1 基础用法

```tsx
// Primary 按钮（最常用）
<Button type="primary">提交</Button>

// Secondary 按钮
<Button>取消</Button>

// Danger 按钮
<Button type="danger">删除</Button>

// Text 按钮
<Button type="text">查看详情</Button>
```

### 10.2 尺寸

```tsx
<Button size="large">大按钮</Button>
<Button size="middle">中按钮（默认）</Button>
<Button size="small">小按钮</Button>
```

### 10.3 带图标

```tsx
// 左侧图标
<Button icon={<SearchIcon />}>搜索</Button>

// 右侧图标
<Button iconPosition="right" icon={<DownIcon />}>
  下载
</Button>

// 纯图标
<Button icon={<PlusIcon />} shape="circle" />
```

### 10.4 状态

```tsx
// 禁用
<Button disabled>禁用按钮</Button>

// 加载中
<Button loading>加载中</Button>

// 块级按钮（宽度 100%）
<Button block>块级按钮</Button>
```

### 10.5 组合使用

```tsx
// 表单操作
<Space>
  <Button type="primary" htmlType="submit">
    提交
  </Button>
  <Button onClick={handleCancel}>取消</Button>
</Space>

// 对话框操作
<Modal
  footer={[
    <Button key="cancel" onClick={handleCancel}>
      取消
    </Button>,
    <Button key="submit" type="primary" onClick={handleOk}>
      确认
    </Button>,
  ]}
>
  确认删除此项目？
</Modal>
```

### 10.6 完整 API

```typescript
interface ButtonProps {
  // 类型
  type?: 'primary' | 'secondary' | 'dashed' | 'danger' | 'ghost' | 'text';

  // 尺寸
  size?: 'large' | 'middle' | 'small';

  // 形状
  shape?: 'default' | 'round' | 'circle';

  // 状态
  disabled?: boolean;
  loading?: boolean;

  // 图标
  icon?: ReactNode;
  iconPosition?: 'left' | 'right';

  // 样式
  block?: boolean;        // 块级按钮
  danger?: boolean;       // 危险按钮（已废弃，使用 type="danger"）

  // HTML 属性
  htmlType?: 'button' | 'submit' | 'reset';

  // 事件
  onClick?: (event: React.MouseEvent<HTMLButtonElement>) => void;

  // 其他
  className?: string;
  style?: React.CSSProperties;
  children?: ReactNode;
}
```

---

## 11. 相关资源

### 组件依赖

| 组件 | 说明 |
|------|------|
| Icon | 图标组件 |
| Space | 按钮组间距 |

### 相关组件

| 组件 | 使用场景 |
|------|---------|
| Link | 文字链接 |
| Dropdown | 下拉操作菜单 |
| FloatButton | 悬浮操作按钮 |

### Design Token 文档

- [tokens.json](../../foundations/tokens/tokens.json) - 完整 Token 定义
- [semantic-colors.json](../../foundations/tokens/semantic-colors.json) - 语义色定义
- [交互色规范](../../foundations/tokens/semantic-colors.md#interactive-colors) - 交互色使用指南

---

## 12. 更新日志

| 版本 | 日期 | 更新内容 |
|------|------|---------|
| v1.0 | 2025-11-17 | 初始版本，完整的 Button 组件设计规范 |

---

**文档版本：** v1.0
**最后更新：** 2025-11-17
**维护者：** 设计系统团队
**审核状态：** ✅ 已审核
