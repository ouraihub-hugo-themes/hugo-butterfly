# Hugo Butterfly Theme

一个基于 Hugo 的现代化博客主题，灵感来自流行的 Hexo Butterfly 主题。

## 特性

- 🎨 **现代化设计** - 卡片式布局，视觉美观
- 🌓 **暗色模式** - 支持亮色/暗色主题自动切换
- 📱 **响应式设计** - 完美适配移动端、平板和桌面设备
- ⚡ **极速构建** - 基于 Hugo 的超快构建速度
- 🔒 **类型安全** - 使用 TypeScript 开发交互功能
- �  **现代化样式** - 采用 Tailwind CSS v4 实现样式系统

## 技术栈

- **Hugo Extended** v0.120.0+ - 静态网站生成器
- **TypeScript** 5.3+ - 类型安全的 JavaScript
- **Tailwind CSS** v4.1+ - 现代化 CSS 框架
- **esbuild** 0.20+ - 极速 TypeScript 编译器
- **pnpm** 10+ - 快速的包管理器

## 快速开始

### 前置要求

- Hugo Extended v0.120.0+
- Node.js 18+
- pnpm 10+

### 安装

#### 用户使用（推荐）

```bash
# 克隆发布版本（最终用户使用）
git clone https://github.com/ouraihub-hugo-themes/hugo-butterfly.git themes/hugo-butterfly
```

#### 开发者修改

```bash
# 克隆开发仓库（贡献者用）
git clone https://github.com/ouraihub/hugo-butterfly.git

# 进入主题目录
cd hugo-butterfly

# 安装依赖
pnpm install
```

### 开发

```bash
# 启动开发服务器（推荐）
pnpm run dev

# 快速开发模式（不编译 TS/CSS）
pnpm run dev:fast

# 类型检查
pnpm run type-check
```

开发服务器将在 `http://localhost:1313` 启动，支持热重载。

### 构建

```bash
# 构建生产版本
pnpm run build

# 构建开发版本
pnpm run build:dev

# 构建测试版本
pnpm run build:staging

# 预览生产构建
pnpm run preview
```

### 搜索功能编译

