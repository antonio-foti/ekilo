# ekilo - Enhanced Kilo [![License: BSD](https://img.shields.io/badge/License-BSD-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)

![eKilo](https://raw.githubusercontent.com/antonio-foti/ekilo/refs/heads/master/eKilo.webp)

**eKilo** is a lightweight terminal text editor based on the original kilo editor with enhanced functions. Its peculiarity is that it can run on any hardware, maintaining a high-performance and useful style. It installs in a minute, if you want to take a look I would be happy, having found a utility myself, having completely replaced vim. Any advice is highly appreciated. 

## Key Features
- **Syntax highlighting**:
  C/C++, Python, Java, JavaScript/TypeScript, C#, PHP, Ruby, Swift, SQL, Rust, Dart
- **Improved terminal resizing**
- **Clean screen exit**
- **Autocompletion**
- **No external dependencies**

## Installation (Linux)
```bash
git clone https://github.com/antonio-foti/ekilo.git
cd ekilo
make
sudo cp ekilo /usr/local/bin/
```

## Uninstallation (Linux)
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
