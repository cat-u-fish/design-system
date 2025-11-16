# Figma Tokens Studio 免费版导入方案

> 针对免费版用户的简化 Token 导入方案，无需付费许可证

---

## 🆓 免费版 vs 付费版对比

| 功能 | 免费版 | 付费版 |
|------|--------|--------|
| **基础 Token 创建** | ✅ 支持 | ✅ 支持 |
| **本地文档存储** | ✅ 支持 | ✅ 支持 |
| **GitHub/GitLab 同步** | ❌ 不支持 | ✅ 支持 |
| **JSON 文件导入** | ⚠️ 部分支持 | ✅ 完全支持 |
| **Token 别名引用** | ⚠️ 基础支持 | ✅ 完全支持 |
| **团队协作** | ❌ 不支持 | ✅ 支持 |

**结论：** 免费版可以正常使用，但需要手动创建 Token 或使用简化的导入方式。

---

## 🎯 推荐方案：手动创建核心 Token（最稳定）

### 为什么推荐手动创建？

✅ **完全免费**，无需付费许可证
✅ **100% 可控**，清楚每个 Token 的用途
✅ **稳定可靠**，不依赖插件功能
✅ **学习效果好**，深入理解 Design Token

---

## 📋 核心 Token 创建清单（仅需 30 分钟）

### 第 1 步：打开 Tokens Studio 插件

1. 在 Figma 中运行 **Tokens Studio for Figma** 插件
2. 如果提示登录，可以选择 **Continue without login**（免费使用）

---

### 第 2 步：创建颜色 Token（最重要）

#### 创建 Grey 灰色系列

1. 在插件中点击 **+ New Token**
2. 选择类型：**Color**
3. 逐个创建：

| Token 名称 | 值 | 用途 |
|-----------|-----|------|
| `grey-50` | `#FAFAFA` | 最浅灰 |
| `grey-100` | `#F5F5F5` | 浅灰背景 |
| `grey-200` | `#EEEEEE` | 分割线 |
| `grey-300` | `#E0E0E0` | 边框（常用） |
| `grey-400` | `#BDBDBD` | 禁用状态 |
| `grey-500` | `#9E9E9E` | 中性灰 |
| `grey-600` | `#757575` | 次要文本 |
| `grey-700` | `#616161` | 深灰 |
| `grey-800` | `#424242` | 深灰背景 |
| `grey-900` | `#212121` | 主文本 |

**创建步骤：**
```
1. 点击 "+" → 选择 Color
2. Name: grey-50
3. Value: #FAFAFA
4. 点击 Save
5. 重复以上步骤创建 grey-100 到 grey-900
```

#### 创建 Blue 蓝色系列（主色）

| Token 名称 | 值 | 用途 |
|-----------|-----|------|
| `blue-50` | `#E3F2FD` | 淡蓝背景 |
| `blue-100` | `#BBDEFB` | 浅蓝背景 |
| `blue-500` | `#2196F3` | 主蓝色 |
| `blue-600` | `#1E88E5` | 链接/按钮 |
| `blue-700` | `#1976D2` | 主要操作 |
| `blue-900` | `#0D47A1` | 按下状态 |

#### 创建功能色（必备）

| Token 名称 | 值 | 用途 |
|-----------|-----|------|
| `red-50` | `#FFEBEE` | 错误背景 |
| `red-600` | `#E53935` | 错误文本 |
| `green-50` | `#E8F5E9` | 成功背景 |
| `green-600` | `#43A047` | 成功文本 |
| `orange-50` | `#FFF3E0` | 警告背景 |
| `orange-600` | `#FB8C00` | 警告文本 |

**提示：** 先创建这 22 个核心颜色，足够 B端系统 80% 的场景使用。

---

### 第 3 步：创建间距 Token

| Token 名称 | 值 | 用途 |
|-----------|-----|------|
| `spacing-0` | `0` | 无间距 |
| `spacing-1` | `4` | 最小单位 |
| `spacing-2` | `8` | 小组件内边距 |
| `spacing-3` | `12` | 按钮内边距 |
| `spacing-4` | `16` | 卡片内边距（常用） |
| `spacing-6` | `24` | 大组件内边距 |
| `spacing-8` | `32` | 区块间距 |
| `spacing-12` | `48` | 大区块间距 |
| `spacing-16` | `64` | 页面模块间距 |

