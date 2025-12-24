# JsMacros Intellisense

A Visual Studio Code extension that provides intelligent TypeScript type hints and autocompletion for [JsMacros](https://github.com/JsMacros/JsMacros) scripts.

## Overview

[JsMacros](https://github.com/JsMacros/JsMacros) is a Minecraft mod that allows you to write JavaScript/TypeScript macros to automate tasks in the game. This VS Code extension enhances your development experience by providing:

- 📝 **IntelliSense support** - Get autocompletion and type hints while writing JsMacros scripts
- 🔄 **Version management** - Download and switch between different JsMacros API versions
- ⚙️ **Configurable** - Customize the extension to work with your specific JsMacros setup
- 🎯 **TypeScript integration** - Seamless integration with VS Code's TypeScript language server

## Features

### Automatic Type Hints

Once configured, the extension automatically provides type definitions for JsMacros APIs, enabling:
- Autocomplete suggestions for JsMacros classes and methods
- Parameter hints for function calls
- Inline documentation from JsMacros TypeScript declarations
- Type checking for your scripts

### Version Management Commands

Access all commands through the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`):

- **`JsMacros Intellisense: fetch newest declarations`** - Download the latest JsMacros TypeScript declarations from GitHub
- **`JsMacros Intellisense: fetch a specific declaration version`** - Download declarations for a specific JsMacros version
- **`JsMacros Intellisense: change the declaration version for your current workspace`** - Switch between installed versions
- **`JsMacros Intellisense: list all currently installed versions`** - View all downloaded declaration versions
- **`JsMacros Intellisense: enable or disable type hints`** - Toggle IntelliSense on/off for the current workspace
- **`JsMacros Intellisense: remove declarations for a specific version`** - Delete downloaded declarations to free up space

## Installation

1. Install the extension from the VS Code Marketplace or from a `.vsix` file
2. Open a workspace where you write JsMacros scripts
3. Run the command **`JsMacros Intellisense: fetch newest declarations`** to download the latest type definitions
4. Start writing your JsMacros scripts with full IntelliSense support!

## Configuration

The extension contributes the following settings that can be configured in your VS Code settings:

### `jsmacros-intellisense.repoUrl`
- **Type:** `string`
- **Default:** `"https://github.com/JsMacros/JsMacros"`
- **Description:** URL to the JsMacros GitHub repository. This is used to fetch TypeScript declarations from releases.
- **Pattern:** Must be a valid GitHub repository URL (`https://github.com/{owner}/{repo}`)

### `jsmacros-intellisense.assetRegExp`
- **Type:** `string`
- **Default:** `"^typescript"`
- **Description:** Regular expression to filter release assets. Used to identify which release asset contains the TypeScript declarations.

### `jsmacros-intellisense.enabledByDefault`
- **Type:** `boolean`
- **Default:** `true`
- **Description:** Whether type hints should be loaded by default when opening a workspace.

## Usage

### Getting Started

1. **Install the extension** and open your JsMacros scripts workspace
2. **Fetch declarations:** Run `JsMacros Intellisense: fetch newest declarations` from the Command Palette
3. **Start coding:** Create or open a `.js` or `.ts` file and start writing JsMacros code
4. **Enjoy IntelliSense:** Type hints and autocompletion will appear automatically as you type

### Switching Versions

If you need to work with a specific version of JsMacros:

1. Run `JsMacros Intellisense: fetch a specific declaration version`
2. Select the version you need from the GitHub releases
3. Run `JsMacros Intellisense: change the declaration version for your current workspace`
4. Select the newly downloaded version

### Managing Storage

Downloaded declarations are stored globally. To free up space:

1. Run `JsMacros Intellisense: list all currently installed versions` to see what's installed
2. Run `JsMacros Intellisense: remove declarations for a specific version` to delete unused versions

## Requirements

- Visual Studio Code version 1.107.0 or higher
- Internet connection to download TypeScript declarations from GitHub

## How It Works

This extension uses a TypeScript server plugin to inject JsMacros type definitions into your workspace. When you fetch declarations:

1. The extension downloads the TypeScript declarations package from the JsMacros GitHub releases
2. Declarations are extracted and stored in VS Code's global storage
3. The TypeScript server plugin loads these declarations
4. IntelliSense becomes available for JsMacros APIs in your scripts

## Known Issues

- Type hints are workspace-specific. You'll need to enable/configure the extension for each workspace
- Switching versions requires reloading the TypeScript server (usually automatic)

## Contributing

Found a bug or have a feature request? Please open an issue on the [GitHub repository](https://github.com/u9g/jsmacros-intellisense).

## License

This extension is open source. Check the repository for license details.

## Links

- [JsMacros GitHub Repository](https://github.com/JsMacros/JsMacros)
- [Report Issues](https://github.com/u9g/jsmacros-intellisense/issues)
