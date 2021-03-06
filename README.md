# Deno for Visual Studio Code

![GitHub Workflow Status](https://img.shields.io/github/workflow/status/denoland/vscode_deno/ci)

![Visual Studio Marketplace Version](https://img.shields.io/visual-studio-marketplace/v/denoland.vscode-deno)
![Visual Studio Marketplace Installs](https://img.shields.io/visual-studio-marketplace/i/denoland.vscode-deno)
![Visual Studio Marketplace Downloads](https://img.shields.io/visual-studio-marketplace/d/denoland.vscode-deno)
![Visual Studio Marketplace Rating (Stars)](https://img.shields.io/visual-studio-marketplace/stars/denoland.vscode-deno)

<img align="right" src=https://raw.githubusercontent.com/denoland/vscode_deno/main/deno.png height="150px">

This extension adds support for using [Deno](https://deno.land/) with Visual
Studio Code, powered by `deno lsp`.

> ⚠️ **Important:** You need to have a version of Deno CLI installed (v1.6 or
> later) and available in your path before attempting to use this extension.
> [Check here](https://deno.land/#installation) for instructions on how to
> install the Deno CLI.

![Basic Usage of the Extension](screenshots/basic_usage.gif)

## Features

- Type checking for JavaScript and TypeScript, including quick fixes, hover
  cards, intellisense, and more.
- Integrates with the version of the Deno CLI you have installed, ensuring there
  is alignment between your editor and the Deno CLI.
- Resolution of modules in line with Deno CLI's module resolution strategy
  allows caching of remote modules in Deno CLI's cache.
- Integration to Deno CLI's linting functionality, including inline diagnostics
  and hover cards.
- Integration to Deno CLI's formatting functionality.
- Allow specifying of import maps and TypeScript configuration files that are
  used with the Deno CLI.

## Usage

1. Install the Deno CLI, available in your path.
2. Install this extension.
3. Open the VS Code command palette with `Ctrl+Shift+P`, and run the
   `Deno Language Server: Initialize Workspace Configuration` command.

## Configuration

You can control the settings for this extension through your VS Code settings
page. You can open the settings page using the `Ctrl+,` keyboard shortcut. The
extension has the following configuration options:

- `deno.enable`: Controls if the Deno Language Server is enabled. When enabled,
  the extension will disable the built-in VSCode JavaScript and TypeScript
  language services, and will use the Deno Language Server (`deno lsp`) instead.
  _boolean, default `false`_
- `deno.codeLens.references`: Enables or disables the display of code lens
  information for references of items in the code. _boolean, default `false`_
- `deno.codeLens.referencesAllFunctions`: Enables or disables the display of
  code lens information for all functions in the code. Requires
  `deno.codeLens.references` to be enabled as well. _boolean, default `false`_
- `deno.config`: The file path to a `tsconfig.json` file. This is the equivalent
  to using `--config` on the command line. The path can be either be relative to
  the workspace, or an absolute path. _string, default `null`, examples:
  `./tsconfig.json`, `/path/to/tsconfig.json`, `C:\path\to\tsconfig.json`_
- `deno.importMap`: The file path to an import map. This is the equivalent to
  using `--import-map` on the command line.
  [Import maps](https://deno.land/manual/linking_to_external_code/import_maps)
  provide a way to "relocate" modules based on their specifiers. The path can
  either be relative to the workspace, or an absolute path. _string, default
  `null`, examples: `./import-map.json`, `/path/to/import-map.json`,
  `C:\path\to\import-map.json`_
- `deno.lint`: Controls if linting information will be provided by the Deno
  Language Server. _boolean, default `false`_
- `deno.unstable`: Controls if code will be type checked with Deno's unstable
  APIs. This is the equivalent to using `--unstable` on the command line.
  _boolean, default `false`_

## Contribute

We appreciate your help!

To build the extension locally, clone this repository and run the following
steps:

1. Open this folder in VS Code.
2. Run `npm i`.
3. Run `npm run compile`.
4. Run the `Launch Client` launch task from the VSCode debug menu.

Most changes and feature enhancements do not require changes to the extension
though, as most information comes from the Deno Language Server itself, which is
integrated into the Deno CLI. Please check out the
[contribution guidelines](https://github.com/denoland/deno/tree/master/docs/contributing)
for the Deno CLI.

## Thanks

This project was inspired by
[justjavac/vscode-deno](https://github.com/justjavac/vscode-deno) and
[axetroy/vscode-deno](https://github.com/axetroy/vscode-deno). Thanks for their
contributions.

## License

The [MIT License](LICENSE)
