# Input 输入框

> 通过键盘输入单行文本的基础表单组件，是 B 端系统中使用频率最高的表单控件。

---

## 1. 何时使用

### 适用场景

✅ **单行文本输入** - 姓名、邮箱、电话等
✅ **数字/金额输入** - 配合 InputNumber 使用
✅ **搜索功能** - 配合搜索图标和清除按钮
✅ **密码输入** - 使用密码模式
✅ **表单字段** - 表单中的各类输入字段
✅ **多行文本** - 使用 Textarea 变体

### 不要使用的场景

❌ **大段文本编辑** - 应使用富文本编辑器（Editor）
❌ **日期选择** - 应使用 DatePicker
❌ **下拉选择** - 应使用 Select
❌ **数字精确输入** - 应使用 InputNumber（带增减按钮）

### 替代方案

| 场景 | 推荐组件 | 说明 |
|------|---------|------|
| 日期时间 | `DatePicker` / `TimePicker` | 提供日历选择 |
| 下拉选择 | `Select` | 预定义选项 |
| 数字输入 | `InputNumber` | 带增减按钮，精确控制 |
| 搜索建议 | `AutoComplete` | 输入时显示建议 |
| 多行文本 | `Textarea` | Input 的多行变体 |

---

## 2. 解剖结构（Anatomy）

### 2.1 基础输入框

```
┌─────────────────────────────────────────────┐
│  ┌──────┬───────────────────────┬─────┐   │
│  │      │                       │     │   │
│  │ 前缀 │  输入区域（占位符）    │ 后缀 │   │
│  │      │                       │     │   │
│  └──────┴───────────────────────┴─────┘   │
└─────────────────────────────────────────────┘
   ↑      ↑                       ↑
   12px   Padding 12px            12px
```

### 2.2 完整结构（带所有可选元素）

```
Label (可选)
  ↓
┌─────────────────────────────────────────────┐
│  ┌─────┬──────┬──────────┬──────┬─────┐   │
│  │ 前  │      │          │      │ 后  │   │
│  │ 置  │ 前缀 │ 输入区域 │ 后缀 │ 置  │   │
│  │ 标  │      │          │      │ 操  │   │
│  │ 签  │      │          │      │ 作  │   │
│  └─────┴──────┴──────────┴──────┴─────┘   │
└─────────────────────────────────────────────┘
  ↓
帮助文本 / 错误提示 (可选)
```

### 2.3 元素说明

| 元素 | 名称 | 必需 | 说明 |
|------|------|------|------|
| Container | 容器 | ✅ | 包含所有子元素，定义边框、背景 |
| Input Field | 输入区域 | ✅ | 用户输入文本的区域 |
| Placeholder | 占位符 | ⚪ 推荐 | 输入提示文字 |
| Label | 标签 | ⚪ 推荐 | 字段名称（表单场景） |
| Prefix | 前缀 | ⚪ 可选 | 左侧图标或文字（如 ¥、🔍） |
| Suffix | 后缀 | ⚪ 可选 | 右侧图标或文字 |
| Addon Before | 前置标签 | ⚪ 可选 | 左侧文字或下拉框 |
| Addon After | 后置操作 | ⚪ 可选 | 右侧按钮或文字（如"搜索"） |
| Clear Button | 清除按钮 | ⚪ 可选 | ✕ 图标，清空输入内容 |
| Password Toggle | 密码可见切换 | ⚪ 可选 | 👁 图标，显示/隐藏密码 |
| Help Text | 帮助文本 | ⚪ 可选 | 字段说明（12px 灰色） |
| Error Message | 错误提示 | ⚪ 可选 | 验证错误信息（12px 红色） |

### 2.4 层级关系

```
Input (Component)
├─ Label (Optional)
├─ Input Container (Frame)
│  ├─ Addon Before (Optional)
│  ├─ Input Wrapper (Frame)
│  │  ├─ Prefix Icon/Text (Optional)
│  │  ├─ Input Field (Required)
│  │  ├─ Suffix Icon/Text (Optional)
│  │  └─ Clear Button (Optional)
│  └─ Addon After (Optional)
└─ Help Text / Error Message (Optional)
```

---

## 3. 尺寸与间距

### 3.1 三种尺寸规格

| 尺寸 | 高度 | 水平内边距 | 字号 | 行高 | 图标尺寸 | 使用场景 |
|------|------|-----------|------|------|---------|---------|
| **Large** | `40px` | `12px` | `16px` | `24px` | `20px` | 移动端、重要表单 |
| **Middle** | `32px` | `12px` | `14px` | `20px` | `16px` | 默认尺寸，最常用 |
| **Small** | `24px` | `8px` | `12px` | `16px` | `14px` | 紧凑布局、表格内输入 |

