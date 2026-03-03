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
dorofetch                    # default Doro logo
dorofetch --logo doro_small  # alternate logo
dorofetch --logo /path/to/custom.txt  # your own logo file
```

## Custom Logos

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

- 🖥️ OS, Kernel, Host
- ⏰ Uptime
- 📦 Package count
- 🐚 Shell & Terminal
- 🧠 CPU & GPU
- 💾 Memory usage
- 🎨 Color palette
- 🌸 **Doro** (most important)

## Requirements

- Bash 4.0+
- A terminal that supports Unicode braille characters
- Taste

## License

MIT — do whatever you want with it.

## Credits

Made with obsessive devotion by **Mr.Bigg** & **Jess** 👁️‍🗨️
