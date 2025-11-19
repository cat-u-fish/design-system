# Form 表单

> 表单容器组件，用于数据收集、验证和提交，统一管理表单项的布局、验证和交互逻辑。

---

## 1. 何时使用

### 适用场景

✅ **数据录入** - 用户注册、登录、信息编辑等场景
✅ **多字段验证** - 需要统一管理多个字段的验证逻辑
✅ **复杂表单** - 包含多种输入类型（文本、选择器、日期等）
✅ **表单联动** - 字段之间有依赖关系或联动逻辑
✅ **批量操作** - 统一提交、重置、回填等操作

### 不要使用的场景

❌ **单一搜索框** - 应使用独立的 Input 组件
❌ **简单筛选** - 1-2 个筛选条件，可直接使用 Input/Select
❌ **内联编辑** - 表格内直接编辑，使用 Editable Cell
❌ **问卷调查** - 应使用专门的 Survey 组件

### 替代方案

| 场景 | 推荐组件 | 说明 |
|------|---------|------|
| 单一输入框 | `Input` | 搜索框、单字段输入 |
| 筛选条件 | `Filter` | 列表筛选器 |
| 步骤表单 | `Steps` + `Form` | 多步骤向导式表单 |
| 动态表单 | `FormBuilder` | 根据配置动态生成表单 |

---

## 2. 解剖结构（Anatomy）

### 组件拆解

```
┌─────────────────────────────────────────────────┐
│  Form Container                                 │
│  ┌───────────────────────────────────────────┐  │
│  │  Form Item 1                              │  │
│  │  ┌─────────┬───────────────────────────┐  │  │
│  │  │ Label * │  [Input Field]            │  │  │
│  │  │         │  Helper Text              │  │  │
│  │  └─────────┴───────────────────────────┘  │  │
│  └───────────────────────────────────────────┘  │
│                  ↓ 16px 间距                    │
│  ┌───────────────────────────────────────────┐  │
│  │  Form Item 2                              │  │
│  │  ┌─────────┬───────────────────────────┐  │  │
│  │  │ Label   │  [Select Dropdown]        │  │  │
│  │  │         │  ❌ Error Message         │  │  │
│  │  └─────────┴───────────────────────────┘  │  │
│  └───────────────────────────────────────────┘  │
│                  ↓ 24px 间距                    │
│  ┌───────────────────────────────────────────┐  │
│  │  [Submit Button]  [Cancel Button]        │  │
│  └───────────────────────────────────────────┘  │
└─────────────────────────────────────────────────┘
```

### 元素说明

#### Form 层级元素

| 元素 | 名称 | 必需 | 说明 |
|------|------|------|------|
| **Form Container** | 表单容器 | ✅ | 包含所有表单项和操作按钮 |
| **Form Item** | 表单项 | ✅ | 单个字段的容器（Label + Input + Message） |
| **Label** | 标签 | ⚪ 可选 | 字段说明（通常必需，某些场景可隐藏） |
| **Required Mark** | 必填标记 | ⚪ 可选 | 红色星号 (*) |
| **Input Field** | 输入控件 | ✅ | 实际的输入组件（Input/Select/Checkbox等） |
| **Helper Text** | 辅助文本 | ⚪ 可选 | 字段说明或示例 |
| **Error Message** | 错误提示 | ⚪ 可选 | 验证失败时显示 |
| **Actions** | 操作区 | ⚪ 可选 | 提交、重置、取消等按钮 |

#### Form Item 结构

```
Form Item
├─ Label Area (左侧或顶部)
│  ├─ Required Mark (*)
│  ├─ Label Text
│  └─ Tooltip Icon (可选)
├─ Control Area (右侧或下方)
│  ├─ Input Component
│  └─ Addon (可选，如单位、图标)
└─ Message Area (底部)
   ├─ Helper Text (灰色提示)
   ├─ Error Message (红色错误)
   ├─ Warning Message (橙色警告)
   └─ Success Message (绿色成功)
```

### 层级关系

```
Form (Component)
├─ Form Container (Frame)
│  ├─ Form Item 1
│  │  ├─ Label + Required Mark
│  │  ├─ Input Field
│  │  └─ Helper/Error Message
│  ├─ Form Item 2
│  │  └─ ...
│  └─ Actions Area
│     ├─ Submit Button
│     └─ Cancel Button
```

