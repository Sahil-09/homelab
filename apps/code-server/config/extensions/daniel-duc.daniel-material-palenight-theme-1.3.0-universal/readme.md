# Material Palenight Theme

A sleek, modern Visual Studio Code theme inspired by Material Palenight, designed for a visually appealing and comfortable coding experience.

## 🎨 Preview

![](https://res.cloudinary.com/daniel-duc/image/upload/v1762442225/Screenshot_From_2025-11-06_22-15-03_vsgb1r.png)

## ✨ Features

- 🎨 Rich, vibrant colors with a dark aesthetic
- 🌙 Optimized for readability and contrast
- 🚀 Supports 20+ programming languages
- 👁️ Colorblind-friendly design
- 🎯 Semantic highlighting
- 🖥️ Perfect for both light and extended coding sessions

## 📦 Installation

1. Open **Visual Studio Code**
2. Go to **Extensions** (`Ctrl+Shift+X`)
3. Search for `Material Palenight Theme`
4. Click **Install**
5. Open the **Command Palette** (`Ctrl+Shift+P`).
6. Select **Preferences: Color Theme** and choose `Material Palenight Theme`.

## 🎨 Color Palette

The theme features a carefully curated color palette:

- **Background**: `#292D3E` - Deep, comfortable dark background
- **Foreground**: `#babed8` - Soft, readable text
- **Primary**: `#89DDFF` - Bright blue for keywords and important elements
- **Secondary**: `#f07178` - Coral for variables and properties
- **Accent**: `#C3E88D` - Green for strings and literals
- **Function**: `#82AAFF` - Light blue for functions
- **Type**: `#FFCB6B` - Yellow for types and classes

## 🔧 Customization

### Basic Customization

```json
{
  "workbench.colorCustomizations": {
    "editor.background": "#1E1E2E",
    "editor.foreground": "#babed8"
  }
}
```

### Advanced Customization

You can override specific token colors by adding to your settings:

```json
{
  "editor.tokenColorCustomizations": {
    "textMateRules": [
      {
        "scope": "string.quoted",
        "settings": {
          "foreground": "#C3E88D"
        }
      }
    ]
  }
}
```

## 📊 Theme Statistics

- **Version**: 1.3.0
- **VS Code Compatibility**: ^1.43.0
- **License**: MIT
- **Publisher**: daniel-duc

## 🐛 Troubleshooting

### Common Issues

**Theme not showing up**

- Restart VS Code after installation
- Check if the theme is properly installed in `~/.vscode/extensions/`

**Colors look different than expected**

- Check if you have any other color theme extensions conflicting
- Reset your workspace settings with `Ctrl+Shift+P` > `Preferences: Open Settings (JSON)`

## 📄 License

This project is licensed under the MIT License.

---

Made with ❤️ by [Daniel Duc](https://github.com/binhduc1211)
