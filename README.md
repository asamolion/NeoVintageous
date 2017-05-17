# NeoVintageous

[![Build Status](https://travis-ci.org/NeoVintageous/NeoVintageous.svg?branch=master)](https://travis-ci.org/NeoVintageous/NeoVintageous) [![Build status](https://ci.appveyor.com/api/projects/status/g4pkv4ws1k2r1xna/branch/master?svg=true)](https://ci.appveyor.com/project/gerardroche/neovintageous/branch/master) [![Minimum Sublime Version](https://img.shields.io/badge/sublime-%3E%3D%203.0-brightgreen.svg?style=flat-square)](https://sublimetext.com) [![GitHub stars](https://img.shields.io/github/stars/NeoVintageous/NeoVintageous.svg?style=flat-square)](https://github.com/NeoVintageous/NeoVintageous/stargazers) [![Source Code](https://img.shields.io/badge/source-github-blue.svg?style=flat-square)](https://github.com/NeoVintageous/NeoVintageous) [![Latest Stable Version](https://img.shields.io/github/tag/NeoVintageous/NeoVintageous.svg?style=flat-square&label=stable)](https://github.com/NeoVintageous/NeoVintageous/tags)

Vintageous-fork, a Vim emulation layer for Sublime Text.

## OVERVIEW

* [Installation](#installation)
* [Usage](#usage)
* [Configuration](#configuration)
* [Contributing](#contributing)
* [Changelog](#changelog)
* [Credits](#credits)
* [License](#license)

## INSTALLATION

### Package Control installation

The preferred method of installation is [Package Control](https://packagecontrol.io/browse/authors/NeoVintageous).

### Manual installation

1. Close Sublime Text.
2. Download or clone this repository to a directory named **`NeoVintageous`** in the Sublime Text Packages directory for your platform:
    * Linux: `git clone https://github.com/NeoVintageous/NeoVintageous.git ~/.config/sublime-text-3/Packages/NeoVintageous`
    * OS X: `git clone https://github.com/NeoVintageous/NeoVintageous.git ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/NeoVintageous`
    * Windows: `git clone https://github.com/NeoVintageous/NeoVintageous.git %APPDATA%\Sublime/ Text/ 3/Packages/NeoVintageous`
3. Done!

## USAGE

See [Neovim user documentation](https://neovim.io/doc/user). Below are notes about some of the features.

For a toggle feature see the [ToggleNeoVintageous](https://github.com/NeoVintageous/ToggleNeoVintageous) plugin.

Command | Description | Documentation | Dependencies | Notes
------- | ----------- | ------------- | ------------ | -----
ctrl-w, H | Move the current window to be at the very top | [Neovim doc](https://neovim.io/doc/user/windows.html#CTRL-W_H) | | Only works in 2 col/row layouts
ctrl-w, J | Move the current window to be at the very bottom | [Neovim doc](https://neovim.io/doc/user/windows.html#CTRL-W_J) | | Only works in 2 col/row layouts
ctrl-w, K | Move the current view to be at the far left | [Neovim doc](https://neovim.io/doc/user/windows.html#CTRL-W_K) | | Only works in 2 col/row layouts
ctrl-w, L | Move the current window to be at the far right | [Neovim doc](https://neovim.io/doc/user/windows.html#CTRL-W_L) | | Only works in 2 col/row layouts
ctrl-w, s | Split current window in two | [Neovim doc](https://neovim.io/doc/user/windows.html#CTRL-W_s) | [Origami](https://github.com/SublimeText/Origami)
ctrl-w, v | Split current window in two (vertically) | [Neovim doc](https://neovim.io/doc/user/windows.html#CTRL-W_v) | [Origami](https://github.com/SublimeText/Origami)

### Command Palette

Command | Description
------- | -----------
NeoVintageous: Exit from Command Mode |
NeoVintageous: Open Changelog |
NeoVintageous: Open My .vintageousrc |
NeoVintageous: Open Readme |
NeoVintageous: Reload My .vintageousrc |
NeoVintageous: Reset |
NeoVintageous: Toggle Use Ctrl Keys |

## CONFIGURATION

Key | Description | Type | Default
----|-------------|------|--------
`vintageous_autoindent` | Enable auto indentation. | `boolean` | `true`
`vintageous_enable_cmdline_mode` | Enable ':' and ex commands. | `boolean` | `true`
`vintageous_enable_surround` | Enable surround.vim plugin. Provides mappings to easily delete, change and add such surroundings in pairs e.g. "cs", "ds", and "ys" actions. | `boolean` | `true`
`vintageous_hlsearch` | Highlight searches in '/', '?', etc. | `boolean` | `true`
`vintageous_ignorecase` | Ignore case in '/', '?', '*', and '#'. | `boolean` | `true`
`vintageous_incsearch` | Apply search patterns incrementally as they are typed. | `boolean` | `true`
`vintageous_magic` | Use regular expressions in '/' and '?' otherwise uses smart case, interpret pattern literally, and ignore case. | `boolean` | `true`
`vintageous_reset_mode_when_switching_tabs` | Reset to normal mode when a tab is activated. | `boolean` | `true`
`vintageous_surround_spaces` | Enable surround.vim plugin pair opener spaces, otherwise the pair closes have spaces i.e. if true then `ysw(` and `ysw)` -&gt; `( things )` and `(things)`, otherwise if false then `ysw(` and `ysw)` -&gt; `(things) and `( things )` | `boolean` | `false`
`vintageous_use_ctrl_keys` | Enable key bindings prefaced by the CTRL modifier. | `boolean` | `false`
`vintageous_use_sys_clipboard` | Propagate copy actions to the system clipboard. | `boolean` | `false`
`vintageous_visualbell` | Enable visual bell. | `boolean` | `true`
`vintageous_visualyank` | Enable visual bell when yanking. | `boolean` | `true`

### Use ctrl keys

To enable ctrl modifier keys set it globally: `Preferences > Settings`

```json
{
    "vintageous_use_ctrl_keys": true
}
```

Or set it per-project: `Project > Edit Project`

```json
{
    "settings": {
        "vintageous_use_ctrl_keys": true
    }
}
```

### Better search highlighting support

Color schemes can [support better search highlighting](https://github.com/NeoVintageous/NeoVintageous/issues/63#issuecomment-301948594) via the following scopes:

     <dict>
        <key>scope</key>
        <string>string.search</string>
        <key>settings</key>
        <dict>
            <key>foreground</key>
            <string>#000000</string>
            <key>background</key>
            <string>#C4BE89</string>
        </dict>
    </dict>
    <dict>
        <key>scope</key>
        <string>string.search.occurrence</string>
        <key>settings</key>
        <dict>
            <key>foreground</key>
            <string>#000000</string>
            <key>background</key>
            <string>#FFE792</string>
        </dict>
    </dict>

## CONTRIBUTING

Your issue reports and pull requests are welcome.

### Tests

The [UnitTesting](https://github.com/randy3k/UnitTesting) package is used to run the tests. Install it, open the Command Palette, type "UnitTesting", press Enter and input "NeoVintageous" as the package to test.

### Debugging

Debug messages are disabled by default. To enable them set the environment variable `SUBLIME_NEOVINTAGEOUS_DEBUG` to a non-blank value. The debug message log is located at `Packages/User/NeoVintageous.log`. See [Set a Sublime Text environment variable](https://github.com/gerardroche/sublime-phpunit#debugging) for a step by step guide on how to set an environment variable for Sublime Text.

### Reverting to a freshly installed state

* [Reverting to a freshly installed state](https://www.sublimetext.com/docs/3/revert.html) (Sublime Text Documentation)
* [Reverting Sublime Text to its default configuration](http://docs.sublimetext.info/en/latest/extensibility/packages.html?highlight=fresh#reverting-sublime-text-to-its-default-configuration) (Unofficial Sublime Text Documentation)

For Linux and OSX [this script](https://github.com/gerardroche/dotfiles/src/bin/sublime-clean) can be used to clean caches, indexes, workspaces, sessions, etc. Check back soon for a Windows compatible script.

*Note: cleaning and reverting are two different tasks. Reverting will remove installed packages and configurations, cleaning will only remove files generated by Sublime Text at runtime like caches, indexes, workspaces, sessions, etc.*

## CHANGELOG

See [CHANGELOG.md](CHANGELOG.md).

## CREDITS

This project is a fork of [Vintageous](https://github.com/guillermooo/Vintageous).

## LICENSE

Released under the [MIT License](LICENSE).