---

## 3. 尺寸与间距

### 3.1 表单布局模式

#### 水平布局（Horizontal）

```
Label (120px)    Input (Auto)
┌──────────┬────────────────────────┐
│ 用户名 * │ [____________]         │
│ 密码     │ [____________]         │
│ 邮箱     │ [____________]         │
└──────────┴────────────────────────┘
```

| 属性 | 值 | Token | 说明 |
|------|-----|-------|------|
| Label 宽度 | `120px` | - | 可调整（80-200px） |
| Label-Input 间距 | `12px` | `spacing-3` | 固定间距 |
| Label 对齐 | `右对齐` | - | 冒号对齐 |

#### 垂直布局（Vertical）

```
Label
[____________]  ← Input 宽度 100%

Label
[____________]
```

| 属性 | 值 | Token | 说明 |
|------|-----|-------|------|
| Label-Input 间距 | `8px` | `spacing-2` | Label 在上方 |
| Input 宽度 | `100%` | - | Fill container |

#### 行内布局（Inline）

```
[Label Input]  [Label Input]  [Submit]
```

| 属性 | 值 | Token | 说明 |
|------|-----|-------|------|
| 表单项间距 | `16px` | `spacing-4` | 水平排列 |

### 3.2 间距规范

#### 表单项间距（基于 4px 网格）

| 间距类型 | 值 | Token | 使用场景 |
|---------|-----|-------|---------|
| **紧凑模式** | `12px` | `spacing-3` | 紧凑布局、弹窗表单 |
| **标准模式** | `16px` | `spacing-4` | 默认（90%场景） |
| **宽松模式** | `24px` | `spacing-6` | 强调区分、复杂表单 |

#### Form Item 内部间距

```
水平布局：
┌─ Label (120px) ─┬─ 12px ─┬─ Input ─┐
│ 用户名 *        │        │ [____]  │
└─────────────────┴────────┴─────────┘

垂直布局：
┌─ Label ─────────┐
│ 用户名 *        │
├─ 8px ───────────┤
│ [____________]  │
├─ 4px ───────────┤
│ 请输入用户名     │ ← Helper Text
└─────────────────┘
```

#### 操作区间距

```
Form Items
     ↓ 32px (spacing-8)
┌─────────────────────────┐
│ [Submit]  [Cancel]      │ ← Actions Area
└─────────────────────────┘
```

### 3.3 Label 规范

| 属性 | 水平布局 | 垂直布局 | Inline 布局 |
|------|---------|---------|------------|
| 宽度 | `120px` (固定) | `100%` (自适应) | `auto` (Hug) |
| 对齐 | `右对齐` | `左对齐` | `左对齐` |
| 必填标记位置 | `文字右侧` | `文字右侧` | `文字右侧` |
| 与 Input 间距 | `12px` | `8px` | `8px` |

### 3.4 错误提示间距

```
[Input Field]
     ↓ 4px
❌ 用户名不能为空  ← Error Message
```

| 属性 | 值 | Token |
|------|-----|-------|
| Input-Message 间距 | `4px` | `spacing-1` |
| Message 左边距 | `0px` (对齐 Input) | - |

---

## 4. 视觉规范

### 4.1 颜色规范

#### Label 颜色

| 状态 | 颜色 | Token | 说明 |
|------|------|-------|------|
| **Default** | `#424242` (Grey 800) | `text-secondary` | 默认灰色 |
| **Focused** | `#1976D2` (Blue 600) | `text-primary` | 聚焦时变蓝（可选） |
| **Disabled** | `#9E9E9E` (Grey 500) | `text-disabled` | 禁用态 |

#### 必填标记 (*)

| 属性 | 颜色 | Token | 说明 |
|------|------|-------|------|
| 必填星号 | `#D32F2F` (Red 700) | `error-primary` | 红色星号 |
| 字号 | `14px` | `font-size-base` | 与 Label 相同 |
| 位置 | Label 文字右侧 `4px` | `spacing-1` | 紧贴文字 |

#### 错误提示颜色

