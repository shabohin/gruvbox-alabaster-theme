# Gruvbox Alabaster Theme

A VS Code theme combining the warm, retro [Gruvbox Dark Pale](https://github.com/morhetz/gruvbox) color palette with [Alabaster's](https://github.com/tonsky/vscode-theme-alabaster) minimalist syntax highlighting philosophy.

## Features

- 🎨 **Gruvbox Dark Pale Colors**: Warm, muted palette that's easy on the eyes
- ✨ **Minimal Highlighting**: Alabaster-inspired - only highlights what matters
- 🔧 **Complete Coverage**: Full theme for all VS Code UI elements
- 🎯 **OkLab Normalized**: Perceptually uniform transparency values
- 🐠 **Fish Shell Integration**: Matching colors for fish + Tide prompt

## Color Philosophy

This theme follows Alabaster's principle of minimal syntax highlighting:
- **Comments** stand out (italic gray)
- **Strings** are highlighted (aqua/cyan)
- **Constants** are distinct (green)
- **Functions/Classes** have their own color (blue)
- Everything else uses variations of base text colors

## Installation

### From VS Code Marketplace

1. Open VS Code
2. Go to Extensions (Cmd+Shift+X)
3. Search for "Gruvbox Alabaster"
4. Click Install
5. Cmd+K Cmd+T → Select "Gruvbox Alabaster"

### Manual Installation

1. Clone this repository into your VS Code extensions folder:
   ```bash
   git clone https://github.com/shabohin/gruvbox-alabaster-theme.git ~/.vscode/extensions/gruvbox-alabaster-theme
   ```
2. Reload VS Code
3. Cmd+K Cmd+T → Select "Gruvbox Alabaster"

### Development

Create a symlink for live theme development:
```bash
ln -s ~/Develop/gruvbox-alabaster-theme ~/.vscode/extensions/gruvbox-alabaster-theme
```

## Color Palette

### Gruvbox Dark Pale

| Usage | Hex | Preview |
|-------|-----|---------|
| Background (darkest) | `#262626` | ![#262626](https://via.placeholder.com/60x20/262626/262626) |
| Background - | `#3a3a3a` | ![#3a3a3a](https://via.placeholder.com/60x20/3a3a3a/3a3a3a) |
| Background -- | `#4e4e4e` | ![#4e4e4e](https://via.placeholder.com/60x20/4e4e4e/4e4e4e) |
| Foreground - | `#8a8a8a` | ![#8a8a8a](https://via.placeholder.com/60x20/8a8a8a/000000) |
| Foreground + | `#949494` | ![#949494](https://via.placeholder.com/60x20/949494/000000) |
| Foreground ++ | `#dab997` | ![#dab997](https://via.placeholder.com/60x20/dab997/000000) |
| Foreground +++ | `#d5c4a1` | ![#d5c4a1](https://via.placeholder.com/60x20/d5c4a1/000000) |
| Foreground (brightest) | `#ebdbb2` | ![#ebdbb2](https://via.placeholder.com/60x20/ebdbb2/000000) |
| Red | `#d75f5f` | ![#d75f5f](https://via.placeholder.com/60x20/d75f5f/000000) |
| Orange | `#ff8700` | ![#ff8700](https://via.placeholder.com/60x20/ff8700/000000) |
| Yellow | `#ffaf00` | ![#ffaf00](https://via.placeholder.com/60x20/ffaf00/000000) |
| Green | `#afaf00` | ![#afaf00](https://via.placeholder.com/60x20/afaf00/000000) |
| Aqua/Cyan | `#85ad85` | ![#85ad85](https://via.placeholder.com/60x20/85ad85/000000) |
| Blue | `#83adad` | ![#83adad](https://via.placeholder.com/60x20/83adad/000000) |
| Purple | `#d485ad` | ![#d485ad](https://via.placeholder.com/60x20/d485ad/000000) |
| Brown | `#d65d0e` | ![#d65d0e](https://via.placeholder.com/60x20/d65d0e/000000) |

## Fish Shell Integration

This theme includes configuration for Fish shell with Tide prompt. Add to your `~/.config/fish/config.fish`:

```fish
# Gruvbox Dark Pale colors for Fish
set -Ux fish_color_normal dab997
set -Ux fish_color_command 83adad
set -Ux fish_color_quote 85ad85
set -Ux fish_color_redirection d485ad
set -Ux fish_color_end afaf00
set -Ux fish_color_error d75f5f
set -Ux fish_color_param d5c4a1
set -Ux fish_color_comment 949494

# Tide prompt colors (minimalist)
set -Ux tide_pwd_bg_color 3a3a3a
set -Ux tide_pwd_color_dirs 83adad
set -Ux tide_git_bg_color 3a3a3a
set -Ux tide_git_color_branch 85ad85
# ... (see full config in repository)
```

## Credits

- **Gruvbox** by [Pavel Pertsev (morhetz)](https://github.com/morhetz/gruvbox)
- **Gruvbox Dark Pale variant** by [Dawid Kurek](https://github.com/dawikur/base16-gruvbox-scheme)
- **Alabaster philosophy** by [Nikita Prokopov (tonsky)](https://github.com/tonsky/vscode-theme-alabaster)

## License

MIT License - feel free to use and modify!

## Contributing

Found a bug or have a suggestion? [Open an issue](https://github.com/shabohin/gruvbox-alabaster-theme/issues)!
