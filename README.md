# Hugo Butterfly Theme

A modern blog theme for Hugo, inspired by the popular Hexo Butterfly theme.

## ✨ Features

- 🎨 **Modern Design** - Card-based layout with beautiful aesthetics
- 🌓 **Dark Mode** - Support for light/dark theme with auto-switching
- 🎯 **8 Color Schemes** - Built-in cool and warm tone themes, customizable
- 📱 **Responsive Design** - Perfect adaptation for mobile, tablet, and desktop
- ⚡ **Fast Loading** - Optimized resources and high-performance code
- 🔍 **Search Function** - Built-in Pagefind search support
- 🌐 **Multi-language Support** - Built-in internationalization (i18n) configuration

## 🚀 Quick Start

### Step 1: Clone the theme to your Hugo site

```bash
git clone https://github.com/ouraihub-hugo-themes/hugo-butterfly.git themes/hugo-butterfly
```

### Step 2: Configure the theme

Set the theme in your Hugo configuration file:

**If using config.toml:**
```toml
theme = "hugo-butterfly"
```

**If using config.yaml:**
```yaml
theme: hugo-butterfly
```

**If using config/_default/ structure:**
Add the above configuration in `config/_default/hugo.toml` or `config/_default/hugo.yaml`.

### Step 3: Start Hugo

```bash
hugo server
```

Visit `http://localhost:1313` to view your site.

## 📁 File Structure

The release version includes the following directories:

```
hugo-butterfly/
├── layouts/              # Hugo template files
├── static/               # Static assets (images, fonts, etc.)
├── assets/               # Compiled styles and scripts
│   ├── css/             # CSS style files
│   └── js/              # JavaScript files
├── config/               # Theme configuration examples
│   └── _default/        # Default configuration
├── i18n/                # Multi-language translation files
├── archetypes/          # Article templates
└── theme.toml           # Theme configuration file
```

## ⚙️ Configure the Theme

### Basic Configuration

Set the following in your site configuration (usually `config/_default/params.toml` or `config.toml`):

```toml
# Site description
description = "A blog powered by Hugo Butterfly theme"

# Site keywords
keywords = ["Hugo", "Blog", "Butterfly"]

# Author information
[author]
  name = "Your Name"
  avatar = "/images/avatar.png"
  description = "A brief introduction about you"

# Dark mode settings
[darkmode]
  enable = true
  button = true
  autoChangeMode = false
```

### More Configuration Options

For detailed configuration options, check the `config/_default/params.toml` file. The theme supports the following customizations:

- Site basic information (title, description, keywords)
- Author information and avatar
- Theme color settings
- Dark mode preferences
- Comment system integration
- Analytics and statistics
- Social media links
- Menu configuration

## 🎨 Theme Colors

The theme comes with 8 carefully designed color schemes:

**Cool Tones:**
- 🔵 Sapphire Blue
- 💜 Royal Purple
- 🌊 Fresh Cyan
- 🩶 Cool Gray

**Warm Tones:**
- ❤️ Crimson Red
- 🧡 Warm Orange
- 💕 Cherry Pink
- 🟤 Autumn Brown

Choose your preferred color scheme in the theme settings.

## 🌍 Multi-language Support

The theme supports multiple languages. Add language configuration in Hugo:

```toml
[languages]
  [languages.en]
    title = "My Blog"
    languageName = "English"
    weight = 1

  [languages.zh]
    title = "我的博客"
    languageName = "中文"
    weight = 2
```

Translation files are located in the `i18n/` directory.

## 📝 Creating Posts

Create a new post:

```bash
hugo new content/posts/my-first-post.md
```

Post templates use `archetypes/default.md`.

## 🔍 Search Feature

The theme uses Pagefind to provide search functionality. The search configuration file is `pagefind.yml`.

By default, the search feature is enabled. Users can use the search bar to find posts.

## 🐛 Feedback & Issues

If you encounter any issues or have suggestions, please visit:
- Development Repository: https://github.com/ouraihub/hugo-butterfly/issues

## 📄 License

MIT License - See LICENSE file for details

## 🙏 Acknowledgments

- [Hexo Butterfly Theme](https://github.com/jerryc127/hexo-theme-butterfly) - Design inspiration
- [Hugo](https://gohugo.io/) - Static site generator
- [Tailwind CSS](https://tailwindcss.com/) - CSS framework

---

**Latest Version**: Check [GitHub Releases](https://github.com/ouraihub-hugo-themes/hugo-butterfly/releases) for the latest version information.