### 3.2 详细间距规范（基于 4px 网格）

#### 水平间距

```
Large (40px):
┌─12px─┬──────┬─8px─┬──────────┬─8px─┬──────┬─12px─┐
│ 前置 │ 前缀 │     │ 输入区域 │     │ 后缀 │ 后置 │
└──────┴──────┴─────┴──────────┴─────┴──────┴──────┘

Middle (32px):
┌─12px─┬──────┬─8px─┬──────────┬─8px─┬──────┬─12px─┐
│ 前置 │ 前缀 │     │ 输入区域 │     │ 后缀 │ 后置 │
└──────┴──────┴─────┴──────────┴─────┴──────┴──────┘

Small (24px):
┌─8px──┬──────┬─4px─┬──────────┬─4px─┬──────┬─8px──┐
│ 前置 │ 前缀 │     │ 输入区域 │     │ 后缀 │ 后置 │
└──────┴──────┴─────┴──────────┴─────┴──────┴──────┘
```

**Token 映射：**
- Large/Middle 内边距: `spacing-3` (12px)
- Small 内边距: `spacing-2` (8px)
- 前缀/后缀与输入区域间距: `spacing-2` (8px，Small 为 4px)

#### 垂直间距（表单场景）

```
Label
  ↓ 8px
Input
  ↓ 4px
Help Text / Error Message
  ↓ 24px (下一个表单项)
```

**Token 映射：**
- Label 与 Input 间距: `spacing-2` (8px)
- Input 与帮助文本间距: `spacing-1` (4px)
- 表单项间距: `spacing-6` (24px)

### 3.3 宽度规则

| 类型 | 宽度 | Figma 设置 | 使用场景 |
|------|------|-----------|---------|
| 默认 | `200px` | `Fixed (200px)` | 姓名、编号等短字段 |
| 标准 | `320px` | `Fixed (320px)` | 邮箱、地址等中等字段 |
| 宽 | `480px` | `Fixed (480px)` | 备注等较长字段 |
| 全宽 | `100%` | `Fill container` | 移动端、弹窗表单 |

**B 端推荐宽度：**
- 姓名/编号: `160px`
- 手机号: `200px`
- 邮箱: `280px`
- 地址: `400px`

### 3.4 Textarea 尺寸

| 尺寸 | 最小高度 | 行数 | 说明 |
|------|---------|------|------|
| 默认 | `80px` | 4 行 | 短文本 |
| 中 | `120px` | 6 行 | 备注、描述 |
| 大 | `200px` | 10 行 | 长文本 |

**可调整大小：**
- 垂直方向: `resize: vertical`（推荐）
- 水平方向: `resize: horizontal`
- 双向: `resize: both`
- 禁用: `resize: none`

---

## 4. 视觉规范

### 4.1 颜色规范（Design Token 映射）

#### 基础输入框

| 状态 | 背景色 | 文字色 | 边框 | 占位符 | Token |
|------|--------|--------|------|--------|-------|
| **Default** | `#FFFFFF` | `#212121` (Grey 900) | `1px solid #D9D9D9` (Grey 350) | `#BDBDBD` (Grey 400) | `background-primary` + `border-default` |
| **Hover** | `#FFFFFF` | `#212121` | `1px solid #1976D2` (Blue 600) | `#BDBDBD` | `border-primary` |
| **Focus** | `#FFFFFF` | `#212121` | `1px solid #1976D2` + `4px shadow` | 隐藏 | `border-primary` + `focus-shadow` |
| **Filled** | `#FFFFFF` | `#212121` | `1px solid #D9D9D9` | - | `text-primary` |
| **Disabled** | `#F5F5F5` (Grey 100) | `#BDBDBD` (Grey 400) | `1px solid #D9D9D9` | `#E0E0E0` | `background-disabled` |
| **Error** | `#FFFFFF` | `#212121` | `1px solid #D32F2F` (Red 700) | `#BDBDBD` | `border-error` |
| **Warning** | `#FFFFFF` | `#212121` | `1px solid #F57C00` (Orange 700) | `#BDBDBD` | `border-warning` |
| **Success** | `#FFFFFF` | `#212121` | `1px solid #388E3C` (Green 700) | `#BDBDBD` | `border-success` |

#### Focus Shadow（聚焦阴影）

```css
box-shadow: 0 0 0 4px rgba(25, 118, 210, 0.12);
```

**Token 映射：**
- 颜色: `{color.blue.600}` + 12% opacity
- 扩散: `4px`

#### 前缀/后缀颜色