| 元素 | 颜色 | Token | 说明 |
|------|------|-------|------|
| 错误文字 | `#D32F2F` (Red 700) | `error-primary` | 错误信息 |
| 错误边框 | `#D32F2F` | `error-primary` | Input 边框变红 |
| 警告文字 | `#F57C00` (Orange 700) | `warning-primary` | 警告信息 |
| 成功文字 | `#388E3C` (Green 700) | `success-primary` | 验证成功 |
| 辅助文字 | `#757575` (Grey 600) | `text-tertiary` | Helper Text |

### 4.2 文字规范

#### Label 文字

| 属性 | 值 | Token | 说明 |
|------|-----|-------|------|
| 字号 | `14px` | `font-size-base` | 默认字号 |
| 行高 | `22px` | `line-height-base` | 行高 |
| 字重 | `400 Regular` | `font-weight-regular` | 不加粗 |
| 颜色 | `#424242` (Grey 800) | `text-secondary` | 次要文字色 |

#### Helper Text / Error Message

| 属性 | 值 | Token | 说明 |
|------|-----|-------|------|
| 字号 | `12px` | `font-size-sm` | 小字号 |
| 行高 | `20px` | `line-height-sm` | 行高 |
| 字重 | `400 Regular` | `font-weight-regular` | 不加粗 |

#### 文案规范

| 规则 | 说明 | 示例 |
|------|------|------|
| Label 简洁 | 2-8 个字符 | ✅ 用户名 ❌ 请输入您的用户名 |
| 必填标识 | 使用红色星号 (*) | ✅ 邮箱 * ❌ 邮箱（必填） |
| 错误提示 | 明确说明错误原因和解决方法 | ✅ 密码长度需 8-20 位 ❌ 格式错误 |
| Helper Text | 说明格式或示例 | "支持 jpg、png，最大 2MB" |

### 4.3 边框与分隔

#### Input 边框状态

| 状态 | 边框颜色 | Token | 说明 |
|------|---------|-------|------|
| **Default** | `#D9D9D9` (Grey 400) | `border-default` | 默认灰色 |
| **Hover** | `#1976D2` (Blue 600) | `border-primary` | 悬停变蓝 |
| **Focused** | `#1976D2` (Blue 600) | `border-primary` | 聚焦蓝色 |
| **Error** | `#D32F2F` (Red 700) | `error-primary` | 验证失败红色 |
| **Success** | `#388E3C` (Green 700) | `success-primary` | 验证成功绿色 |
| **Disabled** | `#E0E0E0` (Grey 300) | `border-disabled` | 禁用态 |

#### 分组分隔

```
┌─ 基本信息 ────────────────────┐
│ 用户名 [______]               │
│ 邮箱   [______]               │
└───────────────────────────────┘
     ↓ 24px
┌─ 详细信息 ────────────────────┐
│ 地址   [______]               │
│ 电话   [______]               │
└───────────────────────────────┘
```

| 属性 | 值 | Token | 说明 |
|------|-----|-------|------|
| 分组间距 | `24px` | `spacing-6` | 分组之间 |
| 分组标题字号 | `16px` | `font-size-lg` | 分组标题 |
| 分组标题字重 | `500 Medium` | `font-weight-medium` | 加粗 |

---

## 5. 组件状态（States）

### 5.1 Form Item 状态

| 状态 | 触发条件 | 视觉变化 | 说明 |
|------|---------|---------|------|
| **Default** | 未交互 | 默认样式 | 初始状态 |
| **Focused** | 聚焦输入框 | Input 边框变蓝 | 用户正在输入 |
| **Validating** | 验证中 | 显示 Loading 图标 | 异步验证（如检查用户名） |
| **Success** | 验证通过 | 绿色边框 + ✓ 图标 | 验证成功 |
| **Error** | 验证失败 | 红色边框 + 错误提示 | 验证失败 |
| **Warning** | 警告 | 橙色边框 + 警告提示 | 非阻断性警告 |
| **Disabled** | `disabled={true}` | 灰色，不可交互 | 禁用状态 |

### 5.2 验证时机

| 时机 | 说明 | 使用场景 |
|------|------|---------|
| **onChange** | 每次输入时验证 | 实时反馈（如密码强度） |
| **onBlur** | 失去焦点时验证 | 常规表单（默认推荐） |
| **onSubmit** | 提交时验证 | 简单表单 |
| **Manual** | 手动触发验证 | 自定义触发 |

### 5.3 状态优先级

```
Disabled > Error > Warning > Success > Validating > Focused > Default
```

