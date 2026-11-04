# Han

[中文](README.md)

Han (Human-Agent Notation) is a systems programming language. Source files use the `.han` extension. Programs are written in straight-line code; the compiler translates them to C and then to a native binary.

This repository is named Hanc. It publishes versioned release files for the Han project. Compiler source and design documents are not stored here.

## Download

Open the Releases page of this repository and pick a version. Each Release matches one Git tag, and both use the same version string.

Read that version's release notes first, then check every asset against the `SHA256SUMS` file in the same Release. The version string on the Release title is the one that counts.

| Asset | Contents |
| --- | --- |
| Release notes | Which files this version contains, and where they run |
| `SHA256SUMS` | SHA-256 for every asset in this Release |
| Release files | The compiler and tool packages actually shipped for that version; names include the version and target platform |

A published tag is left unchanged. When a version is withdrawn, its Release notes name the version that replaces it.

## Tools

| Command | Role |
| --- | --- |
| `han` | Everyday entry. Compiles and runs a single file directly; hands a project with a build config to `hake` |
| `h2c` | Core compiler. Translates `.han` to C. `.v` files are still compiled as V |
| `hake` | Project builds: dependencies, mixed-language compile, and link |
| `vp` | Transitional tool for V compatibility. Everyday Han sources go through `han` |

`h2cpp`, `h2js`, and `h2llvm` are not shipped as release files yet.

## What the language is already aimed at

- Functions stay ordinary declarations. The compiler recognizes calls that may pause; concurrent start uses `launch` / `async`
- Builds and dependencies are described to Hake instead of being assembled from loose scripts
- C is compiled and linked in the same build. V sources can still go through the same toolchain

Syntax and APIs for a given version are those named by that version's release notes.
