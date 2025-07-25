# 🚀 My Terminal Setup (Dotfiles)

A modern, beautiful terminal configuration featuring Zsh, Oh My Zsh, Powerlevel10k, and Ghostty with custom shaders!

## 🎨 What's Included

### Shell Configuration
- **Zsh** - Modern shell with enhanced features
- **Oh My Zsh** - Framework for managing Zsh configuration
- **Powerlevel10k** - Fast and customizable Zsh theme
- **Plugins**: git, z, zsh-autosuggestions, zsh-syntax-highlighting, zsh-completions

### Terminal Emulator
- **Ghostty** - Modern terminal emulator with GPU acceleration (if u run all this shit with no gpu, its fine but the galaxy part of it might lag slightly)
- **Custom Shaders**: 
  - `bloom025.glsl` - Subtle glow effect ✨
  - `cursor_smear.glsl` - Smooth cursor trails 🌊  
  - `starfield.glsl` - Animated starfield background ⭐
- **Background blur and transparency** for that modern aesthetic
- **JetBrainsMono Nerd Font** for beautiful icons and text

## 🔧 Setup Instructions

### Prerequisites
- macOS (tested on macOS)
- [Homebrew](https://brew.sh/)
- [Ghostty](https://ghostty.org/)
- Git configured with your credentials

### Installation

1. **Clone this repository**
   ```bash
   git clone https://github.com/yourusername/dotfiles.git ~/dotfiles-backup
   cd ~/dotfiles-backup
   ```

2. **Backup your existing configs** (optional but recommended)
   ```bash
   mv ~/.zshrc ~/.zshrc.backup 2>/dev/null || true
   mv ~/.p10k.zsh ~/.p10k.zsh.backup 2>/dev/null || true
   mv ~/.oh-my-zsh ~/.oh-my-zsh.backup 2>/dev/null || true
   mv ~/.config/ghostty ~/.config/ghostty.backup 2>/dev/null || true
   ```

3. **Install Oh My Zsh** (if not already installed)
   ```bash
   sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

4. **Install Powerlevel10k theme**
   ```bash
   git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
   ```

5. **Install Zsh plugins**
   ```bash
   # zsh-autosuggestions
   git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
   
   # zsh-syntax-highlighting
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
   
   # zsh-completions
   git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh}/custom}/plugins/zsh-completions
   ```

6. **Copy configuration files**
   ```bash
   cp .zshrc ~/
   cp .p10k.zsh ~/
   cp .zprofile ~/ 2>/dev/null || true
   cp -R ghostty ~/.config/
   ```

7. **Install JetBrainsMono Nerd Font**
   ```bash
   brew tap homebrew/cask-fonts
   brew install --cask font-jetbrains-mono-nerd-font
   ```

8. **Restart your terminal** or run:
   ```bash
   source ~/.zshrc
   ```

## ⚡ Performance Notes

### Known Issues & Solutions
- **Powerlevel10k Instant Prompt**: Currently disabled due to compatibility issues with Ghostty shaders
- **Shader Compatibility**: `cursor_blaze.glsl` was found to cause terminal glitching and has been disabled
- **Working Shaders**: The current combination of bloom025 + cursor_smear + starfield is stable

### Optimizations
- Instant prompt disabled for stability
- Lightweight shader combination for best performance
- Background opacity and blur optimized for macOS

## 🎮 Shader Details

The Ghostty configuration includes a curated collection of shaders:

**✅ Active Shaders:**
- `bloom025.glsl` - Subtle text glow effect
- `cursor_smear.glsl` - Smooth cursor motion trails  
- `starfield.glsl` - Subtle animated star background

**🚫 Problematic Shaders:**
- `cursor_blaze.glsl` - Causes terminal flickering (disabled)

**📁 Additional Shaders Available:**
Check the `ghostty/shaders/` directory for more effects you can experiment with!

## 🛠 Customization

### Changing Shaders
Edit `~/.config/ghostty/config` and modify the `custom-shader` lines:

```bash
# Example: Try different bloom intensities
# custom-shader = shaders/bloom050.glsl  # More intense
# custom-shader = shaders/bloom025.glsl  # Subtle (current)
```

### P10k Configuration
Run the configuration wizard to customize your prompt:
```bash
p10k configure
```

### Zsh Plugins
Add more plugins by editing the `plugins=()` line in `~/.zshrc`

## 📝 File Structure

```
dotfiles/
├── .zshrc                 # Zsh configuration
├── .p10k.zsh             # Powerlevel10k theme config
├── .zprofile             # Zsh profile
├── .oh-my-zsh/           # Oh My Zsh framework
├── ghostty/              # Ghostty terminal config
│   ├── config            # Main Ghostty config
│   ├── ghostty-theme     # Color theme
│   └── shaders/          # Custom shader collection
└── README.md             # This file
```

## 🐛 Troubleshooting

### Terminal Flickering
- Make sure Powerlevel10k instant prompt is disabled
- Try disabling individual shaders to isolate issues

### Font Issues  
- Ensure JetBrainsMono Nerd Font is installed
- Restart Ghostty after font installation

### Slow Performance
- Reduce the number of active shaders
- Disable background blur if needed

## 🤝 Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements!

## 📄 License

This configuration is provided as-is. Feel free to use and modify as needed!

---

**Enjoy your beautiful terminal! 🎉**