### 5.4 错误提示方式

#### 内联错误提示（推荐）

```
[Input Field]
❌ 用户名不能为空  ← 在字段下方直接显示
```

#### Toast 错误提示

```
┌────────────────────────┐
│ ❌ 表单验证失败        │ ← 顶部 Toast
│   - 用户名不能为空     │
│   - 密码长度不足       │
└────────────────────────┘
```

#### 错误汇总（复杂表单）

```
┌─ 表单错误 (2) ────────────┐
│ • 用户名不能为空 → 跳转   │
│ • 邮箱格式错误   → 跳转   │
└───────────────────────────┘
```

---

## 6. 组件变体（Figma Variants）

### 6.1 Variants 属性配置

| 属性名 | 属性值 | 默认值 | 说明 |
|--------|--------|--------|------|
| **Layout** | Horizontal / Vertical / Inline | `Horizontal` | 布局模式 |
| **Size** | Large / Middle / Small | `Middle` | 表单项尺寸 |
| **State** | Default / Focused / Error / Success / Disabled | `Default` | 验证状态 |
| **Required** | True / False | `False` | 是否必填 |
| **LabelAlign** | Left / Right | `Right` (Horizontal) / `Left` (Vertical) | Label 对齐方式 |

### 6.2 Form Item Variants

```
格式：Layout / Size / State / Required

示例：
- Horizontal / Middle / Default / True
- Vertical / Large / Error / False
- Inline / Small / Success / True
```

### 6.3 变体决策树

```
选择 Layout
  ├─ Horizontal:  传统表单（PC 端）
  ├─ Vertical:    移动端、简单表单
  └─ Inline:      筛选条件、搜索框

选择 Size
  ├─ Large:       移动端、强调输入
  ├─ Middle:      默认（90% 场景）
  └─ Small:       紧凑布局、弹窗表单

选择 State
  ├─ Default:     默认状态
  ├─ Focused:     用户正在输入
  ├─ Error:       验证失败
  ├─ Success:     验证成功
  └─ Disabled:    禁用状态
```

---

## 7. Figma Auto Layout 配置

### 7.1 Form Container 设置

```
Frame 名称: Form/Horizontal/Middle

Auto Layout:
├─ Direction: Vertical (↓)
├─ Spacing: 16px (表单项间距)
├─ Padding: 24px (容器内边距)
├─ Alignment:
│  ├─ Horizontal: Left
│  └─ Vertical: Top
└─ Resizing:
   ├─ Horizontal: Fill container
   └─ Vertical: Hug contents
```

### 7.2 Form Item 设置（水平布局）

```
Frame 名称: Form Item/Horizontal

Auto Layout:
├─ Direction: Horizontal (→)
├─ Spacing: 12px (Label 与 Input 间距)
├─ Alignment:
│  ├─ Horizontal: Space between
│  └─ Vertical: Top
└─ Resizing:
   ├─ Horizontal: Fill container
   └─ Vertical: Hug contents

子元素:
├─ Label Area (120px Fixed)
│  ├─ Label Text
│  └─ Required Mark
└─ Control Area (Fill)
   ├─ Input Component
   └─ Helper/Error Message
```

### 7.3 Form Item 设置（垂直布局）

```
Frame 名称: Form Item/Vertical

Auto Layout:
├─ Direction: Vertical (↓)
├─ Spacing: 8px (Label 与 Input 间距)
├─ Alignment: Left
└─ Resizing:
   ├─ Horizontal: Fill container
   └─ Vertical: Hug contents
```

### 7.4 Actions Area 设置

```
Frame 名称: Form Actions

Auto Layout:
├─ Direction: Horizontal (→)
├─ Spacing: 12px (按钮间距)
├─ Padding: 32px (top) + 0px (其他)
├─ Alignment: Left / Center / Right (可选)
└─ Resizing: Fill container
```

---

## 8. Design Token 完整映射表

### 8.1 颜色 Token

