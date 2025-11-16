# Figma Tokens Studio 导入指南

> 如何将 Design Token 导入到 Figma Tokens Studio 插件

---

## 📦 文件准备

已为您准备好以下文件：

| 文件 | 用途 |
|------|------|
| `tokens.json` | Tokens Studio 标准格式文件（可直接导入） |
| `tokens-reference.md` | 完整参考文档（793行，包含所有 Token） |

---

## 🚀 导入步骤

### 步骤 1：安装 Tokens Studio 插件

1. 在 Figma 中，点击菜单 `Plugins` → `Find more plugins`
2. 搜索 **"Tokens Studio for Figma"**
3. 点击 `Install` 安装插件

**插件地址：** https://www.figma.com/community/plugin/843461159747178978

---

### 步骤 2：导入 Token 文件

#### 方法 A：JSON 文件导入（推荐）

1. 在 Figma 中运行 **Tokens Studio** 插件
2. 点击右上角 **设置图标** ⚙️
3. 选择 **Settings** → **Storage**
4. 选择 **Local Document** 或 **JSON File**
5. 点击 **Load from file**
6. 选择 `foundations/tokens/tokens.json` 文件
7. 点击 **Import**

#### 方法 B：手动创建 Token（适合部分导入）

1. 运行 **Tokens Studio** 插件
2. 点击左侧 **+ 按钮** 创建 Token Set
3. 参考 `tokens-reference.md` 文档
4. 手动添加需要的 Token

---

### 步骤 3：配置 Token Sets

导入后，您会看到以下 Token Sets（分组）：

```
color/          # 颜色（Grey, Red, Blue, Green, Orange, Yellow）
font/           # 字体（family, size, weight, lineHeight, letterSpacing）
spacing/        # 间距（0-64）
borderRadius/   # 圆角（none-full）
borderWidth/    # 边框宽度
boxShadow/      # 阴影
opacity/        # 透明度
duration/       # 动画时长
cubicBezier/    # 缓动函数
```

**建议配置：**
- 设置 `color`, `font`, `spacing` 为 **Source** Token Sets（基础）
- 其他为 **Enabled** 状态

---

### 步骤 4：应用 Token 到 Figma 样式

#### 创建颜色样式

1. 在 Tokens Studio 中，找到 `color/blue/500`
2. 右键点击 Token
3. 选择 **Create Style** → **Fill Style**
4. 命名为 `Color/Blue/500`
5. 重复此操作创建其他颜色样式

#### 创建文本样式

1. 找到 `font/size/base` (14px)
2. 右键 → **Create Text Style**
3. 配置：
   - Font Size: `{font.size.base}`
   - Line Height: `{font.lineHeight.normal}`
   - Font Weight: `{font.weight.normal}`
4. 命名为 `Text/Body/Base`

#### 创建效果样式（阴影）

1. 找到 `boxShadow/md`
2. 右键 → **Create Effect Style**
3. 命名为 `Shadow/Medium`

---

## 📋 Token 使用示例

### 在 Figma 中使用 Token

**应用颜色 Token：**
```
1. 选择一个矩形
2. 打开 Tokens Studio 插件
3. 点击 Fill 属性
4. 选择 color.blue.500
5. 矩形填充自动应用蓝色
```

**应用间距 Token：**
```
1. 使用 Auto Layout
2. 在 Tokens Studio 中找到 spacing.4 (16px)
3. 拖拽 Token 到 Padding 属性
4. 自动应用 16px 内边距
```

**应用字体 Token：**
```
1. 选择文本图层
2. 应用 font.size.base (14px)
3. 应用 font.lineHeight.normal (1.43)
4. 应用 font.weight.medium (500)
```

---

## 🎨 B端系统推荐配置

### 常用颜色组合

```json
{
  "primary": "{color.blue.700}",
  "success": "{color.green.600}",
  "warning": "{color.orange.600}",
  "error": "{color.red.600}",
  "text-primary": "{color.grey.900}",
  "text-secondary": "{color.grey.600}",
  "border": "{color.grey.300}",
  "background": "#FFFFFF"
}
```

### 常用间距组合

```json
{
  "button-padding-x": "{spacing.4}",    // 16px
  "button-padding-y": "{spacing.3}",    // 12px
  "card-padding": "{spacing.6}",        // 24px
  "form-item-gap": "{spacing.6}",       // 24px
  "section-gap": "{spacing.16}"         // 64px
}
```

### 常用文本样式