Hugo Butterfly主题使用 [Pagefind](https://pagefind.app/) 提供全文搜索功能。搜索索引需要在构建网站后单独编译。

#### 自动编译（推荐）

在执行 `pnpm run build` 时，搜索索引会自动生成：

```bash
pnpm run build
```

#### 手动编译

如果需要单独编译搜索索引：

```bash
pnpm exec pagefind --site public --output-subdir _pagefind --force-language zh
```

### 清理

```bash
# 清理所有构建文件和缓存
pnpm run clean

# 仅清理构建文件
pnpm run clean:build

# 仅清理缓存
pnpm run clean:cache
```

## 项目结构

```
hugo-butterfly/
├── assets/              # 需要编译的资源
│   ├── ts/             # TypeScript 源文件
│   ├── js/             # 编译后的 JavaScript
│   └── css/            # Tailwind CSS 源文件
├── config/             # 多环境配置
│   ├── _default/       # 默认配置
│   ├── development/    # 开发环境
│   ├── staging/        # 测试环境
│   └── production/     # 生产环境
├── layouts/            # Hugo 模板文件
│   ├── _default/       # 默认模板
│   └── partials/       # 可复用组件
├── static/             # 静态资源
└── i18n/              # 多语言翻译
```

## 配置

### 环境配置

主题支持三种环境配置：

- **development** - 开发环境，显示草稿，禁用压缩
- **staging** - 测试环境，部分压缩，启用调试
- **production** - 生产环境，完全压缩，优化性能

配置文件位于 `config/` 目录：

- `_default/` - 基础配置（所有环境共享）
- `development/` - 开发环境覆盖配置
- `staging/` - 测试环境覆盖配置
- `production/` - 生产环境覆盖配置

### 主题参数

在 `config/_default/params.toml` 中配置主题参数：

```toml
# 网站基础信息
description = "一个基于 Hugo 的 Butterfly 主题博客"
keywords = ["Hugo", "博客", "Butterfly"]

# 作者信息
[author]
  name = "Your Name"
  avatar = "/images/avatar.png"
  description = "这是我的个人简介"

# 暗色模式
[darkmode]
  enable = true
  button = true
  autoChangeMode = false
```

更多配置选项请参考 `config/_default/params.toml` 文件。

## 开发指南

### TypeScript 开发

TypeScript 源文件位于 `assets/ts/` 目录：

```
assets/ts/
├── types/       # 类型定义
├── utils/       # 工具函数
├── modules/     # 功能模块
└── main.ts      # 入口文件
```

添加新模块：

1. 在 `assets/ts/modules/` 创建新文件
2. 导出初始化函数
3. 在 `main.ts` 中导入并调用

### 样式开发

使用 Tailwind CSS v4 开发样式：

```css
/* assets/css/main.css */

@theme {
  /* 自定义设计令牌 */
  --color-primary: #49B1F5;
}

@layer components {
  /* 自定义组件样式 */
  .card {
    @apply bg-white rounded-xl shadow-md;
  }
}
```

### 模板开发

Hugo 模板位于 `layouts/` 目录：

- `_default/baseof.html` - 基础模板
- `partials/` - 可复用组件
- `index.html` - 首页模板

## 常用开发操作

### 日常开发

```bash
# 启动开发服务器（最常用）
pnpm run dev

# 类型检查
pnpm run type-check

# 运行测试
pnpm run test:unit
```

### 版本发布

```bash
# 自动发布（推荐）- 根据 commit 自动判断版本
pnpm release

# 手动指定版本类型
pnpm release:patch    # Bug 修复：1.0.0 -> 1.0.1
pnpm release:minor    # 新功能：1.0.0 -> 1.1.0
pnpm release:major    # 破坏性更新：1.0.0 -> 2.0.0
```

**Commit 规范**（影响自动版本号）：
```bash
# 新功能（触发 minor）
git commit -m "feat: 添加主题切换功能"

# Bug 修复（触发 patch）
git commit -m "fix: 修复暗色模式按钮颜色"

# 破坏性更新（触发 major）
git commit -m "feat!: 重构配置系统

BREAKING CHANGE: 配置格式已更改"

# 其他（不触发版本更新）
git commit -m "docs: 更新文档"
git commit -m "style: 格式化代码"
git commit -m "test: 添加测试"
```

详细发布指南：[docs/development/RELEASE_GUIDE.md](docs/development/RELEASE_GUIDE.md)

## 脚本说明

### TypeScript 脚本

- `ts:build` - 编译并压缩 TypeScript（生产）
- `ts:watch` - 监听模式编译 TypeScript
- `ts:dev` - 编译 TypeScript 带 sourcemap（开发）

### CSS 脚本

- `css:build` - 编译并压缩 CSS（生产）
- `css:watch` - 监听模式编译 CSS
- `css:dev` - 编译 CSS（开发）

### Hugo 脚本

- `dev` - 启动完整开发环境（TS + CSS + Hugo）
- `dev:fast` - 快速开发模式（仅 Hugo）
- `build` - 构建生产版本
- `preview` - 预览生产构建

### 测试脚本

- `test:unit` - 运行单元测试
- `test` - 运行所有测试

### 工具脚本

- `type-check` - TypeScript 类型检查
- `validate` - 验证配置和构建
- `clean` - 清理构建文件

## 浏览器兼容性

- Chrome/Edge 最新版
- Firefox 最新版
- Safari 最新版
- 移动端浏览器（iOS Safari, Chrome Mobile）

## 许可证

MIT License

## 贡献

欢迎提交 Issue 和 Pull Request！

## 致谢

- [Hexo Butterfly Theme](https://github.com/jerryc127/hexo-theme-butterfly) - 设计灵感来源
- [Hugo](https://gohugo.io/) - 强大的静态网站生成器
- [Tailwind CSS](https://tailwindcss.com/) - 现代化 CSS 框架