| 元素 | 颜色 | Token |
|------|------|-------|
| 前缀文字 | `#757575` (Grey 600) | `text-secondary` |
| 前缀图标 | `#757575` (Grey 600) | `icon-secondary` |
| 后缀文字 | `#757575` (Grey 600) | `text-secondary` |
| 后缀图标 | `#757575` (Grey 600) | `icon-secondary` |
| 清除按钮 - Default | `#BDBDBD` (Grey 400) | `icon-tertiary` |
| 清除按钮 - Hover | `#757575` (Grey 600) | `icon-secondary` |

#### 帮助文本/错误提示

| 类型 | 颜色 | 字号 | Token |
|------|------|------|-------|
| 帮助文本 | `#757575` (Grey 600) | `12px` | `text-secondary` |
| 错误提示 | `#D32F2F` (Red 700) | `12px` | `functional-error-text` |
| 警告提示 | `#F57C00` (Orange 700) | `12px` | `functional-warning-text` |
| 成功提示 | `#388E3C` (Green 700) | `12px` | `functional-success-text` |

### 4.2 文字规范

#### 输入文字

| 尺寸 | 字号 | 行高 | 字重 | 颜色 | Token |
|------|------|------|------|------|-------|
| Large | `16px` | `24px` | `400 Regular` | `#212121` | `font-size-lg` |
| Middle | `14px` | `20px` | `400 Regular` | `#212121` | `font-size-base` |
| Small | `12px` | `16px` | `400 Regular` | `#212121` | `font-size-sm` |

#### 占位符（Placeholder）

| 尺寸 | 字号 | 颜色 | 透明度 |
|------|------|------|--------|
| Large | `16px` | `#BDBDBD` (Grey 400) | `100%` |
| Middle | `14px` | `#BDBDBD` | `100%` |
| Small | `12px` | `#BDBDBD` | `100%` |

#### Label 标签

| 类型 | 字号 | 字重 | 颜色 | Token |
|------|------|------|------|-------|
| 默认 | `14px` | `400 Regular` | `#212121` | `text-primary` |
| 必填 | `14px` + `*` | `400 Regular` | `#D32F2F` (星号) | `functional-error` |

**必填标记：**
```
姓名 *     ← 星号红色 (#D32F2F)
```

#### 帮助文本/错误提示

| 类型 | 字号 | 行高 | Token |
|------|------|------|-------|
| 所有 | `12px` | `16px` | `font-size-sm` |

### 4.3 图标规范

#### 图标尺寸

| 输入框尺寸 | 图标尺寸 | Token |
|-----------|---------|-------|
| Large | `20px` | `icon-size-lg` |
| Middle | `16px` | `icon-size-base` |
| Small | `14px` | `icon-size-sm` |

#### 常用图标

| 场景 | 图标 | 位置 | 说明 |
|------|------|------|------|
| 搜索 | 🔍 Search | Prefix | 搜索框 |
| 密码 | 👁 Eye / Eye Off | Suffix | 切换密码可见性 |
| 清除 | ✕ Close | Suffix | 清空输入内容 |
| 用户 | 👤 User | Prefix | 用户名输入 |
| 邮箱 | ✉ Mail | Prefix | 邮箱输入 |
| 锁 | 🔒 Lock | Prefix | 密码输入 |
| 日历 | 📅 Calendar | Suffix | 日期输入（建议用 DatePicker） |

### 4.4 其他视觉元素

#### 圆角

| 尺寸 | 圆角 | Token |
|------|------|-------|
| 所有 | `4px` | `borderRadius-base` |

#### 边框

| 元素 | 宽度 | 样式 | Token |
|------|------|------|-------|
| 默认边框 | `1px` | `solid` | `borderWidth-base` |
| Focus 外框 | `4px` | `box-shadow` | `focus-shadow-spread` |

#### 字符计数器

```
┌─────────────────────────────────┐
│  输入内容...              45/100 │  ← 右下角显示
└─────────────────────────────────┘
```

**样式：**
- 字号: `12px`
- 颜色: `#757575` (Grey 600)
- 超出限制: `#D32F2F` (Red 700)

---

## 5. 组件状态（States）

### 5.1 状态总览

| 状态 | 触发条件 | 视觉变化 | 交互能力 |
|------|---------|---------|---------|
| **Empty** | 无内容 | 显示占位符 | ✅ 可输入 |
| **Hover** | 鼠标悬停 | 边框变蓝 | ✅ 可输入 |
| **Focus** | 点击/Tab 聚焦 | 边框变蓝 + 阴影 | ✅ 可输入 |
| **Filled** | 有内容 | 隐藏占位符 | ✅ 可输入 |
| **Disabled** | `disabled={true}` | 灰色背景 + 灰色文字 | ❌ 不可输入 |
| **Read-only** | `readOnly={true}` | 正常样式，无边框变化 | ❌ 不可输入（可选中） |
| **Error** | 验证失败 | 红色边框 + 错误提示 | ✅ 可输入 |
| **Warning** | 警告提示 | 橙色边框 + 警告提示 | ✅ 可输入 |
| **Success** | 验证成功 | 绿色边框 + 成功提示 | ✅ 可输入 |
| **Loading** | 异步验证中 | 右侧 Loading 图标 | ✅ 可输入 |

