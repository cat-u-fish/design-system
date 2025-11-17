# Typography 排版

> 文本展示组件，包括标题、段落、引用等文字排版元素。

---

## 1. 何时使用

### 适用场景

✅ **待填充**

### 不要使用的场景

❌ **待填充**

---

## 2. 解剖结构（Anatomy）

**待填充**

**包含的子组件：**
- Title（标题）：H1 / H2 / H3 / H4 / H5 / H6
- Paragraph（段落）
- Text（文本）
- Quote（引用）
- Code（代码）

---

## 3. 尺寸与间距

### 3.1 标题字阶系统（基于数学公式）

**公式：** `FontSize(n) = 14px × 1.25^n`

| 级别 | 字号 | 行高 | 字重 | Token | 使用场景 |
|------|------|------|------|-------|---------|
| H1 | `32px` | `40px` | `700 Bold` | `font-size-h1` | 页面主标题 |
| H2 | `28px` | `36px` | `700 Bold` | `font-size-h2` | 页面副标题 |
| H3 | `24px` | `32px` | `600 SemiBold` | `font-size-h3` | 章节标题 |
| H4 | `20px` | `28px` | `600 SemiBold` | `font-size-h4` | 小节标题 |
| H5 | `16px` | `24px` | `600 SemiBold` | `font-size-h5` | 段落标题 |
| H6 | `14px` | `20px` | `600 SemiBold` | `font-size-h6` | 辅助标题 |

### 3.2 正文字阶

| 级别 | 字号 | 行高 | 字重 | Token | 使用场景 |
|------|------|------|------|-------|---------|
| Large | `16px` | `24px` | `400 Regular` | `font-size-lg` | 重要正文 |
| Base | `14px` | `20px` | `400 Regular` | `font-size-base` | 默认正文 |
| Small | `12px` | `16px` | `400 Regular` | `font-size-sm` | 辅助文字 |

**待完善：**
- 标题与段落间距规范
- 段落缩进规范
- 列表间距规范

---

## 4. 视觉规范

### 4.1 颜色规范

| 类型 | 颜色 | Token | 使用场景 |
|------|------|-------|---------|
| 主要文字 | `#212121` | `text-primary` | 标题、正文 |
| 次要文字 | `#757575` | `text-secondary` | 描述、备注 |
| 辅助文字 | `#9E9E9E` | `text-tertiary` | 时间戳、提示 |
| 禁用文字 | `#BDBDBD` | `text-disabled` | 禁用状态 |

**待完善：**
- 暗色模式颜色
- 反色文字（深色背景上）
- 引用文字颜色

### 4.2 字体家族

**待填充：**
- 中文字体：PingFang SC / Microsoft YaHei
- 英文字体：Inter / Roboto
- 等宽字体：Fira Code / Consolas

---

## 5. 组件状态（States）

**待填充**

**建议状态：**
- Default / Disabled / Mark（高亮）/ Code（代码）/ Delete（删除线）/ Underline（下划线）

---

## 6. 组件变体（Figma Variants）

**待填充**

**建议 Variants：**
- Type: H1 / H2 / H3 / H4 / H5 / H6 / Paragraph / Text / Quote / Code
- Color: Primary / Secondary / Tertiary / Disabled
- Weight: Regular / Medium / SemiBold / Bold

---

## 7. Figma Auto Layout 配置

**待填充**

---

## 8. Design Token 完整映射表

**待填充**

---

## 9. 设计最佳实践

### 9.1 Do's（推荐做法）

**待填充**

**建议内容：**
- 标题层级不跳级（H1 → H2 → H3）
- 行高设置为字号的 1.4-1.6 倍
- 段落宽度控制在 60-80 字符

### 9.2 Don'ts（不推荐做法）

**待填充**

---

## 10. 代码示例（组件 API）

**待填充**

---

## 11. 相关资源

### Design Token 文档

- [字体系统](../../foundations/tokens/typography.md)
- [行高规范](../../foundations/tokens/typography.md#行高系统)

---

## 12. 更新日志

| 版本 | 日期 | 更新内容 |
|------|------|---------|
| v0.1 | 2025-11-17 | 初始框架，待完善 |

---

**文档版本：** v0.1（框架）
**最后更新：** 2025-11-17
**维护者：** 设计系统团队
**审核状态：** 🚧 待完善

> **参考样板：** Button（简单组件）
> **优先级：** P0
> **复杂度：** ⭐ 低
