# 组件规范 - 总览

> 基于设计 Token 的完整 UI 组件库规范，覆盖企业级应用的所有核心场景。

---

## 设计理念

### 1. 组件设计原则

```
确定性 (Certainty)
  - 组件行为可预测，符合用户认知模型
  - 相同输入产生相同输出

一致性 (Consistency)
  - 视觉风格统一（基于 Design Token）
  - 交互模式统一（符合平台规范）
  - 命名规范统一（中英对照）

简洁高效 (Efficiency)
  - 减少用户操作步骤
  - 优化信息密度（B 端：14px 基础字号）
  - 快速响应（< 100ms 感知延迟）

包容性 (Inclusivity)
  - WCAG 2.1 AA 级可访问性
  - 支持键盘导航
  - 支持屏幕阅读器
```

### 2. 设计 Token 驱动

所有组件基于三层 Token 体系构建：

```
Primitive Tokens (基础色板)
    ↓ 引用
Semantic Tokens (语义 Token)
    ↓ 引用
Component Tokens (组件 Token) ← 组件直接使用
```

**示例：**
```css
.ant-btn-primary {
  background: var(--button-primary-bg);  /* 组件 Token */
  color: var(--button-primary-text);
  border-radius: var(--radius-md);       /* 基础 Token */
  padding: var(--spacing-2) var(--spacing-4);
}
```

---

## 组件分类体系

### 📊 总览统计