### 5.2 状态优先级

```
Disabled > Read-only > Error > Warning > Success > Focus > Hover > Empty/Filled
```

### 5.3 状态详解

#### Empty（空态）

```
┌─────────────────────────────────┐
│  请输入用户名                   │  ← 占位符显示
└─────────────────────────────────┘
```

**特征：**
- 显示占位符
- 边框灰色 (#D9D9D9)
- 可显示清除按钮（如果有内容）

#### Hover（悬停态）

```
┌─────────────────────────────────┐
│  请输入用户名                   │  ← 边框变蓝
└─────────────────────────────────┘
```

**视觉变化：**
- 边框颜色: `#D9D9D9` → `#1976D2`
- 过渡时间: `200ms`
- 光标: `text`

#### Focus（聚焦态）

```
┌─────────────────────────────────┐
│  |                              │  ← 光标闪烁 + 蓝色阴影
└─────────────────────────────────┘
  ↑
4px 蓝色阴影
```

**视觉变化：**
- 边框颜色: `#1976D2`
- 外阴影: `0 0 0 4px rgba(25, 118, 210, 0.12)`
- 占位符消失
- 光标闪烁

**键盘操作：**
- 输入字符: 正常输入
- `Backspace`: 删除字符
- `Ctrl+A` / `Cmd+A`: 全选
- `Ctrl+C` / `Cmd+C`: 复制
- `Ctrl+V` / `Cmd+V`: 粘贴
- `Enter`: 提交表单（如果在 Form 中）
- `Esc`: 取消聚焦（可选）

#### Filled（已填充）

```
┌─────────────────────────────────┐
│  张三                         ✕ │  ← 显示清除按钮
└─────────────────────────────────┘
```

**特征：**
- 占位符隐藏
- 显示输入内容
- 鼠标悬停时显示清除按钮（`allowClear={true}`）

#### Disabled（禁用态）

```
┌─────────────────────────────────┐
│  不可编辑的内容                 │  ← 灰色背景
└─────────────────────────────────┘
```

**视觉特征：**
- 背景: `#F5F5F5` (Grey 100)
- 文字: `#BDBDBD` (Grey 400)
- 边框: `#D9D9D9` (Grey 350)
- 光标: `not-allowed`
- 所有交互禁用

#### Read-only（只读态）

```
┌─────────────────────────────────┐
│  只读内容（可选中复制）         │
└─────────────────────────────────┘
```

**特征：**
- 正常背景（白色）
- 文字可选中
- 不可编辑
- 无边框 Hover 效果
- 光标: `text`（不是 `not-allowed`）

#### Error（错误态）

```
┌─────────────────────────────────┐
│  invalid@email                  │  ← 红色边框
└─────────────────────────────────┘
  ❌ 请输入有效的邮箱地址
```

**视觉特征：**
- 边框: `#D32F2F` (Red 700)
- 错误提示: 12px 红色文字
- 可选：右侧显示错误图标 ❌

#### Warning（警告态）

```
┌─────────────────────────────────┐
│  123456                         │  ← 橙色边框
└─────────────────────────────────┘
  ⚠️ 密码强度较弱
```

**视觉特征：**
- 边框: `#F57C00` (Orange 700)
- 警告提示: 12px 橙色文字

#### Success（成功态）

```
┌─────────────────────────────────┐
│  user@example.com              ✓│  ← 绿色边框 + 成功图标
└─────────────────────────────────┘
  ✅ 邮箱可用
```

**视觉特征：**
- 边框: `#388E3C` (Green 700)
- 成功提示: 12px 绿色文字
- 右侧显示成功图标 ✓

#### Loading（加载态）

```
┌─────────────────────────────────┐
│  user@example.com              ⊙│  ← Loading 图标
└─────────────────────────────────┘
  验证中...
```

**视觉特征：**
- 右侧显示旋转的 Loading 图标
- 提示文字: "验证中..."
- 可继续输入

### 5.4 状态转换动画

| 转换 | 过渡时间 | 缓动函数 | Token |
|------|---------|---------|-------|
| Default → Hover | `200ms` | `cubic-bezier(0.4, 0, 0.2, 1)` | `duration-short` |
| Hover → Focus | `200ms` | `cubic-bezier(0.4, 0, 0.2, 1)` | `duration-short` |
| 任意 → Error | `0ms` | - | 立即切换 |
| 任意 → Disabled | `0ms` | - | 立即切换 |
| 清除内容 | `100ms` | `ease-out` | `duration-fastest` |

---

## 6. 组件变体（Figma Variants）

### 6.1 Variants 属性配置

| 属性名 | 属性值 | 默认值 | 说明 |
|--------|--------|--------|------|
| **Type** | Text / Password / Search / Textarea | `Text` | 输入框类型 |
| **Size** | Large / Middle / Small | `Middle` | 输入框尺寸 |
| **State** | Empty / Hover / Focus / Filled / Disabled / Error / Success | `Empty` | 交互状态 |
| **Prefix** | None / Icon / Text | `None` | 前缀类型 |
| **Suffix** | None / Icon / Clear / Password | `None` | 后缀类型 |
| **Addon** | None / Before / After / Both | `None` | 前后置标签 |

### 6.2 特殊变体

#### Password（密码输入）

```
┌─────────────────────────────────┐
│  🔒 ••••••••                  👁 │  ← 密码隐藏
└─────────────────────────────────┘

点击 👁 后:
┌─────────────────────────────────┐
│  🔒 password123               👁 │  ← 密码显示
└─────────────────────────────────┘
```

#### Search（搜索框）

```
┌─────────────────────────────────┐
│  🔍 搜索...                    ✕ │
└─────────────────────────────────┘
```

#### Textarea（多行文本）

```
┌─────────────────────────────────┐
│  请输入备注...                  │
│                                 │
│                                 │
│                            0/200│  ← 字符计数
└─────────────────────────────────┘
```

#### 前后置标签

```
┌──────┬──────────────────────┬──────┐
│ http │ www.example.com      │ .com │
└──────┴──────────────────────┴──────┘
  ↑                              ↑
前置标签                      后置标签
```

### 6.3 Variants 组合数量

```
基础组合 = 4 (Type) × 3 (Size) × 7 (State) × 4 (Prefix) × 4 (Suffix) × 4 (Addon)
         = 5,376 个组合（理论值）

实际建议：创建 100-150 个常用组合
```

### 6.4 命名规范

```
格式：Type / Size / State / Prefix / Suffix

示例：
- Text / Middle / Empty / None / None
- Password / Middle / Filled / Icon / Password
- Search / Large / Focus / Icon / Clear
```

---

## 7. Figma Auto Layout 配置

### 7.1 Input Container 设置

```
Frame 名称: Input/Text/Middle/Empty

Auto Layout:
├─ Direction: Horizontal (→)
├─ Spacing:
│  ├─ Prefix → Input: 8px
│  └─ Input → Suffix: 8px
├─ Padding:
│  ├─ Large:  12px (左右)
│  ├─ Middle: 12px (左右)
│  └─ Small:  8px (左右)
├─ Alignment:
│  ├─ Horizontal: Left
│  └─ Vertical: Center
└─ Resizing:
   ├─ Horizontal: Fixed (200px / 320px / Fill container)
   └─ Vertical: Fixed (40px / 32px / 24px)
```

### 7.2 Input Field 设置

```
Text Layer:
├─ Font: Inter / PingFang SC
├─ Weight: 400 (Regular)
├─ Size: 16px / 14px / 12px
├─ Line height: 24px / 20px / 16px
├─ Alignment: Left
├─ Resizing: Fill container (横向拉伸)
└─ Constraints: Top & Bottom (垂直居中)
```

### 7.3 Textarea 设置

```
Frame 名称: Textarea/Middle/Empty

Auto Layout:
├─ Direction: Vertical (↓)
├─ Padding: 12px
├─ Resizing:
│  ├─ Horizontal: Fill container
│  └─ Vertical: Fixed (80px+) 或 Hug contents
└─ Vertical alignment: Top
```

---

## 8. Design Token 完整映射表

### 8.1 颜色 Token

| 元素 | Token 变量 | 亮色模式 | 暗色模式 |
|------|-----------|---------|---------|
| 背景 - Default | `input-bg` | `{color.grey.50}` #FAFAFA | `{color.grey.800}` #424242 |
| 背景 - Disabled | `input-bg-disabled` | `{color.grey.100}` #F5F5F5 | `{color.grey.700}` #616161 |
| 文字 - Default | `input-text` | `{color.grey.900}` #212121 | `{color.grey.50}` #FAFAFA |
| 文字 - Disabled | `input-text-disabled` | `{color.grey.400}` #BDBDBD | `{color.grey.500}` #9E9E9E |
| 占位符 | `input-placeholder` | `{color.grey.400}` #BDBDBD | `{color.grey.600}` #757575 |
| 边框 - Default | `input-border` | `{color.grey.350}` #D9D9D9 | `{color.grey.600}` #757575 |
| 边框 - Hover | `input-border-hover` | `{color.blue.600}` #1976D2 | `{color.blue.500}` #2196F3 |
| 边框 - Focus | `input-border-focus` | `{color.blue.600}` #1976D2 | `{color.blue.500}` #2196F3 |
| 边框 - Error | `input-border-error` | `{color.red.700}` #D32F2F | `{color.red.600}` #E53935 |
| 边框 - Warning | `input-border-warning` | `{color.orange.700}` #F57C00 | `{color.orange.600}` #FB8C00 |
| 边框 - Success | `input-border-success` | `{color.green.700}` #388E3C | `{color.green.600}` #43A047 |
| Focus Shadow | `input-focus-shadow` | `rgba(25, 118, 210, 0.12)` | `rgba(33, 150, 243, 0.12)` |
| 前缀/后缀文字 | `input-addon-text` | `{color.grey.600}` #757575 | `{color.grey.400}` #BDBDBD |
| 前缀/后缀背景 | `input-addon-bg` | `{color.grey.100}` #F5F5F5 | `{color.grey.700}` #616161 |
| 帮助文本 | `input-help-text` | `{color.grey.600}` #757575 | `{color.grey.400}` #BDBDBD |
| 错误提示 | `input-error-text` | `{color.red.700}` #D32F2F | `{color.red.500}` #F44336 |

### 8.2 间距 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| Large 内边距 | `spacing-3` | `12px` |
| Middle 内边距 | `spacing-3` | `12px` |
| Small 内边距 | `spacing-2` | `8px` |
| Prefix 间距 | `spacing-2` | `8px` |
| Suffix 间距 | `spacing-2` | `8px` |
| Label 与 Input 间距 | `spacing-2` | `8px` |
| Input 与帮助文本间距 | `spacing-1` | `4px` |
| 表单项间距 | `spacing-6` | `24px` |

### 8.3 文字 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| Large 字号 | `font-size-lg` | `16px` |
| Middle 字号 | `font-size-base` | `14px` |
| Small 字号 | `font-size-sm` | `12px` |
| 字重 | `font-weight-normal` | `400` |
| Large 行高 | `line-height-lg` | `24px` |
| Middle 行高 | `line-height-base` | `20px` |
| Small 行高 | `line-height-sm` | `16px` |
| 帮助文本字号 | `font-size-xs` | `12px` |

### 8.4 其他 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| 圆角 | `borderRadius-base` | `4px` |
| 边框宽度 | `borderWidth-base` | `1px` |
| Focus Shadow 扩散 | `focus-shadow-spread` | `4px` |
| Hover 过渡时间 | `duration-short` | `200ms` |
| 缓动函数 | `ease-in-out` | `cubic-bezier(0.4, 0, 0.2, 1)` |

---

## 9. 设计最佳实践

### 9.1 Do's（推荐做法）

#### ✅ 清晰的 Label 和占位符

```
✅ 正确：
姓名 *
┌─────────────────────────────────┐
│  请输入您的真实姓名             │
└─────────────────────────────────┘

❌ 错误：
┌─────────────────────────────────┐
│  姓名                           │  ← Label 放在输入框内
└─────────────────────────────────┘
```

**说明：**
- Label 始终在输入框上方或左侧
- 占位符用于补充说明，不能替代 Label
- 必填字段使用红色星号 *

#### ✅ 合理的字段宽度

```
✅ 正确：
手机号
┌──────────────┐
│ 138****1234  │  ← 200px（适合手机号长度）
└──────────────┘

邮箱
┌────────────────────────────┐
│ user@example.com           │  ← 280px（适合邮箱长度）
└────────────────────────────┘

❌ 错误：
手机号
┌──────────────────────────────────────┐
│ 138****1234                          │  ← 过宽
└──────────────────────────────────────┘
```

**宽度建议：**
- 字段宽度应匹配预期内容长度
- 避免所有字段都使用相同宽度

#### ✅ 即时验证反馈

```
✅ 正确：
邮箱
┌─────────────────────────────────┐
│  invalid@                      │  ← 输入时即时验证
└─────────────────────────────────┘
  ❌ 请输入有效的邮箱地址

❌ 错误：
只在提交时验证，用户需要返回修改多个错误
```

#### ✅ 合理使用前后缀

```
✅ 正确：
价格
┌─┬──────────────────────────┐
│¥│ 100.00                  │  ← 前缀说明单位
└─┴──────────────────────────┘

网址
┌──────┬──────────────┬──────┐
│ http │ example      │ .com │  ← 前后置标签
└──────┴──────────────┴──────┘

❌ 错误：
价格
┌─────────────────────────────────┐
│  请输入价格（单位：元）         │  ← 占位符太长
└─────────────────────────────────┘
```

#### ✅ 搜索框设计

```
✅ 正确：
┌─────────────────────────────────┐
│  🔍 搜索商品名称/编号          ✕│  ← 前缀图标 + 清除按钮
└─────────────────────────────────┘

输入后:
┌─────────────────────────────────┐
│  🔍 iPhone                     ✕│
└─────────────────────────────────┘
```

### 9.2 Don'ts（不推荐做法）

#### ❌ 占位符替代 Label

```
❌ 错误（无 Label）：
┌─────────────────────────────────┐
│  请输入姓名                     │  ← 用户输入后不知道是什么字段
└─────────────────────────────────┘

✅ 正确（有 Label）：
姓名
┌─────────────────────────────────┐
│  张三                           │  ← 清晰明了
└─────────────────────────────────┘
```

#### ❌ 过长的占位符

```
❌ 错误：
┌──────────────────────────────────────────┐
│  请输入您的真实姓名，不超过 20 个字符... │  ← 太长
└──────────────────────────────────────────┘

✅ 正确：
姓名 *
┌─────────────────────────────────┐
│  请输入真实姓名                 │
└─────────────────────────────────┘
  最多 20 个字符
```

#### ❌ 错误提示不明确

```
❌ 错误：
邮箱
┌─────────────────────────────────┐
│  invalid                        │
└─────────────────────────────────┘
  ❌ 输入错误

✅ 正确：
邮箱
┌─────────────────────────────────┐
│  invalid                        │
└─────────────────────────────────┘
  ❌ 请输入有效的邮箱地址（如：user@example.com）
```

#### ❌ 禁用态和只读态混淆

```
❌ 错误：
Disabled 和 Read-only 视觉一样

✅ 正确：
Disabled:  灰色背景 + 灰色文字 + 不可选中
Read-only: 白色背景 + 黑色文字 + 可选中复制
```

### 9.3 常见场景最佳实践

#### 登录表单

```
用户名
┌─────────────────────────────────┐
│  👤 请输入用户名/邮箱/手机号    │
└─────────────────────────────────┘

密码
┌─────────────────────────────────┐
│  🔒 ••••••••                  👁│
└─────────────────────────────────┘
  忘记密码？

[登录]
```

#### 搜索框

```
┌──────────────────────────────────┬─────┐
│  🔍 搜索商品名称、编号或品牌    ✕│ 搜索 │
└──────────────────────────────────┴─────┘
```

#### 表单验证

```
邮箱 *
┌─────────────────────────────────┐
│  user@example.com              ✓│  ← 实时验证成功
└─────────────────────────────────┘
  ✅ 邮箱可用

密码 *
┌─────────────────────────────────┐
│  123456                         │
└─────────────────────────────────┘
  ⚠️ 密码强度：弱（建议使用字母+数字+符号）

确认密码 *
┌─────────────────────────────────┐
│  123                            │
└─────────────────────────────────┘
  ❌ 两次输入的密码不一致
```

#### 金额输入

```
转账金额
┌─┬──────────────────────────┬───┐
│¥│ 1000.00                  │ 元│
└─┴──────────────────────────┴───┘
  账户余额：¥5,280.00
```

#### 多行文本（备注）

```
备注
┌─────────────────────────────────┐
│  请输入备注信息...              │
│                                 │
│                                 │
│                           0/200 │  ← 字符计数
└─────────────────────────────────┘
```

### 9.4 可访问性最佳实践

#### ✅ 完整的 ARIA 属性

```html
<input
  type="text"
  id="username"
  name="username"
  aria-label="用户名"
  aria-required="true"
  aria-invalid="false"
  aria-describedby="username-help"
  placeholder="请输入用户名"
/>
<span id="username-help">用户名为 4-16 位字符</span>
```

#### ✅ 错误状态的可访问性

```html
<!-- 错误状态 -->
<input
  type="email"
  aria-invalid="true"
  aria-errormessage="email-error"
/>
<span id="email-error" role="alert">
  请输入有效的邮箱地址
</span>
```

#### ✅ 键盘导航

| 按键 | 功能 |
|------|------|
| `Tab` | 聚焦到输入框 |
| `Shift + Tab` | 反向聚焦 |
| `Enter` | 提交表单（文本输入框）<br>换行（Textarea） |
| `Ctrl/Cmd + A` | 全选 |
| `Ctrl/Cmd + C/V/X` | 复制/粘贴/剪切 |
| `Esc` | 清除输入（可选） |

---

## 10. 代码示例（组件 API）

### 10.1 基础用法

```tsx
// 基础输入框
<Input placeholder="请输入内容" />

// 带默认值
<Input defaultValue="初始内容" />

// 受控组件
<Input value={value} onChange={handleChange} />
```

### 10.2 尺寸

```tsx
<Input size="large" placeholder="大尺寸" />
<Input size="middle" placeholder="中尺寸（默认）" />
<Input size="small" placeholder="小尺寸" />
```

### 10.3 前后缀

```tsx
// 前缀图标
<Input prefix={<UserIcon />} placeholder="用户名" />

// 后缀图标
<Input suffix={<CheckIcon />} placeholder="邮箱" />

// 前后置标签
<Input addonBefore="http://" addonAfter=".com" />

// 前置下拉框
<Input
  addonBefore={
    <Select defaultValue="http://">
      <Option value="http://">http://</Option>
      <Option value="https://">https://</Option>
    </Select>
  }
  placeholder="www.example.com"
/>
```

### 10.4 特殊类型

```tsx
// 密码输入
<Input.Password placeholder="请输入密码" />

// 搜索框
<Input.Search
  placeholder="搜索..."
  onSearch={handleSearch}
  enterButton
/>

// 多行文本
<Input.TextArea
  rows={4}
  placeholder="请输入备注"
  maxLength={200}
  showCount
/>
```

### 10.5 状态

```tsx
// 禁用
<Input disabled placeholder="禁用状态" />

// 只读
<Input readOnly value="只读内容" />

// 允许清除
<Input allowClear placeholder="可清除" />

// 最大长度
<Input maxLength={20} showCount placeholder="最多 20 字符" />
```

### 10.6 验证状态

```tsx
// 错误
<Input status="error" placeholder="错误状态" />

// 警告
<Input status="warning" placeholder="警告状态" />

// 自定义验证（配合 Form.Item）
<Form.Item
  name="email"
  label="邮箱"
  rules={[
    { required: true, message: '请输入邮箱' },
    { type: 'email', message: '邮箱格式不正确' }
  ]}
  help="请输入有效的邮箱地址"
>
  <Input placeholder="user@example.com" />
</Form.Item>
```

### 10.7 完整 API

```typescript
interface InputProps {
  // 基础属性
  type?: 'text' | 'password' | 'email' | 'number' | 'tel' | 'url';
  value?: string;
  defaultValue?: string;
  placeholder?: string;

  // 尺寸
  size?: 'large' | 'middle' | 'small';

  // 前后缀
  prefix?: ReactNode;
  suffix?: ReactNode;
  addonBefore?: ReactNode;
  addonAfter?: ReactNode;

  // 状态
  disabled?: boolean;
  readOnly?: boolean;
  status?: 'error' | 'warning';
  allowClear?: boolean;

  // 长度限制
  maxLength?: number;
  showCount?: boolean;

  // 事件
  onChange?: (e: React.ChangeEvent<HTMLInputElement>) => void;
  onPressEnter?: (e: React.KeyboardEvent<HTMLInputElement>) => void;
  onFocus?: (e: React.FocusEvent<HTMLInputElement>) => void;
  onBlur?: (e: React.FocusEvent<HTMLInputElement>) => void;

  // HTML 属性
  id?: string;
  name?: string;
  autoComplete?: string;
  autoFocus?: boolean;

  // 其他
  className?: string;
  style?: React.CSSProperties;
}

// Textarea
interface TextAreaProps extends Omit<InputProps, 'prefix' | 'suffix'> {
  rows?: number;
  autoSize?: boolean | { minRows: number; maxRows: number };
}

// Password
interface PasswordProps extends InputProps {
  visibilityToggle?: boolean;
  iconRender?: (visible: boolean) => ReactNode;
}

// Search
interface SearchProps extends InputProps {
  enterButton?: boolean | ReactNode;
  loading?: boolean;
  onSearch?: (value: string) => void;
}
```

---

## 11. 相关资源

### 组件依赖

| 组件 | 说明 |
|------|------|
| Icon | 前后缀图标 |
| Button | Search 输入框的搜索按钮 |
| Form | 表单验证 |

### 相关组件

| 组件 | 使用场景 |
|------|---------|
| InputNumber | 数字输入（带增减按钮） |
| Select | 下拉选择 |
| AutoComplete | 输入建议 |
| DatePicker | 日期选择 |
| Mentions | @提及功能 |

### Design Token 文档

- [tokens.json](../../foundations/tokens/tokens.json) - 完整 Token 定义
- [semantic-colors.json](../../foundations/tokens/semantic-colors.json) - 语义色定义
- [表单色规范](../../foundations/tokens/semantic-colors.md#functional-colors) - 功能色使用指南

---

## 12. 更新日志

| 版本 | 日期 | 更新内容 |
|------|------|---------|
| v1.0 | 2025-11-17 | 初始版本，完整的 Input 组件设计规范 |

---

**文档版本：** v1.0
**最后更新：** 2025-11-17
**维护者：** 设计系统团队
**审核状态：** ✅ 已审核