| 样式名称 | 字号 | 字重 | 行高 | 用途 |
|---------|------|------|------|------|
| H1 | `font.size.4xl` (42px) | `font.weight.bold` (700) | `font.lineHeight.tight` (1.14) | 页面标题 |
| H2 | `font.size.3xl` (34px) | `font.weight.bold` (700) | `font.lineHeight.tight` (1.14) | 区块标题 |
| H3 | `font.size.2xl` (28px) | `font.weight.semibold` (600) | `font.lineHeight.snug` (1.29) | 卡片标题 |
| Body | `font.size.base` (14px) | `font.weight.normal` (400) | `font.lineHeight.normal` (1.43) | 正文 |
| Caption | `font.size.xs` (12px) | `font.weight.normal` (400) | `font.lineHeight.normal` (1.43) | 辅助信息 |

---

## 🔄 同步到代码

### 导出 CSS Variables

在 Tokens Studio 中：

1. 点击右上角 **设置** ⚙️
2. 选择 **Export**
3. 选择 **CSS Variables**
4. 复制生成的代码到项目中

示例输出：

```css
:root {
  --color-blue-500: #2196F3;
  --font-size-base: 14px;
  --spacing-4: 16px;
  --border-radius-base: 4px;
  --box-shadow-md: 0 8px 16px -4px rgba(0, 0, 0, 0.12), 0 4px 8px -4px rgba(0, 0, 0, 0.12);
}
```

### 使用 Style Dictionary（高级）

如果需要自动化同步，可以使用 Style Dictionary：

```bash
npm install style-dictionary
```

配置文件 `config.json`:

```json
{
  "source": ["tokens.json"],
  "platforms": {
    "css": {
      "transformGroup": "css",
      "buildPath": "build/css/",
      "files": [{
        "destination": "tokens.css",
        "format": "css/variables"
      }]
    },
    "js": {
      "transformGroup": "js",
      "buildPath": "build/js/",
      "files": [{
        "destination": "tokens.js",
        "format": "javascript/es6"
      }]
    }
  }
}
```

---

## 🌙 暗色模式支持

### 创建 Dark Mode Token Set

1. 在 Tokens Studio 中点击 **+ New Set**
2. 命名为 `dark-mode`
3. 添加暗色模式颜色：

```json
{
  "color": {
    "text": {
      "primary": "{color.grey.50}",
      "secondary": "{color.grey.400}"
    },
    "background": {
      "primary": "{color.grey.900}",
      "secondary": "{color.grey.800}"
    }
  }
}
```

4. 在 Figma 中切换 Token Set 即可预览暗色模式

---

## 📊 24 列栅格系统在 Figma 中使用

### 创建 24 列布局网格

1. 选择 Frame（画板）
2. 右侧面板 → **Layout Grid**
3. 点击 **+** 添加网格
4. 配置：
   - Type: **Columns**
   - Count: **24**
   - Margin: **32px**（桌面）
   - Gutter: **16px**（使用 `{spacing.4}`）

### B端常见布局示例

**表单布局（标签 + 输入框）：**
```
标签：span 4（1/6 宽度）
输入框：span 8（1/3 宽度）
空白：span 12（1/2 宽度）
```

**三列卡片：**
```
每列：span 8（24 ÷ 3 = 8）
间隙：16px
```

**五列数据网格：**
```
每列：span 4-5（24 ÷ 5 ≈ 4.8）
12 列系统无法整除！
```

---

## ⚠️ 常见问题

### Q1: 导入后找不到 Token？

**解决方案：**
- 确认 Token Set 已启用（Toggle 开关打开）
- 检查 JSON 文件格式是否正确
- 尝试重启插件

### Q2: Token 值无法应用到图层？

**解决方案：**
- 某些属性需要先创建 Style（如颜色、文本）
- 直接拖拽 Token 到属性上
- 使用 `${}` 引用语法（如 `{spacing.4}`）

### Q3: 如何批量更新 Token？

**解决方案：**
- 修改 `tokens.json` 文件
- 重新导入到 Tokens Studio
- 所有使用该 Token 的元素自动更新

### Q4: 如何团队协作？

**解决方案：**
- 使用 Tokens Studio 的 **Sync** 功能
- 配置 GitHub/GitLab 同步
- 团队成员自动获取最新 Token

---

## 📚 相关资源

- [Tokens Studio 官方文档](https://docs.tokens.studio/)
- [Design Tokens Community Group](https://design-tokens.github.io/community-group/)
- [Material Design Color System](https://m3.material.io/styles/color/system/overview)

---

**文档版本：** v2.0 (Material Design)
**最后更新：** 2025-11-16
**维护者：** 设计系统团队