| 元素 | Token 变量 | 亮色模式 | 暗色模式 |
|------|-----------|---------|---------|
| Label 文字 | `form-label-text` | `{color.grey.800}` #424242 | `{color.grey.200}` #EEEEEE |
| Label 必填标记 | `form-required-color` | `{color.red.700}` #D32F2F | `{color.red.500}` #F44336 |
| Helper Text | `form-helper-text` | `{color.grey.600}` #757575 | `{color.grey.400}` #BDBDBD |
| Error 文字 | `form-error-text` | `{color.red.700}` #D32F2F | `{color.red.400}` #EF5350 |
| Error 边框 | `form-error-border` | `{color.red.700}` #D32F2F | `{color.red.400}` #EF5350 |
| Warning 文字 | `form-warning-text` | `{color.orange.700}` #F57C00 | `{color.orange.400}` #FFA726 |
| Success 文字 | `form-success-text` | `{color.green.700}` #388E3C | `{color.green.400}` #66BB6A |
| Success 边框 | `form-success-border` | `{color.green.700}` #388E3C | `{color.green.400}` #66BB6A |
| Disabled 文字 | `form-disabled-text` | `{color.grey.500}` #9E9E9E | `{color.grey.500}` #9E9E9E |
| 分组标题 | `form-group-title` | `{color.grey.900}` #212121 | `{color.grey.100}` #F5F5F5 |

### 8.2 间距 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| 表单项间距 - 紧凑 | `form-item-spacing-compact` | `12px` (spacing-3) |
| 表单项间距 - 标准 | `form-item-spacing-default` | `16px` (spacing-4) |
| 表单项间距 - 宽松 | `form-item-spacing-loose` | `24px` (spacing-6) |
| Label-Input 间距 (水平) | `form-label-spacing-horizontal` | `12px` (spacing-3) |
| Label-Input 间距 (垂直) | `form-label-spacing-vertical` | `8px` (spacing-2) |
| Input-Message 间距 | `form-message-spacing` | `4px` (spacing-1) |
| 分组间距 | `form-group-spacing` | `24px` (spacing-6) |
| Actions 上间距 | `form-actions-spacing` | `32px` (spacing-8) |
| Label 宽度 | `form-label-width` | `120px` |

### 8.3 文字 Token

| 元素 | Token 变量 | 值 |
|------|-----------|-----|
| Label 字号 | `form-label-font-size` | `14px` (font-size-base) |
| Label 行高 | `form-label-line-height` | `22px` (line-height-base) |
| Label 字重 | `form-label-font-weight` | `400` (font-weight-regular) |
| Helper 字号 | `form-helper-font-size` | `12px` (font-size-sm) |
| Helper 行高 | `form-helper-line-height` | `20px` (line-height-sm) |
| 分组标题字号 | `form-group-title-font-size` | `16px` (font-size-lg) |
| 分组标题字重 | `form-group-title-font-weight` | `500` (font-weight-medium) |

---

## 9. 设计最佳实践

### 9.1 Do's（推荐做法）

#### ✅ 清晰的 Label

```
✅ 正确：
用户名 *  [____________]
邮箱 *    [____________]

❌ 错误：
请输入您的用户名 *  [____________]  ← Label 过长
```

#### ✅ 实时验证反馈

```
密码 *    [••••••]
          ❌ 密码长度需 8-20 位  ← 失去焦点时立即提示
```

#### ✅ 分组组织

```
┌─ 基本信息 ────────────┐
│ 姓名  [______]        │
│ 邮箱  [______]        │
└───────────────────────┘

┌─ 联系方式 ────────────┐
│ 电话  [______]        │
│ 地址  [______]        │
└───────────────────────┘
```

#### ✅ 明确的必填标识

```
✅ 正确：
用户名 *  ← 红色星号，简洁明确

❌ 错误：
用户名（必填）  ← 占用空间，不够突出
```

#### ✅ 辅助文本说明

```
头像     [Choose File]
         支持 jpg、png，最大 2MB  ← Helper Text
```

### 9.2 Don'ts（不推荐做法）

#### ❌ Label 与 Input 距离过远

```
❌ 错误：
用户名                        [______]  ← 间距过大

✅ 正确：
用户名  [______]  ← 12px 间距
```

#### ❌ 错误提示不明确

```
❌ 错误：
密码 [______]
     ❌ 格式错误  ← 用户不知道怎么改

✅ 正确：
密码 [______]
     ❌ 密码长度需 8-20 位，包含字母和数字
```

#### ❌ 过多的表单项

```
❌ 错误：
一个页面包含 30+ 个表单项  ← 用户疲劳

✅ 正确：
使用 Steps 拆分为 3-4 个步骤
或使用折叠面板（Collapse）分组
```