**创建步骤：**
```
1. 点击 "+" → 选择 Spacing
2. Name: spacing-4
3. Value: 16
4. 点击 Save
```

---

### 第 4 步：创建字体 Token

#### 字体大小

| Token 名称 | 值 | 用途 |
|-----------|-----|------|
| `font-size-xs` | `12` | 辅助信息 |
| `font-size-sm` | `14` | B端基准（正文） |
| `font-size-base` | `14` | 别名 |
| `font-size-lg` | `18` | 小标题 |
| `font-size-xl` | `22` | 次级标题 |
| `font-size-2xl` | `28` | 主标题 |
| `font-size-3xl` | `34` | 大标题 |

**创建步骤：**
```
1. 点击 "+" → 选择 Font Size
2. Name: font-size-base
3. Value: 14
4. 点击 Save
```

#### 字重

| Token 名称 | 值 |
|-----------|-----|
| `font-weight-normal` | `400` |
| `font-weight-medium` | `500` |
| `font-weight-semibold` | `600` |
| `font-weight-bold` | `700` |

---

### 第 5 步：创建圆角 Token

| Token 名称 | 值 | 用途 |
|-----------|-----|------|
| `radius-none` | `0` | 直角 |
| `radius-sm` | `2` | 小圆角 |
| `radius-base` | `4` | 基础圆角（按钮） |
| `radius-md` | `6` | 中圆角 |
| `radius-lg` | `8` | 大圆角（卡片） |
| `radius-xl` | `12` | 超大圆角 |
| `radius-2xl` | `16` | 模态框 |
| `radius-full` | `9999` | 圆形 |

---

### 第 6 步：创建阴影 Token

| Token 名称 | 值 | 用途 |
|-----------|-----|------|
| `shadow-sm` | `0 2px 4px 0 rgba(0, 0, 0, 0.06), 0 1px 2px 0 rgba(0, 0, 0, 0.06)` | 轻微悬浮 |
| `shadow-base` | `0 4px 8px -2px rgba(0, 0, 0, 0.08), 0 2px 4px -2px rgba(0, 0, 0, 0.08)` | 卡片 |
| `shadow-md` | `0 8px 16px -4px rgba(0, 0, 0, 0.12), 0 4px 8px -4px rgba(0, 0, 0, 0.12)` | 下拉菜单 |
| `shadow-lg` | `0 16px 32px -8px rgba(0, 0, 0, 0.16), 0 8px 16px -8px rgba(0, 0, 0, 0.16)` | 模态框 |

**创建步骤：**
```
1. 点击 "+" → 选择 Box Shadow
2. Name: shadow-base
3. Value: 粘贴上面的值
4. 点击 Save
```

---

## 📊 核心 Token 创建总结

| 类型 | 数量 | 预计时间 |
|------|------|---------|
| 颜色（Grey + Blue + 功能色） | 22 个 | 10 分钟 |
| 间距 | 9 个 | 3 分钟 |
| 字体大小 + 字重 | 11 个 | 5 分钟 |
| 圆角 | 8 个 | 3 分钟 |
| 阴影 | 4 个 | 5 分钟 |
| **总计** | **54 个** | **~30 分钟** |

**这 54 个 Token 足够覆盖 B端系统 80% 的设计需求！**

---

## 🎨 应用 Token 到 Figma 样式

### 创建颜色样式