| 分类 | 组件数 | 复杂度 | 优先级 | 完成度 |
|------|--------|--------|--------|--------|
| [1. 通用 (General)](#1-通用-general) | 4 | ⭐ 低 | 🔴 P0 | 🚧 规划中 |
| [2. 布局 (Layout)](#2-布局-layout) | 7 | ⭐⭐ 中 | 🔴 P0 | 🚧 规划中 |
| [3. 导航 (Navigation)](#3-导航-navigation) | 9 | ⭐⭐ 中 | 🔴 P0 | 🚧 规划中 |
| [4. 数据录入 (Data Entry)](#4-数据录入-data-entry) | 18 | ⭐⭐⭐ 高 | 🔴 P0 | 🚧 规划中 |
| [5. 数据展示 (Data Display)](#5-数据展示-data-display) | 15 | ⭐⭐⭐ 高 | 🔴 P0 | 🚧 规划中 |
| [6. 反馈 (Feedback)](#6-反馈-feedback) | 10 | ⭐⭐ 中 | 🔴 P0 | 🚧 规划中 |
| **合计** | **63** | - | - | **0%** |

---

## 1. 通用 (General)

**定位：** 构成界面的最基础、最通用的原子组件

| 中文 | English | 组件名 | 复杂度 | 优先级 | 说明 |
|------|---------|--------|--------|--------|------|
| 按钮 | Button | `Button` | ⭐ | P0 | 触发操作的交互元素 |
| 图标 | Icon | `Icon` | ⭐ | P0 | 图形符号，辅助信息传达 |
| 链接 | Link | `Link` | ⭐ | P0 | 页面或外部跳转 |
| 排版 | Typography | `Typography` | ⭐ | P0 | 文本展示（标题/段落/引用） |

**设计要点：**
- Button: 4 种类型（Primary/Secondary/Danger/Ghost），5 种尺寸
- Icon: SVG 优先，支持多色图标和线性图标
- Link: 下划线可选，支持禁用态
- Typography: 基于数学公式的字阶系统（1.25 比例）

**相关文档：** [通用组件规范](./01-general.md) 🚧

---

## 2. 布局 (Layout)

**定位：** 负责页面结构、空间和组织关系的容器组件

| 中文 | English | 组件名 | 复杂度 | 优先级 | 说明 |
|------|---------|--------|--------|--------|------|
| 栅格 | Grid | `Grid` | ⭐⭐ | P0 | 响应式栅格系统（24 列） |
| 布局 | Layout | `Layout` | ⭐⭐ | P0 | 页面整体布局框架 |
| 间距 | Space | `Space` | ⭐ | P0 | 元素间距控制（水平/垂直） |
| 分割线 | Divider | `Divider` | ⭐ | P0 | 内容分隔（水平/垂直） |
| 卡片 | Card | `Card` | ⭐⭐ | P0 | 信息容器，带标题/边框/阴影 |
| 折叠面板 | Collapse | `Collapse` | ⭐⭐ | P1 | 手风琴式可折叠容器 |
| 可伸缩面板 | Resizable | `Resizable` | ⭐⭐⭐ | P2 | 用户可调整大小的面板 |

**设计要点：**
- Grid: 24 列栅格，支持响应式断点（xs/sm/md/lg/xl/xxl）
- Layout: Header/Sider/Content/Footer 组合
- Space: 基于 4px 网格的间距（8/12/16/24/32）
- Card: 支持操作区、封面图、网格布局

**相关文档：** [布局组件规范](./02-layout.md) 🚧

---

## 3. 导航 (Navigation)

**定位：** 负责页面、视图或内容间的跳转和定位

| 中文 | English | 组件名 | 复杂度 | 优先级 | 说明 |
|------|---------|--------|--------|--------|------|
| 导航菜单 | Navigation Menu | `Menu` | ⭐⭐⭐ | P0 | 多级菜单，支持水平/垂直 |
| 标签页 | Tabs | `Tabs` | ⭐⭐ | P0 | 内容分组切换 |
| 面包屑 | Breadcrumb | `Breadcrumb` | ⭐ | P0 | 显示当前页面路径 |
| 步骤条 | Steps | `Steps` | ⭐⭐ | P0 | 引导流程，显示进度 |
| 分页 | Pagination | `Pagination` | ⭐⭐ | P0 | 数据分页导航 |
| 下拉菜单 | Dropdown | `Dropdown` | ⭐⭐ | P0 | 悬浮操作菜单 |
| 锚点 | Anchor | `Anchor` | ⭐ | P1 | 页内导航定位 |
| 固钉 | Affix | `Affix` | ⭐⭐ | P1 | 固定元素到视口 |
| 返回顶部 | Back to Top | `BackTop` | ⭐ | P2 | 快速回到页面顶部 |

**设计要点：**
- Menu: 支持内联/垂直/水平模式，可折叠
- Tabs: 支持卡片/线条/圆角样式，可关闭
- Steps: 支持水平/垂直/点状/导航式
- Pagination: 支持简洁/完整模式，跳转输入

**相关文档：** [导航组件规范](./03-navigation.md) 🚧

---

## 4. 数据录入 (Data Entry)

**定位：** 用于收集、录入和提交用户数据

| 中文 | English | 组件名 | 复杂度 | 优先级 | 说明 |
|------|---------|--------|--------|--------|------|
| 表单 | Form | `Form` | ⭐⭐⭐ | P0 | 表单容器，统一管理验证 |
| 输入框 | Input | `Input` | ⭐⭐ | P0 | 单行文本输入 |
| 自动完成 | Auto Complete | `AutoComplete` | ⭐⭐ | P1 | 输入建议 |
| 数字输入框 | Input Number | `InputNumber` | ⭐⭐ | P0 | 数字输入，带增减按钮 |
| 选择器 | Select | `Select` | ⭐⭐⭐ | P0 | 下拉选择，支持搜索/多选 |
| 级联选择 | Cascader | `Cascader` | ⭐⭐⭐ | P1 | 多级联动选择 |
| 树选择 | Tree Select | `TreeSelect` | ⭐⭐⭐ | P1 | 树形结构选择 |
| 多选框 | Checkbox | `Checkbox` | ⭐ | P0 | 多项选择 |
| 单选框 | Radio | `Radio` | ⭐ | P0 | 单项选择 |
| 开关 | Switch | `Switch` | ⭐ | P0 | 开/关切换 |
| 日期选择器 | Date Picker | `DatePicker` | ⭐⭐⭐ | P0 | 日期/日期范围选择 |
| 时间选择器 | Time Picker | `TimePicker` | ⭐⭐ | P0 | 时间选择 |
| 滑块 | Slider | `Slider` | ⭐⭐ | P1 | 数值范围选择 |
| 评分 | Rate | `Rate` | ⭐ | P2 | 星级评分 |
| 穿梭框 | Transfer | `Transfer` | ⭐⭐⭐ | P1 | 双列表选择 |
| 上传 | Upload | `Upload` | ⭐⭐⭐ | P0 | 文件上传 |
| 提及 | Mentions | `Mentions` | ⭐⭐ | P2 | @提及功能 |
| 颜色选择器 | Color Picker | `ColorPicker` | ⭐⭐ | P2 | 颜色选择（可选） |

**设计要点：**
- Form: 支持水平/垂直/行内布局，统一验证规则
- Input: 支持前缀/后缀/清除/密码/搜索/文本域
- Select: 虚拟滚动（大数据）、远程搜索、分组
- DatePicker: 快捷选择、禁用日期、自定义单元格

**相关文档：** [数据录入组件规范](./04-data-entry.md) 🚧

---

## 5. 数据展示 (Data Display)

**定位：** 用于结构化地展示信息

| 中文 | English | 组件名 | 复杂度 | 优先级 | 说明 |
|------|---------|--------|--------|--------|------|
| 表格 | Table | `Table` | ⭐⭐⭐ | P0 | 数据表格，支持排序/筛选/分页 |
| 列表 | List | `List` | ⭐⭐ | P0 | 通用列表容器 |
| 树形控件 | Tree | `Tree` | ⭐⭐⭐ | P1 | 树形数据展示 |
| 头像 | Avatar | `Avatar` | ⭐ | P0 | 用户头像 |
| 徽标数 | Badge | `Badge` | ⭐ | P0 | 数字角标 |
| 标签 | Tag | `Tag` | ⭐ | P0 | 标签/分类 |
| 文字提示 | Tooltip | `Tooltip` | ⭐⭐ | P0 | 悬浮提示 |
| 气泡卡片 | Popover | `Popover` | ⭐⭐ | P0 | 点击弹出卡片 |
| 空状态 | Empty | `Empty` | ⭐ | P0 | 无数据占位 |
| 日历 | Calendar | `Calendar` | ⭐⭐⭐ | P1 | 日历展示 |
| 图片 | Image | `Image` | ⭐⭐ | P0 | 图片展示（预览/懒加载） |
| 时间轴 | Timeline | `Timeline` | ⭐⭐ | P1 | 时序信息展示 |
| 统计数值 | Statistic | `Statistic` | ⭐ | P1 | 数值统计展示 |
| 分段控制器 | Segmented | `Segmented` | ⭐ | P1 | 分段选择器 |
| 轮播图 | Carousel | `Carousel` | ⭐⭐ | P1 | 图片/内容轮播 |

**设计要点：**
- Table: 固定列/表头、树形数据、虚拟滚动、可编辑单元格
- List: 无限滚动、栅格布局、响应式
- Tree: 异步加载、拖拽、搜索、自定义节点
- Tooltip: 12 个方向定位，支持受控模式

**相关文档：** [数据展示组件规范](./05-data-display.md) 🚧

---

## 6. 反馈 (Feedback)

**定位：** 对用户操作给予响应或提示

| 中文 | English | 组件名 | 复杂度 | 优先级 | 说明 |
|------|---------|--------|--------|--------|------|
| 全局提示 | Message | `Message` | ⭐⭐ | P0 | 轻量级全局提示 |
| 通知提醒框 | Notification | `Notification` | ⭐⭐ | P0 | 全局通知，停留时间长 |
| 警告提示 | Alert | `Alert` | ⭐ | P0 | 页面级警告信息 |
| 对话框 | Modal | `Modal` | ⭐⭐⭐ | P0 | 模态对话框 |
| 气泡确认框 | Popconfirm | `Popconfirm` | ⭐⭐ | P0 | 轻量确认弹框 |
| 加载中 | Loading | `Loading` | ⭐ | P0 | 加载状态指示器 |
| 骨架屏 | Skeleton | `Skeleton` | ⭐⭐ | P0 | 内容加载占位 |
| 进度条 | Progress | `Progress` | ⭐⭐ | P0 | 进度展示 |
| 抽屉 | Drawer | `Drawer` | ⭐⭐⭐ | P0 | 侧滑面板 |
| 结果页 | Result | `Result` | ⭐ | P1 | 操作结果反馈页 |

**设计要点：**
- Message: 3 秒自动关闭，支持 success/error/warning/info 类型
- Modal: 支持确认框/信息框，可拖拽（可选）
- Loading: Spin + 局部/全局遮罩
- Progress: 线形/环形/仪表盘，支持步骤进度

**相关文档：** [反馈组件规范](./06-feedback.md) 🚧

---

## 组件开发规范

### 1. 命名规范

**组件名：** PascalCase
```typescript
Button / DatePicker / TreeSelect
```

**Props 命名：**
```typescript
// ✅ 好
<Button size="large" type="primary" disabled />

// ❌ 不好
<Button buttonSize="lg" btnType="main" isDisabled />
```

**事件命名：**
```typescript
// ✅ 好
onChange / onVisibleChange / onSelect

// ❌ 不好
change / handleVisible / selectEvent
```

### 2. API 设计原则

**最小化 API 复杂度：**
```typescript
// ✅ 好：简洁的 API
<Select options={options} onChange={handleChange} />

// ❌ 不好：过度配置
<Select
  dataSource={options}
  onChangeEvent={handleChange}
  selectMode="single"
  autoWidth={true}
/>
```

**组合优于配置：**
```typescript
// ✅ 好：组合方式
<Select>
  <Select.Option value="1">选项 1</Select.Option>
  <Select.Option value="2">选项 2</Select.Option>
</Select>

// ❌ 不好：纯配置
<Select options={[
  { label: '选项 1', value: '1' },
  { label: '选项 2', value: '2' }
]} />
```

### 3. 可访问性要求

**所有组件必须满足：**
- ✅ 键盘可访问（Tab/Enter/Space/Arrow）
- ✅ ARIA 属性完整（role/aria-label/aria-checked）
- ✅ 焦点管理（Focus Ring 可见）
- ✅ 屏幕阅读器支持
- ✅ 颜色对比度 ≥ 4.5:1（WCAG AA）

**示例：**
```html
<button
  class="ant-btn ant-btn-primary"
  role="button"
  aria-label="提交表单"
  aria-disabled="false"
  tabindex="0"
>
  提交
</button>
```

### 4. 性能要求

| 指标 | 标准 | 说明 |
|------|------|------|
| 首次渲染 | < 16ms | 避免阻塞主线程 |
| 交互响应 | < 100ms | 用户感知流畅 |
| 大数据渲染 | 虚拟滚动 | Table/Select/Tree 必须支持 |
| 包体积 | < 2KB | 单个组件 gzip 后体积 |
| Tree Shaking | ✅ 支持 | 按需引入 |

---

## 组件状态规范

### 通用状态

所有交互组件必须支持以下状态：

| 状态 | 说明 | 视觉表现 |
|------|------|---------|
| Default | 默认态 | 正常颜色 |
| Hover | 悬停态 | 背景变浅/边框高亮 |
| Active | 激活态 | 背景加深 |
| Focus | 聚焦态 | 显示 Focus Ring（3px 蓝色） |
| Disabled | 禁用态 | 灰色 + 禁止光标 |
| Loading | 加载态 | Loading 图标 + 禁用交互 |
| Error | 错误态 | 红色边框 + 错误提示 |

**状态优先级：**
```
Disabled > Loading > Error > Focus > Active > Hover > Default
```

---

## 组件尺寸规范

### 统一尺寸体系

| 尺寸 | 高度 | 字号 | 内边距（水平） | 使用场景 |
|------|------|------|---------------|---------|
| Large | 40px | 16px | 16px | 主要操作、表单标题 |
| Middle | 32px | 14px | 12px | 默认尺寸，最常用 |
| Small | 24px | 12px | 8px | 次要操作、紧凑布局 |

**应用示例：**
```tsx
<Button size="large">大按钮</Button>
<Input size="middle" />
<Select size="small" />
```

---

## 国际化支持

### 1. 文本外部化

```typescript
// ✅ 好：使用 i18n
<DatePicker placeholder={t('datePicker.placeholder')} />

// ❌ 不好：硬编码
<DatePicker placeholder="请选择日期" />
```

### 2. RTL 支持

所有组件必须支持从右到左（Right-to-Left）布局：

```css
[dir="rtl"] .ant-btn {
  text-align: right;
}
```

---

## 主题定制

### 基于 Design Token

所有组件样式通过 CSS Variables 定制：

```css
/* 全局主题 */
:root {
  --primary-color: #0770FA;
  --border-radius-base: 4px;
  --font-size-base: 14px;
}

/* 组件使用 */
.ant-btn-primary {
  background: var(--primary-color);
  border-radius: var(--border-radius-base);
}
```

**支持的定制方式：**
1. CSS Variables（推荐）
2. Less 变量
3. ConfigProvider 运行时主题

---

## 测试要求

### 单元测试覆盖率

| 类型 | 覆盖率 | 说明 |
|------|--------|------|
| 语句覆盖 | ≥ 80% | Statements |
| 分支覆盖 | ≥ 75% | Branches |
| 函数覆盖 | ≥ 80% | Functions |
| 行覆盖 | ≥ 80% | Lines |

### 必测场景

- ✅ 基本渲染
- ✅ Props 变化
- ✅ 事件触发
- ✅ 键盘交互
- ✅ 边界情况（空数据/大数据）
- ✅ 错误处理

---

## 文档要求

每个组件必须包含：

1. **API 文档**：Props/Methods/Events 完整说明
2. **代码示例**：至少 3 个典型用例
3. **设计指南**：何时使用、最佳实践
4. **可访问性说明**：ARIA 属性、键盘操作
5. **主题定制**：可定制的 Token 列表

---

## 下一步计划

### Phase 1：基础组件（P0）
- [ ] 通用组件（4 个）
- [ ] 布局组件（7 个）
- [ ] 核心表单组件（8 个）
- [ ] 核心反馈组件（6 个）

### Phase 2：完整表单（P0/P1）
- [ ] 复杂表单组件（Select/DatePicker/Upload 等）
- [ ] 数据展示组件（Table/List 等）
- [ ] 导航组件

### Phase 3：扩展组件（P1/P2）
- [ ] 高级数据展示（Tree/Calendar/Timeline）
- [ ] 辅助组件（Anchor/Affix/BackTop）

---

## 相关文档

- [Design Token 规范](../foundations/tokens/README.md) - Token 系统
- [语义化色彩](../foundations/tokens/semantic-colors.md) - 色彩 Token
- [设计原理](../foundations/tokens/design-principles.md) - 数学公式
- [组件色 Token](../foundations/tokens/semantic/component-colors.md) - 组件专用色

---

**文档版本：** v1.0
**最后更新：** 2025-11-16
**维护者：** 设计系统团队