#### ❌ 垂直布局 Label 过长

```
❌ 错误（垂直布局）：
请输入您的用户名（2-20个字符，支持字母、数字、下划线）
[____________]  ← Label 过长

✅ 正确：
用户名 *
[____________]
2-20个字符，支持字母、数字、下划线  ← 放在 Helper Text
```

### 9.3 常见场景最佳实践

#### 登录表单

```tsx
<Form layout="vertical" size="large">
  <Form.Item label="用户名" required>
    <Input placeholder="请输入用户名" />
  </Form.Item>

  <Form.Item label="密码" required>
    <Input.Password placeholder="请输入密码" />
  </Form.Item>

  <Form.Item>
    <Checkbox>记住我</Checkbox>
    <a href="#" style={{ float: 'right' }}>忘记密码？</a>
  </Form.Item>

  <Form.Item>
    <Button type="primary" htmlType="submit" block>
      登录
    </Button>
  </Form.Item>
</Form>
```

#### 注册表单（分组）

```tsx
<Form layout="horizontal" labelCol={{ span: 6 }}>
  {/* 基本信息 */}
  <Divider>基本信息</Divider>
  <Form.Item label="用户名" required>
    <Input placeholder="2-20个字符" />
  </Form.Item>
  <Form.Item label="邮箱" required>
    <Input type="email" />
  </Form.Item>

  {/* 安全设置 */}
  <Divider>安全设置</Divider>
  <Form.Item label="密码" required>
    <Input.Password />
  </Form.Item>
  <Form.Item label="确认密码" required>
    <Input.Password />
  </Form.Item>

  <Form.Item wrapperCol={{ offset: 6 }}>
    <Button type="primary" htmlType="submit">
      注册
    </Button>
  </Form.Item>
</Form>
```

#### 筛选表单（Inline）

```tsx
<Form layout="inline">
  <Form.Item label="姓名">
    <Input placeholder="请输入" />
  </Form.Item>
  <Form.Item label="状态">
    <Select placeholder="请选择">
      <Option value="active">已激活</Option>
      <Option value="inactive">未激活</Option>
    </Select>
  </Form.Item>
  <Form.Item>
    <Button type="primary">搜索</Button>
    <Button>重置</Button>
  </Form.Item>
</Form>
```

#### 动态表单项

```tsx
<Form>
  <Form.List name="contacts">
    {(fields, { add, remove }) => (
      <>
        {fields.map(field => (
          <Form.Item key={field.key} label={`联系人 ${field.key + 1}`}>
            <Input placeholder="姓名" />
            <Button onClick={() => remove(field.name)}>删除</Button>
          </Form.Item>
        ))}
        <Button type="dashed" onClick={() => add()}>
          + 添加联系人
        </Button>
      </>
    )}
  </Form.List>
</Form>
```

### 9.4 可访问性最佳实践

#### ✅ 关联 Label 与 Input

```html
<label for="username">用户名 *</label>
<input id="username" name="username" aria-required="true" />
```

#### ✅ 错误提示关联

```html
<input
  id="email"
  aria-invalid="true"
  aria-describedby="email-error"
/>
<span id="email-error" role="alert">
  邮箱格式错误
</span>
```

#### ✅ 键盘导航

```
Tab:       聚焦到下一个表单项
Shift+Tab: 聚焦到上一个表单项
Enter:     提交表单（在最后一个字段或按钮上）
```

#### ✅ 屏幕阅读器支持

```html
<form role="form" aria-labelledby="form-title">
  <h2 id="form-title">用户注册</h2>

  <div role="group" aria-labelledby="basic-info">
    <h3 id="basic-info">基本信息</h3>
    <!-- 表单项 -->
  </div>
</form>
```

---

## 10. 代码示例（组件 API）

### 10.1 基础用法

```tsx
import { Form, Input, Button } from 'your-design-system';

function BasicForm() {
  const [form] = Form.useForm();

  const onFinish = (values) => {
    console.log('Success:', values);
  };

  return (
    <Form form={form} onFinish={onFinish}>
      <Form.Item
        label="用户名"
        name="username"
        rules={[{ required: true, message: '请输入用户名' }]}
      >
        <Input placeholder="请输入用户名" />
      </Form.Item>

      <Form.Item
        label="密码"
        name="password"
        rules={[{ required: true, message: '请输入密码' }]}
      >
        <Input.Password placeholder="请输入密码" />
      </Form.Item>

      <Form.Item>
        <Button type="primary" htmlType="submit">
          提交
        </Button>
      </Form.Item>
    </Form>
  );
}
```

