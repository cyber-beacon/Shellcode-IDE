# Shellcode-IDE (v0.1.13)
Author: **CX330Blake**

_## Demo

https://github.com/user-attachments/assets/8a0cbc62-4f29-417f-a1d1-6d3005a1be41

## What the project does

Shellcode-IDE is a powerful Binary Ninja plugin designed for reverse engineers, CTF players, exploit developers, and security researchers. It provides a comprehensive environment for developing and analyzing shellcode with a user-friendly GUI that combines Binary Ninja's assembler/disassembler capabilities for rapid iteration and safe validation of shellcode.

### Key Features

- **Two-way conversion**: Raw bytes/hex ↔ assembly text
- **Multi-architecture support**: Assemble for any Binary Ninja architecture/platform
- **Multiple export formats**: Inline `\x..`, raw hex, C stub, Python stub, Zig stub, Rust stub, Go stub
- **Live metadata**: Byte length, instruction count, null count, endianness, architecture
- **Configurable bad-pattern detection**: e.g., `00`, `0a`, `ff`, sequences, regex
- **Peephole optimizations**: With preview/confirm (e.g., `push 0` → `xor reg, reg; push reg`)
- **Validation rules**: No variables/labels, no absolute addresses/relocations, no nulls (unless allowed)
- **Binary Ninja integration**: Menu + toolbar + dockable/floating Qt window with shortcuts

## Why the project is useful

Shellcode-IDE streamlines the shellcode development workflow by providing:

- **Rapid iteration**: Quickly test and validate shellcode snippets without external tools
- **Architecture flexibility**: Work across different architectures with a single interface
- **Safety checks**: Built-in validation prevents common shellcode issues like null bytes
- **Optimization**: Improve your shellcode with intelligent peephole optimizations
- **Multi-format export**: Generate code snippets for various programming languages
- **Integration**: Seamlessly integrates into Binary Ninja's ecosystem

## How users can get started

### Prerequisites

- Binary Ninja (licensed), with Python API available
- Python 3.8+ (matching your Binary Ninja build)
- Qt via PySide2 (Binary Ninja typically bundles PySide2; no manual install required)

### Installation

You can install as a user plugin. The typical plugin directories are:

- **macOS**: `~/Library/Application Support/Binary Ninja/plugins`
- **Linux**: `~/.binaryninja/plugins`
- **Windows**: `%APPDATA%\Binary Ninja\plugins`

#### Manual Install

1. Close Binary Ninja
2. Clone or copy this repository into your plugins directory as `Shellcode-IDE`

    - **Example (macOS/Linux)**:

        ```bash
        cd "~/Library/Application Support/Binary Ninja/plugins"  # macOS
        # or cd ~/.binaryninja/plugins  # Linux
        git clone https://github.com/CX330Blake/Shellcode-IDE.git Shellcode-IDE
        ```

3. Start Binary Ninja. The plugin registers a Tools menu entry and a toolbar icon

#### Platform-specific Instructions

**macOS**:

```bash
cd "~/Library/Application Support/Binary Ninja/plugins"
git clone https://github.com/CX330Blake/Shellcode-IDE Shellcode-IDE
```

**Linux**:

```bash
cd ~/.binaryninja/plugins
git clone https://github.com/CX330Blake/Shellcode-IDE Shellcode-IDE
```

**Windows (PowerShell)**:

```powershell
cd "$env:APPDATA\Binary Ninja\plugins"
git clone https://github.com/CX330Blake/Shellcode-IDE Shellcode-IDE
```

After installation, restart Binary Ninja or use "Reload Plugins".

### Quick Start

#### To disassemble bytes/hex to assembly

1. Open Shellcode IDE from `Tools → Shellcode IDE` or toolbar icon
2. Select target `Architecture`/`Platform` (defaults to active view when available)
3. Paste hex/bytes into the "Hex/Bytes" tab (supports whitespace, `0x` prefixes, and `\x..` forms)
4. Click "Disassemble". View assembly in the output panel and stats in the status bar
5. Export via the "Formats" tab (copy or save to file)

#### To assemble assembly to shellcode

1. Switch to the "Assembly" tab and enter one instruction per line
2. Click "Assemble". Errors (if any) show inline with line/column info
3. Review live stats, run "Optimize" (optional), "Validate", and export in your preferred format

### Usage Examples

**Basic Assembly:**

```
mov rax, 0x3b
mov rdi, 0x68732f6e69622f
push rdi
mov rsi, rsp
xor rdx, rdx
syscall
```

**Hex Input:**

```
90 90 48 c7 c0 3b 00 00 00 48 c7 c7 2f 62 69 6e 2f 73 68 57 48 89 e6 48 31 d2 0f 05
```

or

```
\x90\x90\x48\xc7\xc0\x3b\x00\x00\x00\x48\xc7\xc7\x2f\x62\x69\x6e\x2f\x73\x68\x57\x48\x89\xe6\x48\x31\xd2\x0f\x05
```

## Where users can get help

- **Documentation**: Refer to the detailed information in this README
- **Issues**: Report bugs or request features at [GitHub Issues](https://github.com/CX330Blake/Shellcode-IDE/issues)
- **Binary Ninja Community**: Join the Binary Ninja community forums for plugin-related questions
- **Source Code**: Browse the source code in this repository for implementation details

## Who maintains and contributes

### Maintainer

- **CX330Blake** - Original author and current maintainer

### Contributing

Contributions are welcome! Please open issues for bugs/ideas and submit focused PRs.

#### Development Setup

1. Clone the repository into your Binary Ninja plugins directory
2. Install dependencies: `pip install -r requirements.txt`
3. Restart Binary Ninja or use "Reload Plugins"

#### For Developers

- **Tech stack**: Python 3.8+, Binary Ninja Python API, PySide2
- Keep changes minimal and scoped to the task
- Match the existing code style and structure
- Include tests for new logic where practical

### Dependencies

The plugin requires the following dependencies:

- `pygments>=2.12`
- `keystone-engine>=0.9.2`

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details._

## Description:

Shellcode IDE — makes developing and analyzing shellcode much more convenient.


## Installation Instructions

### Darwin

macOS:
cd "~/Library/Application Support/Binary Ninja/plugins"
git clone https://github.com/CX330Blake/Shellcode-IDE Shellcode-IDE
Restart Binary Ninja or use "Reload Plugins".

### Linux

Linux:
cd ~/.binaryninja/plugins
git clone https://github.com/CX330Blake/Shellcode-IDE Shellcode-IDE
Restart Binary Ninja or use "Reload Plugins".

### Windows

Windows (PowerShell or CMD):
cd "%APPDATA%\Binary Ninja\plugins"
git clone https://github.com/CX330Blake/Shellcode-IDE Shellcode-IDE
Restart Binary Ninja or use "Reload Plugins".

## Minimum Version

This plugin requires the following minimum version of Binary Ninja:

* 3164



## Required Dependencies

The following dependencies are required for this plugin:

 * pip - pygments>=2.12, keystone-engine>=0.9.2
 * apt - 
 * installers - 
 * other - Requires Binary Ninja with Python API (licensed)., PySide2 is bundled with Binary Ninja; no extra install typically required.


## License

This plugin is released under a MIT license.
## Metadata Version

2
