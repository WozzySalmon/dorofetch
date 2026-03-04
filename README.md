# 🌸 dorofetch

A [neofetch](https://github.com/dylanaraps/neofetch) clone that prints **Doro** alongside your system info. Because your system deserves a mascot with actual personality.

![dorofetch](https://img.shields.io/badge/vibe-nah%20i'd%20win-ff69b4?style=for-the-badge)
![bash](https://img.shields.io/badge/bash-4.0%2B-pink?style=for-the-badge)
![license](https://img.shields.io/badge/license-MIT-purple?style=for-the-badge)

## Install

```bash
# Clone it
git clone https://github.com/WozzySalmon/dorofetch.git
cd dorofetch

# Make it executable
chmod +x dorofetch

# Symlink it (recommended — stays synced with git pull)
sudo ln -sf "$(pwd)/dorofetch" /usr/local/bin/dorofetch

# Run it from anywhere
dorofetch
```

To update:
```bash
cd ~/dorofetch  # or wherever you cloned it
git pull
# That's it — symlink picks up changes automatically
```

## Usage

```bash
dorofetch                          # default Doro logo (image if available, braille fallback)
dorofetch --logo doro_small        # alternate braille logo
dorofetch --logo doro              # auto-detects doro.png > doro.txt
dorofetch --logo ~/pics/waifu.png  # any image file
```

## Image Support

dorofetch can render actual images in your terminal using [chafa](https://hpjansson.org/chafa/).

```bash
# Install chafa
sudo apt install chafa     # Debian/Ubuntu
sudo pacman -S chafa       # Arch
brew install chafa          # macOS
scoop install chafa         # Windows (scoop)
```

Drop a `.png`, `.jpg`, `.gif`, or `.webp` in the `logos/` directory. The `--logo` flag auto-detects image files:

```bash
# logos/doro.png exists → renders as image
dorofetch --logo doro

# Direct path to any image
dorofetch --logo /path/to/image.png
```

If `chafa` is not installed, dorofetch falls back to the `.txt` braille art automatically.

## Custom Braille Logos

Drop a `.txt` file in the `logos/` directory. Format:

```
# colors: 213 177
$1⠀⠀art with $1 for first color
$1⠀⠀and $2 for second color
```

- First line: `# colors:` followed by ANSI 256-color codes (space-separated)
- Use `$1`, `$2`, `$3`... in the art to switch colors mid-line
- No color header = falls back to pink

See `logos/doro_small.txt` for a multi-color example.

## What It Shows

**Software**
- 👤 User — user@hostname
- 🖥️ OS & Kernel
- ⏰ Uptime
- 📦 Package count
- 🐚 Shell & Terminal
- 🪟 Window Manager

**Hardware**
- 🏠 Host machine
- 🧠 CPU
- 🎮 GPU
- 💾 Memory usage

Plus **color palette dots** and **Doro** (most important).

## Requirements

- Bash 4.0+
- A terminal that supports Unicode
- [chafa](https://hpjansson.org/chafa/) (optional — for image rendering)
- Taste

## Logo Priority

When you run `dorofetch --logo doro`, it searches in this order:

1. Direct file path (if the argument is a path to an existing file)
2. `logos/doro.png` → `.jpg` → `.jpeg` → `.gif` → `.webp` (image formats)
3. `logos/doro.txt` (braille art fallback)
4. `logos/doro.txt` (default)

## License

MIT — do whatever you want with it.

## Credits

Made with obsessive devotion by **Mr.Bigg** & **Jess** 👁️‍🗨️