### 10.2 布局模式

```tsx
// 水平布局（默认）
<Form layout="horizontal" labelCol={{ span: 6 }} wrapperCol={{ span: 18 }}>
  <Form.Item label="用户名" name="username">
    <Input />
  </Form.Item>
</Form>

// 垂直布局
<Form layout="vertical">
  <Form.Item label="用户名" name="username">
    <Input />
  </Form.Item>
</Form>

// 行内布局
<Form layout="inline">
  <Form.Item label="用户名" name="username">
    <Input />
  </Form.Item>
  <Form.Item>
    <Button type="primary">搜索</Button>
  </Form.Item>
</Form>
```

### 10.3 表单验证

```tsx
<Form
  form={form}
  onFinish={onFinish}
  onFinishFailed={onFinishFailed}
>
  {/* 必填验证 */}
  <Form.Item
    name="username"
    rules={[{ required: true, message: '请输入用户名' }]}
  >
    <Input />
  </Form.Item>

  {/* 长度验证 */}
  <Form.Item
    name="password"
    rules={[
      { required: true, message: '请输入密码' },
      { min: 8, max: 20, message: '密码长度需 8-20 位' },
    ]}
  >
    <Input.Password />
  </Form.Item>

  {/* 自定义验证 */}
  <Form.Item
    name="email"
    rules={[
      { type: 'email', message: '邮箱格式错误' },
      {
        validator: async (_, value) => {
          const exists = await checkEmailExists(value);
          if (exists) {
            throw new Error('邮箱已被注册');
          }
        },
      },
    ]}
  >
    <Input />
  </Form.Item>

  {/* 确认密码验证 */}
  <Form.Item
    name="confirmPassword"
    dependencies={['password']}
    rules={[
      { required: true, message: '请确认密码' },
      ({ getFieldValue }) => ({
        validator(_, value) {
          if (!value || getFieldValue('password') === value) {
            return Promise.resolve();
          }
          return Promise.reject(new Error('两次密码不一致'));
        },
      }),
    ]}
  >
    <Input.Password />
  </Form.Item>
</Form>
```

### 10.4 表单联动

```tsx
<Form>
  {/* 条件显示 */}
  <Form.Item label="配送方式" name="deliveryType">
    <Radio.Group>
      <Radio value="express">快递</Radio>
      <Radio value="pickup">自提</Radio>
    </Radio.Group>
  </Form.Item>

  <Form.Item noStyle shouldUpdate={(prev, curr) => prev.deliveryType !== curr.deliveryType}>
    {({ getFieldValue }) =>
      getFieldValue('deliveryType') === 'express' ? (
        <Form.Item label="收货地址" name="address" rules={[{ required: true }]}>
          <Input.TextArea />
        </Form.Item>
      ) : (
        <Form.Item label="自提门店" name="store" rules={[{ required: true }]}>
          <Select>
            <Option value="store1">门店1</Option>
            <Option value="store2">门店2</Option>
          </Select>
        </Form.Item>
      )
    }
  </Form.Item>
</Form>
```

### 10.5 动态表单项

```tsx
<Form>
  <Form.List name="users">
    {(fields, { add, remove }) => (
      <>
        {fields.map(({ key, name, ...restField }) => (
          <Space key={key} align="baseline">
            <Form.Item
              {...restField}
              name={[name, 'name']}
              rules={[{ required: true, message: '请输入姓名' }]}
            >
              <Input placeholder="姓名" />
            </Form.Item>
            <Form.Item
              {...restField}
              name={[name, 'email']}
              rules={[{ required: true, type: 'email' }]}
            >
              <Input placeholder="邮箱" />
            </Form.Item>
            <Button type="text" onClick={() => remove(name)}>
              删除
            </Button>
          </Space>
        ))}
        <Button type="dashed" onClick={() => add()} block>
          + 添加用户
        </Button>
      </>
    )}
  </Form.List>
</Form>
```

### 10.6 完整 API

