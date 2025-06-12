# ekilo - Enhanced Kilo [![License: BSD](https://img.shields.io/badge/License-BSD-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)

**ekilo** is a lightweight terminal text editor based on the original kilo editor with enhanced functions.

## Key Features
- **Multi-language syntax highlighting**:
  C/C++, Python, Java, JavaScript/TypeScript, C#, PHP, Ruby, Swift, SQL, Rust, Dart
- **Improved terminal resizing**
- **Clean screen exit**
- **Autocompletion**

## Installation
```bash
git clone https://github.com/antonio-foti/ekilo.git
cd ekilo
make
sudo cp ekilo /usr/local/bin/
```

## Uninstallation
```bash
sudo rm /usr/local/bin/ekilo
```

## Usage
```bash
ekilo filename.ext
```

## Keyboard Shortcuts
- **Ctrl-S:** Save file
- **Ctrl-Q:** Quit (press 3 times for unsaved files)
- **Ctrl-F:** Search
- **Ctrl-H:** Backspace/Delete
- **Arrows:** Navigation


## Troubleshooting

If window size is incorrect:
- Press Ctrl-L to refresh
- Resize terminal slowly
- Use supported terminals (xterm, gnome-terminal, etc)


**Note:** Compilation warnings about string truncation can be safely ignored

**License:** BSD 3-Clause (based on original kilo license)

**Acknowledgements:** Original kilo by Salvatore Sanfilippo (antirez)