1. 选择 Token `grey-900` (#212121)
2. 右键 → **Create Style** → **Fill Style**
3. 命名：`Text/Primary`
4. 重复创建其他常用颜色样式

### 推荐创建的样式

**颜色样式（10 个）：**
```
Text/Primary        → grey-900
Text/Secondary      → grey-600
Background/Primary  → #FFFFFF
Background/Card     → grey-50
Border/Default      → grey-300
Primary/Default     → blue-700
Success             → green-600
Warning             → orange-600
Error               → red-600
```

**文本样式（5 个）：**
```
H1 → font-size-3xl (34px) + font-weight-bold (700)
H2 → font-size-2xl (28px) + font-weight-semibold (600)
H3 → font-size-xl (22px) + font-weight-semibold (600)
Body → font-size-base (14px) + font-weight-normal (400)
Caption → font-size-xs (12px) + font-weight-normal (400)
```

**效果样式（3 个）：**
```
Shadow/Card     → shadow-base
Shadow/Dropdown → shadow-md
Shadow/Modal    → shadow-lg
```

---

## 🔄 替代方案 2：使用 Figma 原生变量（推荐）

如果 Tokens Studio 导入有问题，可以直接使用 Figma 原生变量功能（2023 年新增，无需插件）：

### 步骤 1：创建变量集合

1. 在 Figma 右侧面板，点击 **Variables**
2. 点击 **Create collection**
3. 命名：`Design Tokens`

### 步骤 2：添加颜色变量

1. 点击 **+** → 选择 **Color**
2. 创建变量：

```
grey/50    → #FAFAFA
grey/100   → #F5F5F5
grey/300   → #E0E0E0
grey/600   → #757575
grey/900   → #212121

blue/500   → #2196F3
blue/700   → #1976D2

green/600  → #43A047
red/600    → #E53935
orange/600 → #FB8C00
```

### 步骤 3：添加数字变量（间距）

1. 点击 **+** → 选择 **Number**
2. 创建变量：

```
spacing/4  → 16
spacing/6  → 24
spacing/8  → 32
```

### 优势

✅ **Figma 原生功能**，无需插件
✅ **完全免费**，无任何限制
✅ **性能更好**，集成度高
✅ **支持暗色模式**，可创建 Light/Dark 两个模式

---

## 📋 快速复制清单

### 核心颜色（直接复制到 Figma）

```
Grey:
#FAFAFA, #F5F5F5, #EEEEEE, #E0E0E0, #BDBDBD
#9E9E9E, #757575, #616161, #424242, #212121

Blue:
#E3F2FD, #BBDEFB, #2196F3, #1E88E5, #1976D2, #0D47A1

Green:
#E8F5E9, #43A047

Red:
#FFEBEE, #E53935

Orange:
#FFF3E0, #FB8C00
```

### 核心间距

```
4px, 8px, 12px, 16px, 24px, 32px, 48px, 64px
```

### 核心字号

```
12px, 14px, 18px, 22px, 28px, 34px
```

---

## ❓ 常见问题

### Q: 为什么免费版导入 JSON 会失败？

**A:** 免费版的 JSON 导入功能有限制，推荐使用：
1. **手动创建 Token**（最稳定）
2. **使用 Figma 原生变量**（官方功能）
3. **升级到付费版**（如果需要团队协作）

### Q: 手动创建太慢了怎么办？

**A:** 优先创建核心 Token：
- **颜色**：Grey + Blue + 功能色（22 个）
- **间距**：spacing-4, 6, 8, 12, 16（5 个）
- **字号**：font-size-xs, base, lg, xl, 2xl（5 个）

**这 32 个 Token 已经足够开始设计了！**

### Q: 后续如何扩展？

**A:** 根据项目需要，逐步添加：
1. 先用核心 Token 完成主要页面设计
2. 遇到新需求时再添加新的 Token
3. 保持 Token 数量精简，避免过度设计

---

## 💡 最佳实践建议

### 对于 B端系统，优先创建：

**必备 Token（32 个）：**
```
颜色：
- Grey: 50, 300, 600, 900（4 个）
- Blue: 500, 700（2 个）
- 功能色：Red-600, Green-600, Orange-600（3 个）

间距：
- 4, 8, 12, 16, 24, 32, 48（7 个）

字号：
- 12, 14, 18, 22, 28（5 个）

字重：
- 400, 500, 600, 700（4 个）

圆角：
- 0, 4, 8, 16（4 个）

阴影：
- shadow-base, shadow-md, shadow-lg（3 个）
```

**扩展 Token（后续添加）：**
- 更多颜色变体
- 更细粒度的间距
- 特殊效果（渐变、模糊等）

---

**总结：** 免费版完全可以正常使用！建议使用手动创建或 Figma 原生变量功能，无需依赖付费插件。

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
**维护者：** 设计系统团队