```typescript
// Form 组件 Props
interface FormProps {
  // 布局
  layout?: 'horizontal' | 'vertical' | 'inline';
  labelCol?: { span: number; offset?: number };  // Label 栅格配置
  wrapperCol?: { span: number; offset?: number }; // Input 栅格配置
  labelAlign?: 'left' | 'right';                  // Label 对齐方式
  labelWrap?: boolean;                            // Label 是否换行

  // 尺寸
  size?: 'large' | 'middle' | 'small';

  // 表单实例
  form?: FormInstance;

  // 初始值
  initialValues?: Record<string, any>;

  // 事件
  onFinish?: (values: any) => void;               // 提交成功回调
  onFinishFailed?: (errorInfo: any) => void;      // 提交失败回调
  onValuesChange?: (changed: any, all: any) => void; // 值变化回调

  // 验证
  validateTrigger?: 'onChange' | 'onBlur' | 'onSubmit';
  validateMessages?: Record<string, string>;       // 自定义错误提示模板

  // 其他
  name?: string;                                   // 表单名称
  preserve?: boolean;                              // 卸载时是否保留值
  disabled?: boolean;                              // 禁用所有表单项
}

// Form.Item Props
interface FormItemProps {
  // 标识
  name?: string | string[];                        // 字段名
  label?: ReactNode;                              // Label 文字

  // 验证
  rules?: Rule[];                                  // 验证规则
  required?: boolean;                              // 是否必填
  validateTrigger?: 'onChange' | 'onBlur';        // 验证时机
  dependencies?: string[];                         // 依赖字段

  // 布局
  labelCol?: { span: number };
  wrapperCol?: { span: number };
  labelAlign?: 'left' | 'right';

  // 提示
  help?: ReactNode;                                // 提示文字
  extra?: ReactNode;                               // 额外提示
  tooltip?: ReactNode;                             // Tooltip 提示

  // 状态
  validateStatus?: 'success' | 'warning' | 'error' | 'validating';
  hasFeedback?: boolean;                           // 是否显示验证图标

  // 其他
  noStyle?: boolean;                               // 不渲染 Form.Item 样式
  shouldUpdate?: boolean | ((prev, curr) => boolean); // 是否响应更新
  hidden?: boolean;                                // 是否隐藏
}

// Form 实例方法
interface FormInstance {
  getFieldValue: (name: string) => any;
  getFieldsValue: (nameList?: string[]) => any;
  setFieldValue: (name: string, value: any) => void;
  setFieldsValue: (values: any) => void;
  validateFields: (nameList?: string[]) => Promise<any>;
  resetFields: (fields?: string[]) => void;
  submit: () => void;
}
```

---

## 11. 相关资源

### 组件依赖

| 组件 | 说明 |
|------|------|
| Input | 文本输入框 |
| Select | 下拉选择器 |
| Checkbox | 复选框 |
| Radio | 单选框 |
| DatePicker | 日期选择器 |
| Upload | 文件上传 |
| Button | 提交按钮 |
| Space | 按钮间距 |

### 相关组件

| 组件 | 使用场景 |
|------|---------|
| Steps | 多步骤表单 |
| Modal | 弹窗表单 |
| Drawer | 抽屉表单 |
| Collapse | 折叠分组表单 |
| Tabs | 分标签表单 |

### Design Token 文档

- [tokens.json](../../../foundations/tokens/tokens.json) - 完整 Token 定义
- [semantic-colors.json](../../../foundations/tokens/semantic-colors.json) - 语义色定义
- [间距系统](../../../foundations/spacing.md) - 间距规范

### 设计资源

- [Ant Design Form 规范](https://ant.design/components/form-cn/)
- [Material Design Text Fields](https://m3.material.io/components/text-fields/overview)
- [WCAG 表单可访问性指南](https://www.w3.org/WAI/tutorials/forms/)

---

## 12. 更新日志

| 版本 | 日期 | 更新内容 |
|------|------|---------|
| v1.0 | 2025-11-19 | 初始版本，完整的 Form 组件设计规范 |

---

**文档版本：** v1.0
**最后更新：** 2025-11-19
**维护者：** 设计系统团队
**审核状态：** ✅ 已完成

> **参考样板：** Table, Input
> **优先级：** P0
> **复杂度：** ⭐⭐⭐ 高
