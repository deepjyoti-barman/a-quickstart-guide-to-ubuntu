# A Quickstart Guide to Ubuntu

## Table of Contents

- [A Quickstart Guide to Ubuntu](#a-quickstart-guide-to-ubuntu)
  - [Table of Contents](#table-of-contents)
  - [Set Up Ubuntu, Resolve Issues and Tweaks](#set-up-ubuntu-resolve-issues-and-tweaks)
    - [Install the Perfect Terminal Font: MesloLGS NF](#install-the-perfect-terminal-font-meslolgs-nf)
    - [Install the Perfect Editor Font: Cascadia Mono](#install-the-perfect-editor-font-cascadia-mono)
    - [Ubuntu Text Sharpness Fix](#ubuntu-text-sharpness-fix)
    - [Update Custom DNS Settings](#update-custom-dns-settings)
    - [GNOME Online Accounts](#gnome-online-accounts)
    - [GNOME Multitasking Settings](#gnome-multitasking-settings)
    - [Resolve: `chpwd_recent_filehandler` Issue in Zsh](#resolve-chpwd_recent_filehandler-issue-in-zsh)
    - [Resolve: zsh-autocomplete Startup Error](#resolve-zsh-autocomplete-startup-error)
  - [Ubuntu Keyboard Shortcuts](#ubuntu-keyboard-shortcuts)
  - [Applications](#applications)
    - [1. Google Chrome](#1-google-chrome)
    - [2. Visual Studio Code](#2-visual-studio-code)
    - [3. Brave](#3-brave)
    - [4. Sublime Text](#4-sublime-text)
    - [5. Zoom](#5-zoom)
    - [6. Kindle PWA](#6-kindle-pwa)
    - [7. Microsoft Teams PWA](#7-microsoft-teams-pwa)
    - [8. ChatGPT](#8-chatgpt)
    - [9. JetBrains Toolkit](#9-jetbrains-toolbox)
    - [10. JetBrains IDEs](#10-jetbrains-ides)
      - [Install WebStorm](#install-webstorm)
      - [Install IntelliJ IDEA](#install-intellij-idea)
      - [Install PyCharm](#install-pycharm)
      - [Install PHPStorm](#install-phpstorm)
      - [Install Android Studio](#install-android-studio)
    - [11. Android Studio Configuration](#11-android-studio-configuration)
  - [Zsh Environment & Shell Configuration](#zsh-environment--shell-configuration)
    - [File: `~/.zshenv`](#file-zshenv)
    - [File: `~/.zshrc`](#file-zshrc)
    - [File: `~/aliases.zsh`](#file-aliaseszsh)
  - [Tools and Utilities](#tools-and-utilities)
    - [git](#git-git)
    - [bat](#bat-batcat)
    - [tree](#tree-tree)
    - [zip](#zip-zip)
    - [unzip](#unzip-unzip)
    - [curl](#curl-curl)
    - [Ghostty Terminal](#ghostty-terminal-ghostty)
    - [micro](#micro-micro)
    - [wl-clipboard](#wl-clipboard-wl-copy-wl-paste)
    - [zsh](#zsh-zsh)
    - [oh-my-zsh](#oh-my-zsh-omz)
    - [Powerlevel10k and Additional oh-my-zsh Plugins](#powerlevel10k-and-additional-oh-my-zsh-plugins-p10k)
    - [SDKMan](#sdkman-sdk)
    - [Java](#java-java)
    - [Gradle](#gradle-gradle)
    - [Maven](#maven-mvn)
    - [JMeter](#jmeter-jmeter)
    - [AQL](#aql-aql)
    - [NVM](#nvm-nvm)
    - [MariaDB Client](#mariadb-client-mysql)
    - [pyenv](#pyenv-pyenv)
    - [Docker Desktop](#docker-desktop-docker)
    - [JetBrains Toolbox](#jetbrains-toolbox-jetbrains-toolbox)
    - [GitHub Desktop](#github-desktop-github-desktop)
    - [Allure](#allure-allure)
    - [Vim](#vim-vim)
    - [Zed](#zed-zed)
    - [uv](#uv-uv)
    - [Ollama](#ollama-ollama)
    - [DBeaver Community](#dbeaver-community-dbeaver)
    - [Studio 3T Community Edition](#studio-3t-community-edition-studio-3t)
    - [Okular PDF Reader](#okular-pdf-reader-okular)
    - [Golang](#golang-go)
    - [Timeshift](#timeshift-timeshift)
    - [GNOME Tweaks](#gnome-tweaks-gnome-tweaks)
    - [Extension Manager](#extension-manager-gnome-shell-extension-manager)
    - [Software Properties GTK](#software-properties-gtk-software-properties-gtk)
    - [Media Codecs](#media-codecs-ubuntu-restricted-extras)
    - [VLC](#vlc-vlc)
    - [Firewall](#firewall-ufw-gufw)
    - [TLP](#tlp-tlp)
    - [Thermald](#thermald-thermald)
    - [Synaptic](#synaptic-synaptic)
    - [Preload](#preload-preload)
    - [Papirus Icon Theme](#papirus-icon-theme)
    - [BleachBit](#bleachbit-bleachbit)
    - [XAMPP](#xampp-lampp)
    - [net-tools](#net-tools-net-tools)

## Set Up Ubuntu, Resolve Issues and Tweaks

### Install the Perfect Terminal Font: MesloLGS NF

#### MesloLGS NF: Overview

MesloLGS NF is a Nerd Font commonly used with Powerlevel10k. It includes the special icons needed by rich terminal prompts.

#### MesloLGS NF: Why it's useful

- Makes Powerlevel10k icons display correctly.
- Prevents missing-symbol boxes in your terminal prompt.
- Works well with Ghostty and other modern terminal emulators.

#### MesloLGS NF: Installation and Verification Commands

Create your user font directory:

```sh
mkdir -p ~/.local/share/fonts
```

Download the MesloLGS NF font files:

```sh
cd ~/.local/share/fonts

curl -LO "https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf"
curl -LO "https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf"
curl -LO "https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf"
curl -LO "https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf"
```

Refresh the font cache:

```sh
fc-cache -fv
```

Verify the installation:

```sh
fc-list | grep -i "MesloLGS"
fc-match "MesloLGS NF"
```

#### MesloLGS NF: Simple Examples

```sh
# Checks whether MesloLGS is installed
fc-list | grep -i "MesloLGS"

# Shows the font file that matches this font name
fc-match "MesloLGS NF"

# Refreshes the font cache after installing fonts
fc-cache -fv
```

#### MesloLGS NF: Important Concepts

- `Nerd Font`: A font patched with extra icons for terminal prompts.
- `User font folder`: `~/.local/share/fonts` installs fonts only for your user account.
- `Terminal font setting`: After installation, set your terminal font to `MesloLGS NF` in the terminal configuration.

---

### Install the Perfect Editor Font: Cascadia Mono

#### Cascadia Mono: Overview

Cascadia Mono is a monospaced font useful for terminals and code editors.

#### Cascadia Mono: Why it's useful

- Makes code and terminal text easier to read.
- A good choice for editors and terminal emulators.
- Available directly from Ubuntu packages.

#### Cascadia Mono: Installation and Verification Commands

```sh
sudo apt update
sudo apt install fonts-cascadia-code
```

Verify the installation:

```sh
fc-list | grep -i "Cascadia Mono"
fc-match "Cascadia Mono"
```

#### Cascadia Mono: Simple Examples

```sh
# Checks whether Cascadia Mono is installed
fc-list | grep -i "Cascadia Mono"

# Shows the matching font file
fc-match "Cascadia Mono"

# Refreshes the font cache if needed
fc-cache -fv
```

#### Cascadia Mono: Important Concepts

- `Monospace font`: Every character has the same width, which helps code align properly.
- `Font cache`: Linux uses a cache to find installed fonts.
- `Editor setting`: Install the font, then select it in your terminal or editor settings.

---

### Ubuntu Text Sharpness Fix

#### Ubuntu Text Sharpness Fix: Overview

This GNOME setting changes font hinting to make text appear sharper on some displays.

#### Ubuntu Text Sharpness Fix: Why it's useful

- Can improve text clarity on 1080p laptop screens.
- Helps fonts align more strongly to physical pixels.
- Useful if Ubuntu desktop text looks slightly soft or blurry.

#### Ubuntu Text Sharpness Fix: Installation and Verification Commands

```sh
gsettings set org.gnome.desktop.interface font-hinting 'full'
```

Log out and log back in to apply the change fully.

Verify the setting:

```sh
gsettings get org.gnome.desktop.interface font-hinting
```

#### Ubuntu Text Sharpness Fix: Simple Examples

```sh
# Shows the current font hinting setting
gsettings get org.gnome.desktop.interface font-hinting

# Sets font hinting to full
gsettings set org.gnome.desktop.interface font-hinting 'full'

# Restores the common lighter hinting style
gsettings set org.gnome.desktop.interface font-hinting 'slight'
```

#### Ubuntu Text Sharpness Fix: Important Concepts

- `Font hinting`: Controls how font shapes align to physical pixels.
- `slight`: Preserves font shapes more closely, but can look softer.
- `full`: Aligns strokes more aggressively to pixels, which can look sharper.
- `Logout/login`: Some desktop font-rendering changes may require a new session.

---

### Update Custom DNS Settings

#### Custom DNS: Overview

Custom DNS lets you choose which DNS servers your system uses to resolve domain names.

#### Custom DNS: Why it's useful

- Can improve reliability if your default DNS is slow or broken.
- Useful for using public DNS providers such as Google DNS.
- Helps troubleshoot network name-resolution issues.

#### Custom DNS: Installation and Verification Commands

Open the network settings for your currently connected Wi-Fi network:

```text
Settings → Wi-Fi → Click the settings icon for the currently connected network
```

Configure IPv4 DNS:

```text
1. Open the IPv4 tab.
2. Turn off Automatic DNS.
3. Enter: 8.8.8.8, 8.8.4.4
```

Configure IPv6 DNS:

```text
1. Open the IPv6 tab.
2. Turn off Automatic DNS.
3. Enter: 2001:4860:4860::8888, 2001:4860:4860::8844
```

#### Custom DNS: Simple Examples

```sh
# Shows the DNS settings currently used by the system
resolvectl status

# Tests DNS resolution for a domain
nslookup google.com

# Checks whether a domain resolves and responds
ping google.com
```

#### Custom DNS: Important Concepts

- `DNS`: Converts names such as `google.com` into IP addresses.
- `IPv4 DNS`: Uses addresses such as `8.8.8.8`.
- `IPv6 DNS`: Uses addresses such as `2001:4860:4860::8888`.
- `Automatic DNS`: Provided by your router or network unless disabled.

---

### GNOME Online Accounts

#### GNOME Online Accounts: Overview

GNOME Online Accounts connects accounts such as Google and Microsoft 365 to Ubuntu desktop applications.

#### GNOME Online Accounts: Why it's useful

- Syncs calendar, contacts, and email integration into GNOME applications.
- Reduces repeated sign-ins across desktop applications.
- Useful after setting up a fresh Ubuntu desktop.

#### GNOME Online Accounts: Installation and Verification Commands

Open Online Accounts from:

```text
Settings → Online Accounts
```

Connect your Google, Microsoft 365, or other supported accounts.

Account integration:

```text
Google Calendar feeds into GNOME Calendar.
Google Contacts syncs into GNOME Contacts.
Email becomes available to compatible apps without repeated sign-ins.
```

#### GNOME Online Accounts: Simple Examples

```sh
# Opens Online Accounts settings, if available
gnome-control-center online-accounts

# Opens GNOME Calendar, if installed
gnome-calendar

# Opens GNOME Contacts, if installed
gnome-contacts
```

#### GNOME Online Accounts: Important Concepts

- `Account provider`: Google, Microsoft 365, and other supported services.
- `Desktop integration`: Account data becomes available to GNOME applications.
- `Sync`: Calendar and contact data can update automatically.

---

### GNOME Multitasking Settings

#### GNOME Multitasking Settings: Overview

GNOME Multitasking settings control workspace and application-switching behavior.

#### GNOME Multitasking Settings: Why it's useful

- Makes workspace behavior less distracting.
- Helps application switching focus on the current workspace.
- Useful if you organize work by workspace.

#### GNOME Multitasking Settings: Installation and Verification Commands

Open Multitasking settings:

```text
Settings → Multitasking
```

Recommended settings:

```text
1. Enable Hot Corner.
2. Under App Switching, select:
   "Include apps from the current workspace only"
```

#### GNOME Multitasking Settings: Simple Examples

```sh
# Opens multitasking settings, if supported
gnome-control-center multitasking

# Checks whether app switching is limited to the current workspace
gsettings get org.gnome.shell.app-switcher current-workspace-only

# Limits app switching to the current workspace
gsettings set org.gnome.shell.app-switcher current-workspace-only true
```

#### GNOME Multitasking Settings: Essential Keystrokes

GNOME workspace navigation is interactive:

| Key                 | Action                         |
| ------------------- | ------------------------------ |
| `Super`             | Open overview                  |
| `Alt + Tab`         | Switch applications            |
| `Super + Page Up`   | Move to the previous workspace |
| `Super + Page Down` | Move to the next workspace     |

#### GNOME Multitasking Settings: Important Concepts

- `Workspace`: A virtual desktop for grouping windows.
- `Hot Corner`: Moving the pointer to a corner opens the overview.
- `Current workspace only`: Makes application switching less cluttered.

---

### Resolve: `chpwd_recent_filehandler` Issue in Zsh

#### chpwd_recent_filehandler: Root Cause

When opening a Zsh terminal or changing directories, Zsh may display an error such as:

```text
chpwd_recent_filehandler:29: no such file or directory: /Users/<username>/.local/share/zsh/chpwd-recent-dirs
```

The `chpwd_recent_filehandler` function, commonly enabled by a Zsh configuration or plugin such as `zsh-autocomplete`, maintains a history of recently visited directories. It runs whenever the working directory changes.

Its history file is expected at:

```text
~/.local/share/zsh/chpwd-recent-dirs
```

The error occurs because either the `~/.local/share/zsh` directory or the `chpwd-recent-dirs` file does not exist. This is common after copying a Zsh configuration to a new machine, installing a plugin on a fresh system, or deleting the file manually.

#### chpwd_recent_filehandler: Actual Fix

Create the directory and empty history file that the Zsh hook expects, then restart Zsh:

```sh
mkdir -p ~/.local/share/zsh
touch ~/.local/share/zsh/chpwd-recent-dirs
exec zsh
```

- `mkdir -p ~/.local/share/zsh` creates the required directory structure if it does not already exist.
- `touch ~/.local/share/zsh/chpwd-recent-dirs` creates the missing recent-directory history file without overwriting an existing one.
- `exec zsh` starts a fresh Zsh session so the configuration and plugins reload.

After restarting Zsh, verify the fix by changing directories:

```sh
cd /tmp
cd ~
```

Zsh should now maintain recent-directory history without showing the `chpwd_recent_filehandler` error.

---

### Resolve: zsh-autocomplete Startup Error

#### zsh-autocomplete Startup Error: Issue Details

After installing `zsh-autocomplete`, every new terminal session showed errors like:

```zsh
autocomplete:_main_complete:old:138: command not found: _autocomplete__history_lines
autocomplete:_main_complete:new:post:3: command not found: _autocomplete__unambiguous
```

Running this manually fixed the current shell:

```zsh
exec zsh
```

But the same error returned whenever a brand-new terminal window was opened.

#### zsh-autocomplete Startup Error: Root Cause

`zsh-autocomplete` has internal helper completion functions, including:

```zsh
_autocomplete__history_lines
_autocomplete__unambiguous
```

Those helper files live inside:

```zsh
~/.oh-my-zsh/custom/plugins/zsh-autocomplete/Completions
```

Oh My Zsh runs `compinit` while loading its main configuration. `compinit` initializes Zsh's command-completion system and creates a completion dump file to cache completion definitions for faster shell startup.

The dump file is usually stored in the user's home directory and has a name similar to:

```zsh
~/.zcompdump-<hostname>-<zsh-version>
```

The issue was that the `zsh-autocomplete/Completions` directory was not visible in `fpath` before Oh My Zsh ran `compinit`.

So zsh-autocomplete itself loaded, but its helper completion functions were missing from the completion lookup path. That caused the `command not found` errors.

`exec zsh` temporarily fixed it because the shell restarted after some state had already been refreshed, but it did not fix the startup order permanently.

#### zsh-autocomplete Startup Error: Resolution

The fix is to add the plugin's (`zsh-autocomplete`) nested `Completions` directory to Zsh's function search path (`fpath`) before Oh My Zsh is loaded.

This ensures that `compinit`, which Oh My Zsh runs during startup, can find and register the completion functions provided by `zsh-autocomplete`.

**Step 1:** Add the following configuration near the top of `~/.zshrc`, immediately after defining `ZSH` variable:

```zsh
export ZSH="$HOME/.oh-my-zsh"
ZSH_CUSTOM="${ZSH_CUSTOM:-$ZSH/custom}"

# zsh-autocomplete ships helper completions in a nested Completions directory.
# Oh My Zsh runs compinit before it sources plugin scripts, so expose these
# helpers to fpath before OMZ initializes completion.
if [[ -d "$ZSH_CUSTOM/plugins/zsh-autocomplete/Completions" ]]; then
  fpath=("$ZSH_CUSTOM/plugins/zsh-autocomplete/Completions" $fpath)
fi
```

**Step 2:** `zsh-autocomplete` should not be listed inside the Oh My Zsh `plugins=(...)` array in this setup, because it will loaded separately with an explicit `source` command.

The plugins section should look like this:

```zsh
plugins=(
  docker
  docker-compose
  extract
  git
  sublime
  web-search
  z
  zsh-autosuggestions
  fast-syntax-highlighting
)
```

Notice that `zsh-autocomplete` is intentionally not included there. This matters because loading `zsh-autocomplete` through the Oh My Zsh `plugins=(...)` array does not expose its nested helper directory early enough:

```zsh
~/.oh-my-zsh/custom/plugins/zsh-autocomplete/Completions
```

**Step 3:** Load the `zsh-autocomplete` manually after Oh My Zsh:

```zsh
source "$ZSH/oh-my-zsh.sh"

# Load zsh-autocomplete manually, after OMZ
source "$ZSH_CUSTOM/plugins/zsh-autocomplete/zsh-autocomplete.plugin.zsh"
```

**Step 4:** Clear stale completion caches or dump files so that zsh could rebuild completion metadata with the corrected `fpath`:

```zsh
rm ~/.zcompdump(N) ~/.zcompdump-*(N) ~/.zcompdump*.zwc(N)
```

This uses zsh's `(N)` glob qualifier, which means "expand to nothing if there are no matches." That makes the command safe to run even if some cache files do not exist.

**Step 5:** Restart the shell:

```zsh
exec zsh
```

#### zsh-autocomplete Startup Error: Short Summary of the Fix

The problem was not that `zsh-autocomplete` was missing. The problem was startup order.

Oh My Zsh initialized completions before plugins's (`zsh-autocomplete`) helper completion directory was available. Adding that directory to `fpath` before Oh My Zsh runs `compinit`, then clearing the stale completion cache, fixed the issue permanently.

---

## Ubuntu Keyboard Shortcuts

### Ubuntu Keyboard Shortcuts: Overview

These GNOME keyboard shortcuts help you open applications and move windows quickly.

### Ubuntu Keyboard Shortcuts: Why it's useful

- Speeds up everyday desktop navigation.
- Makes window management easier.
- Useful when working across many applications and terminals.

### Ubuntu Keyboard Shortcuts: Installation and Verification Commands

No installation is needed. These shortcuts are built into Ubuntu GNOME.

### Ubuntu Keyboard Shortcuts: Simple Examples

```text
Super + Number
```

Opens the application in the dock at that position.

```text
Super + Super
```

Opens the application launcher grid.

```text
Super + Arrow keys
```

Moves the current window left, right, or maximizes it, depending on the direction and current state.

### Ubuntu Keyboard Shortcuts: Essential Keystrokes

| Key              | Action                                     |
| ---------------- | ------------------------------------------ |
| `Super + Number` | Open the dock application in that position |
| `Super + Super`  | Open the application launcher grid         |
| `Super + Left`   | Tile the current window left               |
| `Super + Right`  | Tile the current window right              |
| `Super + Up`     | Maximize the current window                |
| `Super + Down`   | Restore or minimize the current window     |

### Ubuntu Keyboard Shortcuts: Important Concepts

- `Super key`: Usually the Windows key or Command-like key on the keyboard.
- `Dock position`: Numbers map to application icons pinned in the dock.
- `Window tiling`: Quickly places windows without dragging.

## Applications

### 1. Google Chrome

#### Commands to Install

```bash
# Install
cd ~/Downloads
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo apt install ./google-chrome-stable_current_amd64.deb

# Verify
google-chrome --version

# Open the app
google-chrome
```

#### Why Use `apt` to Install Packages on Ubuntu?

1. **Dependency Management**
   - Automatically finds and installs required dependencies.

2. **System Integration**
   - Installs software properly into Ubuntu's package system.

3. **Easy Updates**
   - Software can receive updates through the normal `apt` update process when a repository is configured.

4. **Easy Removal**
   - Packages can be cleanly removed using:

     ```bash
     sudo apt remove <package-name>
     ```

5. **Better Than `dpkg` Alone**
   - `dpkg` installs `.deb` files but does not automatically resolve dependencies.
   - `apt` can install the `.deb` and handle dependencies:

     ```bash
     sudo apt install ./package.deb
     ```

### 2. Visual Studio Code

#### Installation Process

1. Open **App Center**.
2. Search for **Visual Studio Code**.
3. Select the **code** by Visual Studio Code.
4. Click `Install`.
5. Enter your Ubuntu password if prompted.
6. Launch **Visual Studio Code** from Applications.

#### Necessary Extensions

- \[Deprecated\] Browser Preview
- Auto Import
- Auto Rename Tag
- Babel JavaScript
- Better Comments
- Black Formatter
- C/C++ (Optional)
- C/C++ Compile Run (Optional)
- chai theme
- ChatGPT - Work with Code on macOS
- Claude Code for VSCode
- Code Runner
- Code Spell Checker
- CodeSnap
- Color Highlight
- Container Tools
- CSS Peek
- Debugger for Java
- Docker
- DotENV
- EditorConfig for VS Code
- Error Lens
- ES7+ React/Redux/React-Native snippets
- ESLint
- Extension Pack for Java
- Feature Syntax Highlight and Snippets (Cucumber/Gherkin)
- Git Blame
- Git Graph
- Git History
- GitHub Copilot
- GitHub Copilot Chat
- Gradle for Java
- Go (Optional)
- Image Preview
- Import Cost
- indent-rainbow
- JavaScript (ES6) code snippets
- Language Support for Java(TM) by Red Hat
- Live Sass Compiler (Optional)
- Live Server
- Markdown Preview Github Styling
- markdownlint
- Material Icon Theme
- Maven for Java
- One Dark Darker
- One Dark Pro Monokai Darker Theme
- Output Calculator
- PHP
- Path Intellisense
- Peacock
- Playwright Tests for VSCode
- Postman (Optional)
- Prettier - Code formatter
- Project Manager
- Project Manager for Java
- Pylance
- Python
- Python Debugger
- Quokka.js
- Sass (Optional)
- shell-format
- Spring Boot Extension Pack
- Tailwind CSS IntelliSense
- Test Runner for Java
- Thunder Client (Optional)
- Todo Highlight
- Todo Tree
- Turbo Console Log
- TSLint (Optional)
- vscode-pdf
- vscode-pets
- vscode-random

#### VS Code Settings

Click on the `Manage` (Screw) icon → `Settings` (Shortcut: `Command + ,`) → From the top right corner click on `Open Settings (JSON)`

```json
{
  // Configuration for extension "Code Runner"
  // "c-cpp-compile-run.c-flags": "-Wall -Wextra -O0 -std=c18",
  // "c-cpp-compile-run.cpp-flags": "-Wall -Wextra -O0 -std=c++20",
  "black-formatter.args": [
    "--line-length",
    "100",
    "--skip-string-normalization"
  ],

  "chat.tips.enabled": false,
  "chat.viewSessions.orientation": "stacked",

  "code-runner.clearPreviousOutput": true,
  "code-runner.executorMap": {
    "python": "python3 -u",
    "typescript": "npx tsx"
  },
  "code-runner.ignoreSelection": true,
  "code-runner.runInTerminal": true,
  "code-runner.saveFileBeforeRun": true,
  "code-runner.showExecutionMessage": true,

  "color-highlight.markerType": "dot-after",

  "cSpell.ignoreWords": ["deepjyoti", "pytest"],

  "diffEditor.ignoreTrimWhitespace": false,

  "editor.fontSize": 18,
  "editor.suggestSelection": "first",
  "editor.rulers": [100],
  "editor.wordWrap": "on",
  "editor.minimap.scale": 2,
  "editor.minimap.autohide": "mouseover",
  "editor.minimap.renderCharacters": false,
  "editor.fontFamily": "Cascadia Mono, Monolisa, Menlo, Monaco, 'Courier New', monospace, Consolas",
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "editor.bracketPairColorization.enabled": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.inlineSuggest.showToolbar": "onHover",
  "editor.inlineSuggest.suppressSuggestions": false,
  "editor.quickSuggestions": {
    "other": "inline",
    "comments": "inline",
    "strings": "inline"
  },
  "[ignore]": {
    "editor.defaultFormatter": "foxundermoon.shell-format"
  },

  "explorer.compactFolders": false,
  "explorer.confirmDelete": false,
  "explorer.confirmDragAndDrop": false,

  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 4000,

  "github.copilot.enable": {
    "*": false,
    "plaintext": false,
    "markdown": false,
    "scminput": false
  },

  "java.project.importOnFirstTimeStartup": "disabled",

  "liveServer.settings.donotShowInfoMsg": true,
  "liveServer.settings.port": 5500,

  "peacock.favoriteColors": [
    {
      "name": "Angular Red",
      "value": "#dd0531"
    },
    {
      "name": "Azure Blue",
      "value": "#007fff"
    },
    {
      "name": "JavaScript Yellow",
      "value": "#f9e64f"
    },
    {
      "name": "Mandalorian Blue",
      "value": "#1857a4"
    },
    {
      "name": "Node Green",
      "value": "#215732"
    },
    {
      "name": "React Blue",
      "value": "#61dafb"
    },
    {
      "name": "Something Different",
      "value": "#832561"
    },
    {
      "name": "Svelte Orange",
      "value": "#ff3d00"
    },
    {
      "name": "Vue Green",
      "value": "#42b883"
    },
    {
      "name": "Bluish White",
      "value": "#b6d6f7"
    }
  ],

  "playwright.reuseBrowser": false,

  // "prettier.singleQuote": false,
  // "prettier.tabWidth": 4,

  "security.workspace.trust.banner": "never",
  "security.workspace.trust.emptyWindow": true,
  "security.workspace.trust.enabled": false,
  "security.workspace.trust.startupPrompt": "never",
  "security.workspace.trust.untrustedFiles": "open",

  "terminal.integrated.fontFamily": "MesloLGS NF, Monaco",
  "terminal.integrated.fontSize": 14,

  "todo-tree.ripgrep.ripgrep": "/usr/bin/rg",

  "turboConsoleLog.addSemicolonInTheEnd": true,
  "turboConsoleLog.logMessagePrefix": " ",
  "turboConsoleLog.quote": "'",
  "turboConsoleLog.delimiterInsideMessage": " ",

  "workbench.colorTheme": "One Dark Darker",
  "workbench.iconTheme": "material-icon-theme",
  "workbench.startupEditor": "none",

  "window.zoomLevel": 0.5,

  // Configuration for extension "Language Support for Java(TM) by Red Hat"
  "redhat.telemetry.enabled": true,
  "[java]": {
    "editor.defaultFormatter": "redhat.java"
  },

  // Configuration for extension "Black Formatter"
  "[python]": {
    "editor.defaultFormatter": "ms-python.black-formatter"
  },

  // Configuration for extension "Prettier - Code formatter" for JavaScript
  "[javascript]": {
    "editor.tabSize": 2,
    "editor.insertSpaces": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "prettier.singleQuote": true,
    "prettier.tabWidth": 2,
    "prettier.useTabs": false,
    "prettier.printWidth": 80,
    "prettier.semi": true
  },

  // Configuration for extension "Prettier - Code formatter" for React
  "[javascriptreact]": {
    "editor.tabSize": 2,
    "editor.insertSpaces": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "prettier.singleQuote": true,
    "prettier.tabWidth": 2,
    "prettier.useTabs": false,
    "prettier.printWidth": 80,
    "prettier.semi": true
  },

  // Configuration for extension "Prettier - Code formatter" for JSON
  "[json]": {
    "editor.tabSize": 2,
    "editor.insertSpaces": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "prettier.singleQuote": false,
    "prettier.tabWidth": 2,
    "prettier.useTabs": false,
    "prettier.printWidth": 80,
    "prettier.semi": true
  }
}
```

#### Configure Inline Suggestions Shortcut in VS Code

By default, accepting AI inline suggestions may require a different key combination. You can create a custom shortcut for quicker access.

**Steps**

1. Open the Command Palette: `Ctrl + Shift + P`
2. Search for and select: `Preferences: Open Keyboard Shortcuts`
3. In the Keyboard Shortcuts search box, search for: `Trigger Inline Suggestion`
4. Click the Edit (pencil) icon or `+` icon next to the command.
5. Press the desired key combination: `Alt + I`
6. Press `Enter` to save the shortcut.
7. You can now press `Alt + I` to trigger inline AI suggestions directly from the editor.

> Note: If `Alt + I` is already assigned to another command, VS Code will display a warning and allow you to override the existing shortcut.

### 3. Brave

1. Open **App Center**.
2. Search for **Brave**.
3. Select **Brave** by Brave Software.
4. Click `Install`.
5. Enter your password if prompted.
6. Launch **Brave** from Applications.

### 4. Sublime Text

1. Open **App Center**.
2. Search for **Sublime Text**.
3. Select **Sublime Text** by Snapcrafters.
4. Click `Install`.
5. Enter your password if prompted.
6. Launch **Sublime Text** from Applications.

#### Sublime Text: Configuration

Open up 'Sublime Text' -> From the top on the menu bar click on `Preferences` tab -> `Settings` (Shortcut: `Command + ,`)

```json
{
  "ignored_packages": ["Vintage"],
  "color_scheme": "Packages/ayu/ayu-mirage.sublime-color-scheme",
  "theme": "ayu-mirage.sublime-theme",
  "font_size": 14,
  "spell_check": true,
  "dictionary": "Packages/Language - English/en_US.dic",
  "index_files": true
}
```

#### Sublime Text: Necessary Packages

- A File Icon
- All Autocomplete
- AutoFileName
- ayu
- BracketHighlighter
- Emmet
- Package Control
- SideBarEnhancements
- SublimeLinter
- [SublimeLinter](https://packagecontrol.io/search/SublimeLinter)
- [SublimeLinter-javac](https://packagecontrol.io/packages/SublimeLinter-javac)
- [SublimeLinter-jshint](https://packagecontrol.io/packages/SublimeLinter-jshint)
- [Sublime​Linter-tslint](https://packagecontrol.io/packages/SublimeLinter-tslint)
- [Sublime​Linter-pylint](https://packagecontrol.io/packages/SublimeLinter-pylint)
- [SublimeLinter-php](https://packagecontrol.io/packages/SublimeLinter-php)
- [Sublime​Linter-ruby](https://packagecontrol.io/packages/SublimeLinter-ruby)
- [SublimeLinter-clang](https://packagecontrol.io/packages/SublimeLinter-clang)
- [SublimeLinter-cpplint](https://packagecontrol.io/packages/SublimeLinter-cpplint)
- [Sublime​Linter-html-tidy](https://packagecontrol.io/packages/SublimeLinter-html-tidy)
- [Sublime​Linter-csslint](https://packagecontrol.io/packages/SublimeLinter-csslint)
- [SublimeLinter-json](https://packagecontrol.io/packages/SublimeLinter-json)
- [SublimeLinter-shellcheck](https://packagecontrol.io/packages/SublimeLinter-shellcheck)
- SublimeREPL
- Terminal
- Terminus
- zzz A File Icon zzz

### 5. Zoom

1. Open **App Center**.
2. Search for **Zoom**.
3. Select **zoom-client** by Oliver Grawert.
4. Click `Install`.
5. Enter your password if prompted.
6. Launch **Zoom** from Applications.

### 6. Kindle PWA

**Kindle** can be accessed directly as a Progressive Web App (PWA) through the Kindle Cloud Reader.

#### Access Kindle

1. Open **Google Chrome** or another Chromium-based browser.
2. Go to:
   [https://read.amazon.in/kindle-library](https://read.amazon.in/kindle-library)
3. Sign in with your **Amazon** account.
4. Open your **Kindle** library and start reading.

#### Install Kindle as a PWA (Optional)

For a more app-like experience in Chrome:

1. Open the **Kindle** library URL.
2. Click the `Install` icon in the address bar, if available.
3. Select `Install`.
4. **Kindle** will appear as a separate application in Ubuntu's Applications menu.

#### If the Install Icon Is Missing for Kindle

If the `Install` icon is not visible, your browser may be hiding it, may not support PWAs, or Amazon's site may not have triggered the installation prompt.

You can usually force the browser to package it as an app:

1. Click the three vertical dots (⋮) in the top-right corner.
2. Hover over `Cast, save and share`.
3. Select `Install page as app...`.
4. Confirm by clicking `Install`.
5. **Kindle** will appear as a separate application in Ubuntu's Applications menu.

> Alternative: If Install page as app... is not available, select Create shortcut... and enable Open as window.
>
> Note: A PWA does not require installing a separate Kindle application on Ubuntu.

### 7. Microsoft Teams PWA

**Microsoft Teams** can be accessed and installed as a Progressive Web App (PWA) using a supported browser such as Google Chrome.

#### Access Microsoft Teams

1. Open **Google Chrome** or another Chromium-based browser.
2. Go to:
   [https://teams.microsoft.com](https://teams.microsoft.com)
3. Sign in with your Microsoft account.
4. **Microsoft Teams** will open in the browser.

#### Install Microsoft Teams as a PWA (Optional)

For a more app-like experience in Chrome:

1. Open the **Microsoft Teams** URL.
2. Click the `Install` icon in the address bar, if available.
3. Select `Install`.
4. **Microsoft Teams** will appear as a separate application in Ubuntu's Applications menu.

#### If the Install Icon Is Missing for Microsoft Teams

If the `Install` icon is not visible, your browser may be hiding it, may not support PWAs, or the Teams website may not have triggered the installation prompt.

You can usually force the browser to package it as an app:

1. Click the three vertical dots (⋮) in the top-right corner.
2. Hover over `Cast, save and share`.
3. Select `Install page as app...`.
4. Confirm by clicking `Install`.
5. **Microsoft Teams** will appear as a separate application in Ubuntu's Applications menu.

> Alternative: If Install page as app... is not available, select Create shortcut... and enable Open as window.
>
> Note: A PWA does not require installing a separate Microsoft Teams application on Ubuntu.

### 8. ChatGPT

#### Installation Steps for ChatGPT

- Download the `ChatGPT.deb` package manually from: [https://learn.chatgpt.com/docs/linux/linux-app](https://learn.chatgpt.com/docs/linux/linux-app)

- Install the package using `apt` package manager:

  ```bash
  # Install
  cd ~/Downloads
  sudo apt install ./chatgpt_amd64.deb
  ```

- Open the app from the Applications menu.

### 9. JetBrains Toolbox

**JetBrains Toolbox** is a desktop application that allows you to install, manage, and update JetBrains IDEs such as IntelliJ IDEA, PyCharm, WebStorm, and others.

#### Installation Steps for JetBrains Toolbox

- Download the latest **JetBrains Toolbox** archive from: [https://www.jetbrains.com/toolbox-app/](https://www.jetbrains.com/toolbox-app/)

- Save the downloaded `.tar.gz` file in your `Downloads` directory.

- Install the application via the following commands:

  ```bash
  # Install dependencies
  sudo apt update

  sudo apt install -y \
    libxi6 \
    libxrender1 \
    libxtst6 \
    mesa-utils \
    libfontconfig1 \
    libgtk-3-bin \
    tar \
    dbus-user-session \
    libxcb-keysyms1

  # Create an applications directory
  mkdir -p ~/Applications

  # Extract the downloaded archive
  tar -xvf ~/Downloads/jetbrains-toolbox-3.7.2.87231.tar.gz -C ~/Applications

  # Rename the extracted directory
  mv ~/Applications/jetbrains-toolbox-3.7.2.87231 ~/Applications/jetbrains-toolbox

  # Launch the application
  cd ~/Applications/jetbrains-toolbox/bin
  ./jetbrains-toolbox
  ```

- On the first launch, **JetBrains Toolbox** initializes its application files under: `~/.local/share/JetBrains/Toolbox`

- It also creates a desktop entry under: `~/.local/share/applications`

- After the first launch, you should be able to find **JetBrains Toolbox** from Ubuntu's Applications menu.

> Note: The version number in the downloaded filename may change when a newer version of JetBrains Toolbox is released. Update the filename in the tar, mv, and related commands accordingly.

### 10. JetBrains IDEs

**JetBrains Toolbox** can be used to install and manage JetBrains IDEs such as **WebStorm**, **IntelliJ IDEA**, and **PyCharm**. It can also be used to install and manage Android Studio.

#### Open JetBrains Toolbox

1. Open the Applications menu.
2. Search for `JetBrains Toolbox`.
3. Launch the application.
4. Sign in with your JetBrains account if required.

#### Install WebStorm

1. Find `WebStorm` in **JetBrains Toolbox**.
2. Click `Install`.
3. Wait for the installation to complete.
4. Click `Launch` to open WebStorm.

#### Install IntelliJ IDEA

1. Find `IntelliJ IDEA` in **JetBrains Toolbox**.
2. Click `Install`.
3. Wait for the installation to complete.
4. Click `Launch` to open IntelliJ IDEA.

#### Install PyCharm

1. Find `PyCharm` in **JetBrains Toolbox**.
2. Click `Install`.
3. Wait for the installation to complete.
4. Click `Launch` to open PyCharm.

#### Install PHPStorm

1. Find `PHPStorm` in **JetBrains Toolbox**.
2. Click `Install`.
3. Wait for the installation to complete.
4. Click `Launch` to open PHPStorm.

#### Install Android Studio

1. Find `Android Studio` in JetBrains Toolbox.
2. Click `Install`.
3. Select the desired Android Studio version, if prompted.
4. Wait for the installation to complete.
5. Click `Launch` to open Android Studio.
6. Complete the Android Studio setup wizard.
7. Install the required Android SDK and other components when prompted.

After installation, JetBrains Toolbox creates application launchers for the installed IDEs. You can launch them directly from Ubuntu's **Applications** menu:

```text
Applications → WebStorm
Applications → IntelliJ IDEA
Applications → PyCharm
Applications → Android Studio
```

> Note: JetBrains Toolbox handles downloading, installing, and updating the IDEs and Android Studio as well. You do not need to manually download separate .tar.gz or .deb packages for these applications.

### 11. Android Studio Configuration

#### Android Studio: Overview

Android Studio is the main IDE for Android app development. It includes tools for building, running, debugging, and managing Android SDKs.

#### Android Studio: Why it's useful

- Required for most Android development workflows.
- Installs and manages Android SDK components.
- Provides `adb` for device and emulator communication.
- Works well when installed through JetBrains Toolbox.

#### Enabling Command Line Tools in Android Studio

To enable Command Line Tools in Android Studio perform the following steps:

- Open Android Studio and navigate to `Settings`
- In the `Settings` menu expand `Languages & Frameworks`
- Select `Android SDK`
- Click on `SDK Tools` tab
- Check `Android SDK Command-line Tools (latest)`
- Click on `Apply` and install the package
- Click on `OK`

**NOTE**: On the same menu under `SDK Tools` you can check `Show Package Details` and search for old APIs, build-tools that are not being used any longer and uncheck them to remove and free up some space. Also you can update some packages if update is available.

#### Environment variables configuration

- Check the current shell being used using command: `echo $SHELL`
- If the shell is: `zsh`, open the file `~/.zshenv` using `vim ~/.zshenv` (create the file if not present)
- Paste the following content:

  > File content `~/.zshenv`:

  ```bash
  skip_global_compinit=1

  # Path configuration | Package: Android Studio
  export ANDROID_HOME="$HOME/Android/Sdk"

  export PATH=$PATH:$ANDROID_HOME/emulator
  export PATH=$PATH:$ANDROID_HOME/platform-tools
  export PATH=$PATH:$ANDROID_HOME/cmdline-tools/latest/bin
  ```

#### Android Studio: Essential Keystrokes

Android Studio is interactive:

| Key                | Action                      |
| ------------------ | --------------------------- |
| `Ctrl + Shift + A` | Search actions and settings |
| `Ctrl + Alt + S`   | Open settings               |
| `Shift + F10`      | Run app                     |
| `Shift + F9`       | Debug app                   |

#### Android Studio: Important Concepts

- `Android SDK`: Tools and platform files needed for Android development.
- `ANDROID_HOME`: Environment variable that points to your SDK folder.
- `adb`: Command-line tool for devices and emulators.
- `sdkmanager`: Installs and updates SDK components.

#### Important Commands

- Print the Android Debug Bridge version:

  ```bash
  adb --version
  ```

- List connected devices:

  ```bash
  adb devices

  # With detailed information
  adb devices -l
  ```

- Print the Android SDK Manager version:

  ```bash
  sdkmanager --version
  ```

- Restart the ADB server:

  ```bash
  adb kill-server
  adb start-server
  ```

- Install an .apk:

  ```bash
  adb install app.apk

  # Reinstall an APK by keeping application data
  adb install -r app.apk
  ```

- Uninstall an application:

  ```bash
  adb uninstall <package-name>
  ```

- Start an application:

  ```bash
  adb shell monkey -p <package-name> 1
  ```

- Get the UDID of the devices connected:

  ```bash
  adb devices
  ```

- Push and pull file into android device:

  ```bash
  # Push file into Android device
  adb push ./local/file /path/on/device

  # Pull file from Android device
  adb pull /path/on/device ./local/path
  ```

- View android logs:

  ```bash
  adb logcat

  # Clear existing logs
  adb logcat -c
  ```

- Take a screenshot:

  ```bash
  adb exec-out screencap -p > screenshot.png
  ```

- Record the device screen:

  ```bash
  adb shell screenrecord /sdcard/screen.mp4

  # Press Ctrl+C to stop recording

  # Then pull the file
  adb pull /sdcard/screen.mp4
  ```

- Get the appPackage and appActivity of an app:

  ```bash
  adb shell dumpsys window | grep -E 'CurrentFocus|FocusedApp'
  ```

## Zsh Environment & Shell Configuration

### File: `~/.zshenv`

```zsh
# =========================================================
# Shell Startup
# =========================================================

# Skip global compinit initialization for faster shell startup
skip_global_compinit=1

# =========================================================
# XDG base directories
# =========================================================

# Use standard locations for user-specific config, cache, data, and state.
export XDG_CONFIG_HOME=$HOME/.config
export XDG_CACHE_HOME=$HOME/.cache
export XDG_DATA_HOME=$HOME/.local/share
export XDG_STATE_HOME=$HOME/.local/state

# =========================================================
# Pager Colorization
# =========================================================

# This shell snippet configures man to use bat (or Debian/Ubuntu's batcat) as its pager,
# giving man pages syntax highlighting and cleaner formatting.
if command -v bat >/dev/null 2>&1; then
  export MANPAGER="col -bx | bat -l man -p"
elif command -v batcat >/dev/null 2>&1; then
  export MANPAGER="col -bx | batcat -l man -p"
fi

# =========================================================
# Default Editor
# =========================================================

# Sets Neovim as the default editor for CLI tools like git, crontab etc.
# VISUAL generally indicates your preferred full-screen/interactive editor,
# while EDITOR is the more general fallback.
if command -v nvim >/dev/null 2>&1; then
  export EDITOR="nvim"
  export VISUAL="nvim"
fi

# =========================================================
# Android Studio
# =========================================================

export ANDROID_HOME=$HOME/Android/Sdk

export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/platform-tools
export PATH=$PATH:$ANDROID_HOME/cmdline-tools/latest/bin

# =========================================================
# SDKMan Default Exports
# =========================================================
# export GRADLE_HOME=$HOME/.sdkman/candidates/gradle/current
# export JAVA_HOME=$HOME/.sdkman/candidates/java/current
# export JMETER_HOME=$HOME/.sdkman/candidates/jmeter/current
# export MAVEN_HOME=$HOME/.sdkman/candidates/maven/current

# =========================================================
# XAMPP
# =========================================================

export PATH=$PATH:/opt/lampp/bin
```

### File: `~/.zshrc`

```zsh
# =========================================================
# Powerlevel10k
# =========================================================

# Enable Powerlevel10k instant prompt. Should stay close to the top of ~/.zshrc.
# Initialization code that may require console input (password prompts, [y/n]
# confirmations, etc.) must go above this block; everything else may go below.
if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi

# If you come from bash you might have to change your $PATH.
# export PATH=$HOME/bin:$HOME/.local/bin:/usr/local/bin:$PATH

# Path to your Oh My Zsh installation.
export ZSH="$HOME/.oh-my-zsh"

# =========================================================
# Oh-my-zsh Theme
# =========================================================

# Set name of the theme to load --- if set to "random", it will
# load a random theme each time Oh My Zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
ZSH_THEME="powerlevel10k/powerlevel10k"

# Set list of themes to pick from when loading at random
# Setting this variable when ZSH_THEME=random will cause zsh to load
# a theme from this variable instead of looking in $ZSH/themes/
# If set to an empty array, this variable will have no effect.
# ZSH_THEME_RANDOM_CANDIDATES=( "robbyrussell" "agnoster" )

# Uncomment the following line to use case-sensitive completion.
# CASE_SENSITIVE="true"

# Uncomment the following line to use hyphen-insensitive completion.
# Case-sensitive completion must be off. _ and - will be interchangeable.
# HYPHEN_INSENSITIVE="true"

# Uncomment one of the following lines to change the auto-update behavior
# zstyle ':omz:update' mode disabled  # disable automatic updates
# zstyle ':omz:update' mode auto      # update automatically without asking
# zstyle ':omz:update' mode reminder  # just remind me to update when it's time

# Uncomment the following line to change how often to auto-update (in days).
# zstyle ':omz:update' frequency 13

# Uncomment the following line if pasting URLs and other text is messed up.
# DISABLE_MAGIC_FUNCTIONS="true"

# Uncomment the following line to disable colors in ls.
# DISABLE_LS_COLORS="true"

# Uncomment the following line to disable auto-setting terminal title.
# DISABLE_AUTO_TITLE="true"

# Uncomment the following line to enable command auto-correction.
# ENABLE_CORRECTION="true"

# Uncomment the following line to display red dots whilst waiting for completion.
# You can also set it to another string to have that shown instead of the default red dots.
# e.g. COMPLETION_WAITING_DOTS="%F{yellow}waiting...%f"
# Caution: this setting can cause issues with multiline prompts in zsh < 5.7.1 (see #5765)
# COMPLETION_WAITING_DOTS="true"

# Uncomment the following line if you want to disable marking untracked files
# under VCS as dirty. This makes repository status check for large repositories
# much, much faster.
# DISABLE_UNTRACKED_FILES_DIRTY="true"

# Uncomment the following line if you want to change the command execution time
# stamp shown in the history command output.
# You can set one of the optional three formats:
# "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
# or set a custom format using the strftime function format specifications,
# see 'man strftime' for details.
# HIST_STAMPS="mm/dd/yyyy"

# Would you like to use another custom folder than $ZSH/custom?
# ZSH_CUSTOM=/path/to/new-custom-folder

# =========================================================
# Oh-my-zsh Plugins
# =========================================================

# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(
    docker
    docker-compose
    extract
    fast-syntax-highlighting
    git
    sublime
    web-search
    z
    zsh-autocomplete
    zsh-autosuggestions
)

source $ZSH/oh-my-zsh.sh

# User configuration

# export MANPATH="/usr/local/man:$MANPATH"

# You may need to manually set your language environment
# export LANG=en_US.UTF-8

# Preferred editor for local and remote sessions
# if [[ -n $SSH_CONNECTION ]]; then
#   export EDITOR='vim'
# else
#   export EDITOR='nvim'
# fi

# Compilation flags
# export ARCHFLAGS="-arch $(uname -m)"

# Set personal aliases, overriding those provided by Oh My Zsh libs,
# plugins, and themes. Aliases can be placed here, though Oh My Zsh
# users are encouraged to define aliases within a top-level file in
# the $ZSH_CUSTOM folder, with .zsh extension. Examples:
# - $ZSH_CUSTOM/aliases.zsh
# - $ZSH_CUSTOM/macos.zsh
# For a full list of active aliases, run `alias`.
#
# Example aliases
# alias zshconfig="mate ~/.zshrc"
# alias ohmyzsh="mate ~/.oh-my-zsh"

# =========================================================
# Config to Auto-load Tools on Startup
# =========================================================

# Plugin configuration | Package: powerlevel10k
# To customize prompt, run `p10k configure` or edit ~/.p10k.zsh.
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh

# Path configuration | Package: sdkman
# THIS MUST BE AT THE END OF THE FILE FOR SDKMAN TO WORK!!!
export SDKMAN_DIR="$HOME/.sdkman"
[[ -s "$HOME/.sdkman/bin/sdkman-init.sh" ]] && source "$HOME/.sdkman/bin/sdkman-init.sh"

# Path configuration | Package: pyenv
export PYENV_ROOT="$HOME/.pyenv"
[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init - bash)"

# Path configuration | Package: nvm
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

# Path configuration | Package: Zed
export PATH=$HOME/.local/bin:$PATH

# Path configuration | Package: deno
___MY_VMOPTIONS_SHELL_FILE="${HOME}/.jetbrains.vmoptions.sh"; if [ -f "${___MY_VMOPTIONS_SHELL_FILE}" ]; then . "${___MY_VMOPTIONS_SHELL_FILE}"; fi
. "/home/deepjyoti/.deno/env"

# Path configuration | Package: gonb
export PATH="$HOME/go/bin:$PATH"
export JUPYTER_PATH="$HOME/.local/share/jupyter${JUPYTER_PATH:+:$JUPYTER_PATH}"

# =========================================================
# History
# =========================================================

# Keeps a persistent, shared zsh history while avoiding common duplicates.
mkdir -p "$XDG_STATE_HOME/zsh"
HISTFILE="$XDG_STATE_HOME/zsh/history"
HISTSIZE=50000
SAVEHIST=50000

setopt SHARE_HISTORY
setopt HIST_IGNORE_DUPS
setopt HIST_IGNORE_SPACE

# =========================================================
# Modular Config Files
# =========================================================

# Aliases
source "$HOME/aliases.zsh"
```

### File: `~/aliases.zsh`

```zsh
# =========================================================
# CLI tools
# =========================================================

# Better ls
alias ls='eza --icons=auto'

# Detailed listing
alias ll='eza -lh --icons=auto --git'

# Detailed listing including hidden files
alias la='eza -lah --icons=auto --git'

# Tree view
alias tree='eza --tree --icons=auto'

# Reuse ls completions for eza (avoids defining a separate completion function)
compdef eza=ls

# Better cat
# alias cat='bat'

# =========================================================
# Core utilities
# =========================================================

alias grep='rg --color=auto'
alias diff='diff --color=auto'
alias df='df -h'
alias fd='fdfind'
alias f='fdfind'
alias bat='batcat'
alias cat='batcat -p'
alias rm='rm -i'
alias cp='cp -i'
alias mv='mv -i'

# =========================================================
# Navigation
# =========================================================

# Jump back to the previous directory with `-`
# -- prevents - being parsed as a flag
alias -- -='cd -'

# Launch lf and follow its last visited directory when you quit.
lf() {
    tmp=$(mktemp)
    command lf -last-dir-path="$tmp" "$@"
    if [ -f "$tmp" ]; then
        dir=$(cat "$tmp")
        rm -f "$tmp"
        [ -d "$dir" ] && [ "$dir" != "$(pwd)" ] && cd "$dir"
    fi
}

# =========================================================
# Editor
# =========================================================

# alias vim='nvim'
```

Finally one should execute the following commands to make all of them sync and work:

```zsh
source .zshenv
source .zshrc
```

## Tools and Utilities

### git (`git`)

#### git: Overview

`git` is a version control tool used to track changes in files and projects over time. It is most commonly used for code, but it can track almost any text-based files.

#### git: Why it's useful

- Keeps a history of your work so you can go back if needed.
- Helps you see exactly what changed.
- Makes collaboration easier through GitHub, GitLab, Bitbucket, and similar services.
- Replaces manually copying folders like `project-final-v2`.

#### git: Installation and Verification Commands

```sh
sudo apt install git
git --version
```

#### git: Simple Examples

```sh
# Creates a new Git repository in the current folder
git init

# Shows which files have changed
git status

# Stages all changed files for the next commit
git add .

# Saves the staged changes as a commit
git commit -m "Initial commit"

# Shows commit history in a compact format
git log --oneline
```

#### git: Essential keystrokes

`git` is a non-interactive command-line utility, though some commands may open a text editor.

#### git: Important Concepts

- `Repository`: A folder being tracked by Git.
- `Commit`: A saved snapshot of changes.
- `Staging`: Choosing which changes will go into the next commit.
- `Remote`: A copy of the repository hosted somewhere else, such as GitHub.

---

### bat (`batcat`)

#### bat: Overview

`bat` is a modern replacement for `cat`. It displays file contents with syntax highlighting, line numbers, and nicer formatting.

#### bat: Why it's useful

- Makes files easier to read in the terminal.
- Improves on `cat` by adding colors and line numbers.
- Useful for quickly viewing code, config files, and notes.
- On Ubuntu, the command is usually named `batcat`.

#### bat: Installation and Verification Commands

```sh
sudo apt install bat
batcat --version
```

#### bat: Simple Examples

```sh
# Displays `file.txt` with formatting
batcat file.txt

# Displays a code file with syntax highlighting.
batcat script.py

# Displays the file with line numbers
batcat -n file.txt

# Uses plain output, closer to normal `cat`
batcat -p file.txt
```

#### bat: Essential Keystrokes

If output opens in a pager:

| KeyAction |                    |
| --------- | ------------------ |
| `q`       | Quit               |
| `Space`   | Move down one page |
| `b`       | Move up one page   |
| `/text`   | Search for `text`  |

#### bat: Important concepts

`batcat` vs `bat`: On Ubuntu/Debian, the executable is often called `batcat`.

Useful alias:

```sh
alias bat='batcat'
```

Relationship to `cat`: Use `cat` for raw output; use `batcat` when you want readable output.

---

### tree (`tree`)

#### tree: Overview

`tree` displays folders and files in a visual tree structure.

#### tree: Why it's useful

- Helps you understand a folder or project layout quickly.
- Is easier to read than running many `ls` commands.
- Useful for documenting directory structures.
- Improves on `ls` when you need to see nested folders.

#### tree: Installation and Verification Commands

```sh
sudo apt install tree
tree --version
```

#### tree: Simple Examples

```sh
# Shows the directory tree from the current folder
tree

# Shows only two levels of folders and files
tree -L 2

# Includes hidden files and folders
tree -a

# Shows directories only
tree -d
```

#### tree: Essential Keystrokes

`tree` is non-interactive, so it has no essential keystrokes.

#### tree: Important Concepts

- `Depth`: `-L 2` limits output depth and prevents very large trees.
- `Hidden files`: `-a` includes files such as `.gitignore`.
- `Directories only`: `-d` displays only the folder structure.
- `tree` vs `ls`: `ls` lists one directory; `tree` displays nested directories.

---

### zip (`zip`)

#### zip: Overview

`zip` creates `.zip` archive files from files and folders.

#### zip: Why it's useful

- Combines multiple files into one archive.
- Uses a common format that works across Linux, macOS, and Windows.
- Useful for backups, sharing, uploads, and packaging files.

#### zip: Installation and Verification Commands

```sh
sudo apt install zip unzip
zip --version
```

#### zip: Simple Examples

```sh
# Creates a ZIP archive containing file.txt
zip archive.zip file.txt

# Creates a ZIP archive containing multiple files
zip archive.zip file1.txt file2.txt

# Creates a ZIP archive from the project/ folder recursively
zip -r project.zip project/

# Creates a ZIP archive while excluding the node_modules folder
zip -r project.zip project/ -x "project/node_modules/*"
```

#### zip: Essential Keystrokes

`zip` is non-interactive, so it has no essential keystrokes.

#### zip: Important Concepts

- `Recursive folders`: Use `-r` to include a directory and everything inside it.
- `Archive name first`: Use the format `zip archive.zip file.txt`.
- `Exclude files`: Use `-x` to leave out large or unnecessary files and folders.

---

### unzip (`unzip`)

#### unzip: Overview

`unzip` extracts files from `.zip` archives.

#### unzip: Why it's useful

- Opens ZIP files from downloads, emails, and shared folders.
- Lets you inspect archive contents before extracting.
- Works together with `zip`.

#### unzip: Installation and Verification Commands

```sh
sudo apt install unzip
unzip --version
```

#### unzip: Simple Examples

```sh
# Extracts archive.zip into the current folder
unzip archive.zip

# Extracts archive.zip into the extracted/ folder
unzip archive.zip -d extracted/

# Lists files in the archive without extracting them
unzip -l archive.zip

# Extracts files without overwriting existing files
unzip -n archive.zip
```

#### unzip: Essential Keystrokes

`unzip` is non-interactive, but it may ask before overwriting existing files.

#### unzip: Important Concepts

- `Destination folder`: Use `-d` to choose where files are extracted.
- `Preview first`: Use `unzip -l archive.zip` to inspect an unknown archive before extracting it.
- `Overwrite behavior`: Use `-n` to avoid overwriting existing files.

---

### curl (`curl`)

#### curl: Overview

`curl` transfers data to or from URLs. It is commonly used to download files, check websites, and test APIs.

#### curl: Why it's useful

- Downloads files directly from the terminal.
- Checks web responses without opening a browser.
- Useful for testing APIs.
- More flexible than `wget` for custom HTTP requests.

#### curl: Installation and Verification Commands

```sh
sudo apt install curl
curl --version
```

#### curl: Simple Examples

```sh
# Prints the response from a URL
curl https://example.com

# Shows only the response headers
curl -I https://example.com

# Downloads a file using its original filename
curl -O https://example.com/file.zip

# Follows redirects and downloads the file
curl -L -O https://example.com/file.zip
```

#### curl: Essential Keystrokes

`curl` is non-interactive, so it has no essential keystrokes.

#### curl: Important Concepts

- `Headers`: Use `-I` to show response metadata, such as the status code and content type.
- `Redirects`: Use `-L` to follow redirects.
- `Output files`: Use `-O` to save a download using its remote filename.
- `curl` vs `wget`: `wget` is simple for downloads; `curl` is more flexible for web and API requests.

---

### Ghostty Terminal (`ghostty`)

#### Ghostty Terminal: Overview

Ghostty is a modern terminal emulator. It is the app window where you run shells such as `bash` or `zsh`, along with command-line tools such as `git`, `curl`, and `micro`.

#### Ghostty Terminal: Why it's useful

- Provides a fast, modern terminal experience.
- Supports themes, custom fonts, transparency, tabs, and splits.
- Is a good choice for an iTerm2-style terminal setup on Ubuntu.
- Can replace or complement terminals such as GNOME Terminal, Konsole, Alacritty, and Kitty.

#### Ghostty Terminal: Installation and Verification Commands

```sh
sudo apt install ghostty
ghostty --version
```

#### Ghostty Terminal: Simple Examples

```sh
# Opens Ghostty
ghostty

# Shows available command-line options
ghostty --help

# Shows the active configuration
ghostty +show-config

# Checks whether the configuration is valid
ghostty +validate-config
```

#### Ghostty Terminal: Essential Keystrokes

| Key                | Action                          |
| ------------------ | ------------------------------- |
| `Ctrl + ,`         | Open configuration              |
| `Ctrl + Shift + ,` | Reload configuration            |
| `Ctrl + Shift + C` | Copy                            |
| `Ctrl + Shift + V` | Paste                           |
| `Ctrl + Shift + T` | Open a new tab                  |
| `Ctrl + Shift + W` | Close the current tab or window |

#### Ghostty Terminal: Important Concepts

- `Terminal vs shell`: Ghostty is the terminal application; `zsh` or `bash` is the shell running inside it.
- `Configuration`: Ghostty uses a plain-text configuration file.
- `Theme and font`: These settings control how the terminal looks.
- `Transparency`: `background-opacity` controls how see-through the terminal background is.

#### Ghostty Terminal: Configuration

```conf
# =========================
# iTerm2-style Ghostty — Ubuntu
# =========================

# Theme
theme = Vercel
#theme = iTerm2 Default

# Font
font-family = MesloLGS NF
font-size = 11.5

# Transparency
background-opacity = 0.82
background-blur = true
background-opacity-cells = true

# Cursor
cursor-style = block
cursor-style-blink = true
cursor-color = #FFFFFF
shell-integration = none

# Selection
selection-background = #4A4A4A
selection-foreground = #FFFFFF

# Window padding
window-padding-x = 14
window-padding-y = 12

# Window size
window-width = 140
window-height = 43

# Inactive splits
unfocused-split-opacity = 0.75
```

---

### micro (`micro`)

#### micro: Overview

`micro` is a beginner-friendly text editor that runs in the terminal.

#### micro: Why it's useful

- Easier for beginners than `vim`.
- Uses familiar shortcuts for saving, quitting, copying, and pasting.
- Useful for editing configuration files, notes, scripts, and small code files.
- A practical upgrade from very basic terminal editing.

#### micro: Installation and Verification Commands

```sh
sudo apt install micro
micro --version
```

#### micro: Simple Examples

```sh
# Opens or creates file.txt
micro file.txt

# Edits your Zsh configuration file
micro ~/.zshrc

# Edits a system file with administrator permissions
sudo micro /etc/hosts

# Opens file.txt at line 20
micro +20 file.txt
```

#### micro: Essential Keystrokes

| Key        | Action     |
| ---------- | ---------- |
| `Ctrl + S` | Save       |
| `Ctrl + Q` | Quit       |
| `Ctrl + F` | Search     |
| `Ctrl + G` | Go to line |
| `Ctrl + C` | Copy       |
| `Ctrl + X` | Cut        |
| `Ctrl + V` | Paste      |
| `Ctrl + Z` | Undo       |

#### micro: Important Concepts

- `Terminal editor`: `micro` runs inside your terminal.
- `Save and quit`: Use `Ctrl + S` to save, then `Ctrl + Q` to quit.
- `Config files`: `micro` is convenient for files such as `~/.zshrc` and `~/.gitconfig`.

---

### wl-clipboard (`wl-copy`, `wl-paste`)

#### wl-clipboard: Overview

`wl-clipboard` provides clipboard commands for Wayland sessions. It includes `wl-copy` and `wl-paste`.

#### wl-clipboard: Why it's useful

- Lets terminal commands use your desktop clipboard.
- Useful for copying command output, paths, logs, and file contents.
- Replaces X11 clipboard tools such as `xclip` when you use Wayland.

#### wl-clipboard: Installation and Verification Commands

Check whether your session uses X11 or Wayland:

```sh
echo $XDG_SESSION_TYPE
```

If it shows `x11`, use `xclip`. If it shows `wayland`, use `wl-clipboard`.

```sh
sudo apt install wl-clipboard
echo "Hello" | wl-copy
wl-paste
```

#### wl-clipboard: Simple Examples

```sh
# Copies Hello to the clipboard
echo "Hello" | wl-copy

# Prints the current clipboard contents
wl-paste

# Copies the contents of file.txt
cat file.txt | wl-copy

# Copies the current directory path
pwd | wl-copy
```

#### wl-clipboard: Essential Keystrokes

`wl-clipboard` is non-interactive, so it has no essential keystrokes.

#### wl-clipboard: Important Concepts

- `Wayland vs X11`: Use `wl-clipboard` on Wayland and `xclip` on X11.
- `Piping`: Anything sent into `wl-copy` is copied to the clipboard.
- `Desktop clipboard`: `wl-copy` and `wl-paste` use your normal system clipboard.

---

### zsh (`zsh`)

#### zsh: Overview

`zsh` is a Unix shell. Like `bash`, it runs commands, scripts, aliases, and terminal workflows.

#### zsh: Why it's useful

- More customizable than a default `bash` setup.
- Includes powerful autocomplete and command-history features.
- Works well with prompt tools and frameworks such as Oh My Zsh, Starship, and Powerlevel10k.
- Useful as a modern everyday shell.

#### zsh: Installation and Verification Commands

```sh
sudo apt install zsh
zsh --version
```

To make Zsh your default login shell:

```sh
chsh -s "$(which zsh)"
```

Verify the shell configured for your user:

```sh
grep "^$USER:" /etc/passwd
getent passwd "$USER" | cut -d: -f7
```

After logging out and back in, verify your default and current shells:

```sh
echo "$SHELL"
echo "$0"
```

#### zsh: Simple Examples

```sh
# Starts a Zsh session manually
zsh

# Shows your default login shell
echo "$SHELL"

# Shows the currently running shell
echo "$0"

# Edits your Zsh configuration file
micro ~/.zshrc

# Reloads your Zsh configuration after editing it
source ~/.zshrc
```

#### zsh: Essential Keystrokes

| Key        | Action                                    |
| ---------- | ----------------------------------------- |
| `Tab`      | Autocomplete commands, files, and folders |
| `Ctrl + A` | Move to the beginning of the line         |
| `Ctrl + E` | Move to the end of the line               |
| `Ctrl + R` | Search command history                    |
| `Ctrl + C` | Cancel the current command                |
| `Ctrl + L` | Clear the screen                          |

#### zsh: Important Concepts

- `Shell vs terminal`: Zsh is the shell; Ghostty is a terminal application that can run it.
- `Default shell`: `chsh -s "$(which zsh)"` makes Zsh your login shell.
- `Config file`: `~/.zshrc` controls aliases, prompts, plugins, and shell behavior.
- `Aliases`: Shortcuts for longer commands.

---

### oh-my-zsh (`omz`)

#### oh-my-zsh: Overview

Oh My Zsh is a framework for managing your Zsh configuration, themes, aliases, and plugins.

#### oh-my-zsh: Why it's useful

- Makes Zsh easier to customize.
- Provides built-in plugins for common tools such as `git`, `docker`, and `z`.
- Makes prompt themes and shell enhancements easier to manage.
- Improves plain Zsh by providing a ready-made configuration structure.

#### oh-my-zsh: Installation and Verification Commands

Make sure `zsh` is your current active shell first and then install Oh My Zsh using:

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Verify the installation:

```sh
omz version
```

Update Oh My Zsh:

```sh
omz update
```

#### oh-my-zsh: Install Plugins

Install the zsh-autosuggestions plugin:

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git "$ZSH_CUSTOM/plugins/zsh-autosuggestions"
```

Install the zsh-syntax-highlighting plugin:

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git "$ZSH_CUSTOM/plugins/zsh-syntax-highlighting"
```

Install the fast-syntax-highlighting plugin:

```bash
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting"
```

Install the zsh-autocomplete plugin:

```bash
git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git "$ZSH_CUSTOM/plugins/zsh-autocomplete"
```

Note: use either `zsh-syntax-highlighting` or `fast-syntax-highlighting` in the active Oh My Zsh plugins list. Do not enable both at the same time.

#### oh-my-zsh: (Optional) Remove zsh-syntax-highlighting

If `zsh-syntax-highlighting` was installed by cloning it into the Oh My Zsh custom plugins directory, uninstall it with:

```bash
rm -rf "$ZSH_CUSTOM/plugins/zsh-syntax-highlighting"
```

Verify that the plugin directory no longer exists:

```bash
ls "$ZSH_CUSTOM/plugins/zsh-syntax-highlighting"
```

It should report that the directory does not exist.

You can also check whether it is still configured in `.zshrc`:

```bash
grep -n "zsh-syntax-highlighting" ~/.zshrc
```

If this command returns a matching line in `plugins=(...)`, remove that entry from the plugins list.

#### oh-my-zsh: Simple Examples

```sh
# Shows the installed Oh My Zsh version
omz version

# Updates Oh My Zsh
omz update

# Opens your Zsh configuration to edit themes, plugins, and aliases
micro ~/.zshrc

# Reloads your Zsh configuration after editing it
source ~/.zshrc
```

#### oh-my-zsh: Essential Keystrokes

`omz` is non-interactive, so it has no essential keystrokes. Editing `~/.zshrc` uses your text editor.

#### oh-my-zsh: Important Concepts

- `~/.zshrc`: Your main Zsh configuration file.
- `Themes`: Control how your prompt looks.
- `Plugins`: Add shortcuts, completions, and helper commands.
- `$ZSH_CUSTOM`: The usual location for custom themes and plugins.

---

### Powerlevel10k and Additional oh-my-zsh Plugins (`p10k`)

#### Powerlevel10k: Overview

Powerlevel10k is a fast, highly customizable Zsh prompt theme. It is commonly used with Oh My Zsh.

#### Powerlevel10k: Why it's useful

- Gives your terminal a more informative prompt.
- Can show Git status, the current folder, time, language versions, and more.
- Works well with Nerd Fonts such as MesloLGS NF.
- Improves the default shell prompt by making important context visible.

#### Powerlevel10k: Installation and Verification Commands

Setup guide: [Zsh Plugins](https://gist.github.com/n1snt/454b879b8f0b7995740ae04c5fb5b7df)

```sh
# Installs the Powerlevel10k theme and useful Zsh plugins
git clone https://github.com/romkatv/powerlevel10k.git "$ZSH_CUSTOM/themes/powerlevel10k"
git clone --depth 1 https://github.com/marlonrichert/zsh-autocomplete.git "$ZSH_CUSTOM/plugins/zsh-autocomplete"
git clone https://github.com/zsh-users/zsh-autosuggestions "${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions"
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting"

# Opens your Zsh configuration file
micro ~/.zshrc
```

Update these fields in `~/.zshrc`:

```sh
plugins=(
    docker
    docker-compose
    extract
    fast-syntax-highlighting
    git
    sublime
    web-search
    z
    zsh-autocomplete
    zsh-autosuggestions
)

ZSH_THEME="powerlevel10k/powerlevel10k"
```

Reload your configuration:

```sh
source ~/.zshrc
```

Recommended choices during the first interactive setup:

```text
Diamond: Press 'y'
Lock: Press 'y'
Debian Logo: Press 'y' (or) Pointer check: Press 'y'
Icon Check: Press 'y'
Prompt Style: Select 'Rainbow'
Character Set: Select 'Unicode'
Current Time: Select '12 hour format'
Prompt Separators: Select 'Angled'
Prompt Head: Select 'Sharp'
Prompt Tails: Select 'Flat'
Prompt Height: Select 'Two lines'
Prompt Connection: Select 'Dotted'
Prompt Frame: Select 'Full'
Connection and Frame: Select 'Dark'
Prompt Spacing: Select 'Sparse'
Icons: Select 'Many icons'
Prompt Flow: Select 'Concise'
Enable Transient Prompt?: Choose 'No'
Instant Prompt Mode: Select 'Verbose'
Overwrite ~/.p10k.zsh?: Choose 'Yes'
```

Run the configuration wizard again whenever needed:

```sh
p10k configure
```

`skip_global_compinit=1` is required for `zsh-autocomplete` on Ubuntu. It prevents Ubuntu's system-wide Zsh configuration from automatically running `compinit`, allowing `zsh-autocomplete` to initialize and manage completion itself.

```sh
touch ~/.zshenv
echo "skip_global_compinit=1" >> ~/.zshenv
exec zsh
echo "$skip_global_compinit"
```

#### Powerlevel10k: Simple Examples

```sh
# Starts the interactive prompt setup
p10k configure

# Edits your theme and plugin settings
micro ~/.zshrc

# Reloads your shell configuration
source ~/.zshrc

# Restarts the current Zsh session
exec zsh
```

#### Powerlevel10k: Essential Keystrokes

During `p10k configure`, use the choices shown on screen.

| Key        | Action                      |
| ---------- | --------------------------- |
| `y`        | Answer yes to a prompt      |
| `n`        | Answer no to a prompt       |
| `Enter`    | Confirm the selected option |
| `Ctrl + C` | Cancel setup                |

#### Powerlevel10k: Important Concepts

- `Prompt theme`: Powerlevel10k changes your shell prompt, not your terminal application.
- `Nerd Font`: A Nerd Font is required for icons to display correctly.
- `Plugins`: `zsh-autocomplete`, `zsh-autosuggestions`, and syntax highlighting improve daily shell usage.
- `~/.p10k.zsh`: Powerlevel10k's detailed theme configuration file.

#### Powerlevel10k: `~/.zshrc` Configuration

```sh
# ----------------------------------
# Powerlevel10k Config
# ----------------------------------

# Enable Powerlevel10k instant prompt. Keep this close to the top of ~/.zshrc.
# Initialization code that may require console input, such as password prompts
# or [y/n] confirmations, must go above this block.
if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi

# ----------------------------------
# Theme
# ----------------------------------

# Path to your Oh My Zsh installation.
export ZSH="$HOME/.oh-my-zsh"

# Set the theme to load.
ZSH_THEME="powerlevel10k/powerlevel10k"

# ----------------------------------
# Plugins
# ----------------------------------

plugins=(
    docker
    docker-compose
    extract
    fast-syntax-highlighting
    git
    sublime
    web-search
    z
    zsh-autocomplete
    zsh-autosuggestions
)

source "$ZSH/oh-my-zsh.sh"

# ----------------------------------
# Aliases
# ----------------------------------

alias rm='rm -i'
alias cp='cp -i'
alias mv='mv -i'
alias bat='batcat'

# ----------------------------------
# Tool Startup Config
# ----------------------------------

# To customize the prompt, run `p10k configure` or edit ~/.p10k.zsh.
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh

# SDKMan: This must stay at the end of the file for SDKMan to work.
export SDKMAN_DIR="$HOME/.sdkman"
[[ -s "$HOME/.sdkman/bin/sdkman-init.sh" ]] && source "$HOME/.sdkman/bin/sdkman-init.sh"

# pyenv
export PYENV_ROOT="$HOME/.pyenv"
[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init - zsh)"

# nvm
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"
[ -s "$NVM_DIR/bash_completion" ] && . "$NVM_DIR/bash_completion"

# Zed
export PATH="$HOME/.local/bin:$PATH"

# Deno
___MY_VMOPTIONS_SHELL_FILE="${HOME}/.jetbrains.vmoptions.sh"
if [ -f "${___MY_VMOPTIONS_SHELL_FILE}" ]; then
  . "${___MY_VMOPTIONS_SHELL_FILE}"
fi
. "$HOME/.deno/env"

# Go / gonb
export PATH="$HOME/go/bin:$PATH"
```

---

### SDKMan (`sdk`)

#### SDKMan: Overview

SDKMan manages software development kits such as Java, Gradle, Maven, and JMeter.

#### SDKMan: Why it's useful

- Installs developer tools without manually downloading archives.
- Lets you manage multiple versions of Java and related tools.
- Makes switching versions easier.
- Improves on one-off manual installations for JVM-based tooling.

#### SDKMan: Installation and Verification Commands

```sh
curl -s "https://get.sdkman.io" | bash
source ~/.zshrc
sdk version
```

#### SDKMan: Simple Examples

```sh
# Shows the installed SDKMan version
sdk version

# Lists available Java versions
sdk list java

# Shows currently active SDKMan-managed tools
sdk current

# Cleans SDKMan temporary files and caches
sdk flush
```

#### SDKMan: Essential Keystrokes

`sdk` is non-interactive, though some installations may ask for confirmation.

#### SDKMan: Important Concepts

- `Candidate`: A tool SDKMan can install, such as Java, Gradle, or Maven.
- `Version`: SDKMan lets you install more than one version of the same tool.
- `Default version`: The version used automatically in new terminal sessions.
- `Shell config`: SDKMan needs its initialization script loaded from `~/.zshrc`.

---

### Java (`java`)

#### Java: Overview

Java is a programming language and runtime used by many backend, Android, data, and enterprise tools. SDKMan is a convenient way to install and manage Java versions.

#### Java: Why it's useful

- Many tools require Java, including Gradle, Maven, and JMeter.
- SDKMan makes it easy to install multiple Java versions.
- Useful when different projects require different Java versions.

#### Java: Installation and Verification Commands

```sh
# Lists available Java versions
sdk list java

# Installs Temurin Java versions
sdk install java 25.0.4-tem
sdk install java 21.0.12-tem
sdk install java 8.0.502-tem

# Shows the currently active Java version
sdk current java

# Shows installed and local Java versions
sdk list java | grep -e installed -e local

# Cleans SDKMan temporary files and caches
sdk flush
```

If required:

```sh
sdk update
sdk selfupdate
sdk default java 21.0.12-tem
```

#### Java: Simple Examples

```sh
# Lists Java versions available through SDKMan
sdk list java

# Installs Java 21 from the Temurin distribution
sdk install java 21.0.12-tem

# Shows the currently active Java version
sdk current java

# Checks the Java runtime version
java -version
```

#### Java: Essential Keystrokes

Java and SDKMan commands are non-interactive, though installations may ask for confirmation.

#### Java: Important Concepts

- `JDK vs JRE`: A JDK is used for development; a JRE is only for running Java applications.
- `LTS versions`: Java 8, 11, 17, and 21 are common long-term support versions.
- `Default version`: `sdk default java ...` sets the Java version for new shells.
- `Temurin`: The `-tem` suffix refers to Eclipse Temurin builds.

---

### Gradle (`gradle`)

#### Gradle: Overview

Gradle is a build tool commonly used for Java, Kotlin, Android, and JVM projects.

#### Gradle: Why it's useful

- Builds, tests, and packages projects.
- Common in Android and modern JVM projects.
- Runs project-defined tasks consistently.
- Often replaces older Ant-based build workflows and complements Maven.

#### Gradle: Installation and Verification Commands

```sh
sdk list gradle
sdk install gradle 9.7.0
sdk default gradle 9.7.0
source ~/.zshrc
gradle --version
```

#### Gradle: Simple Examples

```sh
# Shows the installed Gradle version
gradle --version

# Lists available tasks in a Gradle project
gradle tasks

# Builds the project
gradle build

# Runs project tests
gradle test
```

#### Gradle: Essential Keystrokes

`gradle` is non-interactive, so it has no essential keystrokes.

#### Gradle: Important Concepts

- `Task`: A named action Gradle can run, such as `build` or `test`.
- `Wrapper`: Many projects use `./gradlew` instead of a system-wide `gradle` command.
- `Build file`: Gradle projects usually use `build.gradle` or `build.gradle.kts`.

---

### Maven (`mvn`)

#### Maven: Overview

Maven is a build and dependency-management tool commonly used for Java projects.

#### Maven: Why it's useful

- Builds Java projects in a standard way.
- Downloads and manages dependencies.
- Common in enterprise Java projects.
- Complements Gradle; both solve similar build problems with different styles.

#### Maven: Installation and Verification Commands

```sh
sdk list maven
sdk install maven 3.9.16
mvn --version
```

#### Maven: Simple Examples

```sh
# Shows the installed Maven version
mvn --version

# Compiles the project
mvn compile

# Runs tests
mvn test

# Builds the project package, such as a .jar file
mvn package
```

#### Maven: Essential Keystrokes

`mvn` is non-interactive, so it has no essential keystrokes.

#### Maven: Important Concepts

- `pom.xml`: Maven's main project configuration file.
- `Lifecycle`: Maven has standard phases such as `compile`, `test`, and `package`.
- `Dependencies`: Maven downloads project libraries automatically.

---

### JMeter (`jmeter`)

#### JMeter: Overview

JMeter is a tool for load testing and performance testing applications, especially web APIs and services.

#### JMeter: Why it's useful

- Tests how a service behaves under load.
- Useful for API, web, and backend performance checks.
- Can run with a GUI for designing tests or from the command line for automation.

#### JMeter: Installation and Verification Commands

```sh
sdk list jmeter
sdk install jmeter 5.6.3
jmeter --version
```

#### JMeter: Simple Examples

```sh
# Shows the installed JMeter version
jmeter --version

# Opens the JMeter GUI
jmeter

# Runs a test plan in non-GUI mode
jmeter -n -t test-plan.jmx

# Runs a test plan and saves results to results.jtl
jmeter -n -t test-plan.jmx -l results.jtl
```

#### JMeter: Essential Keystrokes

If using the JMeter GUI:

| Key        | Action         |
| ---------- | -------------- |
| `Ctrl + S` | Save test plan |
| `Ctrl + O` | Open test plan |
| `Ctrl + R` | Start test     |
| `Ctrl + .` | Stop test      |

#### JMeter: Important Concepts

- `Test plan`: A `.jmx` file that describes what JMeter should test.
- `Thread group`: Controls virtual users and the load pattern.
- `GUI vs non-GUI`: Use the GUI to design tests; use `-n` mode to run repeatable tests.
- `Results file`: `-l results.jtl` saves test results.

---

### AQL (`aql`)

#### AQL: Overview

`aql` is the Aerospike Query Language shell. It is used to connect to Aerospike databases and run queries or administrative checks.

#### AQL: Why it's useful

- Lets you interact with Aerospike from the terminal.
- Useful for checking records, namespaces, sets, and indexes.
- Comes with Aerospike Tools.
- Similar in purpose to `mysql` or `psql`, but for Aerospike.

#### AQL: Installation and Verification Commands

Check your Ubuntu version and CPU architecture:

```sh
lsb_release -a
uname -m
```

Example output:

```text
Ubuntu 26.04
x86_64
```

1. Visit [Aerospike Tools downloads](https://aerospike.com/download/tools/) to find the latest compatible version.
2. Select **Supported Versions** and copy the download link for your Ubuntu version and CPU architecture.
3. Download and install the matching package:

```sh
wget https://download.aerospike.com/artifacts/aerospike-tools/13.0.2/aerospike-tools_13.0.2_ubuntu26.04_x86_64.tgz
tar -xvf aerospike-tools_13.0.2_ubuntu26.04_x86_64.tgz
cd aerospike-tools_13.0.2_ubuntu26.04_x86_64
sudo dpkg -i aerospike-tools_13.0.2-ubuntu26.04_amd64.deb
aql --version
```

#### AQL: Simple Examples

```sh
# Shows the installed AQL version
aql --version

# Starts the AQL shell using default connection settings
aql

# Connects to Aerospike on host 127.0.0.1 and port 3000
aql -h 127.0.0.1 -p 3000

# Runs one AQL command and exits
aql -c "show namespaces"
```

#### AQL: Essential Keystrokes

Inside the interactive AQL shell:

| Key        | Action                       |
| ---------- | ---------------------------- |
| `Ctrl + C` | Cancel current input or exit |
| `Ctrl + D` | Exit the shell               |
| `Enter`    | Run the command              |

#### AQL: Important Concepts

- `Aerospike Tools`: The package that includes `aql`.
- `Host and port`: Aerospike commonly listens on port `3000`.
- `Interactive vs one-shot`: Use `aql` to open a shell, or `aql -c "command"` to run one command.
- `Version matching`: Download the Aerospike Tools build that matches your Ubuntu version and CPU architecture.

---

### NVM (`nvm`)

#### NVM: Overview

NVM is Node Version Manager. It installs and switches between Node.js versions.

#### NVM: Why it's useful

- Lets you install Node.js without using system packages.
- Makes it easy to use different Node.js versions for different projects.
- Installs `npm` along with Node.js.
- Improves on a single global Node.js installation.

#### NVM: Installation and Verification Commands

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
source ~/.zshrc
nvm --version

# Installs the latest long-term support version of Node.js
nvm install --lts

# Verifies Node.js and npm
node -v
npm -v
```

Optional commands:

```sh
# Switches the current shell to the LTS Node.js version
nvm use --lts

# Makes the LTS version the default for new shells
nvm alias default 'lts/*'
```

#### NVM: Simple Examples

```sh
# Shows the installed NVM version
nvm --version

# Installs the latest long-term support version of Node.js
nvm install --lts

# Switches the current shell to the LTS Node.js version
nvm use --lts

# Shows the active Node.js version
node -v
```

#### NVM: Essential Keystrokes

`nvm` is a non-interactive shell function, so it has no essential keystrokes.

#### NVM: Important Concepts

- `Node.js`: A JavaScript runtime used for frontend tooling and backend applications.
- `LTS`: A long-term support version, recommended for most users.
- `Default alias`: Controls which Node.js version new shells use.
- `Shell integration`: NVM must be loaded from your shell configuration file.

---

### MariaDB Client (`mysql`)

#### MariaDB Client: Overview

MariaDB Client provides the `mysql` command-line client. It is used to connect to MySQL or MariaDB databases.

#### MariaDB Client: Why it's useful

- Lets you connect to remote MySQL or MariaDB databases from the terminal.
- Useful for checking tables, running queries, and debugging database access.
- Lets you install only the client without installing a full database server.
- Replaces needing a GUI tool for quick database checks.

#### MariaDB Client: Installation and Verification Commands

If you only need the `mysql` command to connect to another database:

```sh
sudo apt install -y mariadb-client
mysql --version
mysql -h <db-host> -P 3306 -u <username> -p
```

If the package cannot be found, use this on Fedora/RHEL-style systems:

```sh
dnf install -y mariadb
```

#### MariaDB Client: Simple Examples

```sh
# Shows the installed MySQL/MariaDB client version
mysql --version

# Connects to a remote database and prompts for a password
mysql -h <db-host> -P 3306 -u <username> -p

# Connects as the local root user and prompts for a password
mysql -u root -p

# Connects directly to a specific database
mysql -h <db-host> -u <username> -p <database>
```

#### MariaDB Client: Essential Keystrokes

Inside the interactive MySQL shell:

| Key        | Action                                    |
| ---------- | ----------------------------------------- |
| `Ctrl + C` | Cancel current input                      |
| `Ctrl + D` | Exit the shell                            |
| `Enter`    | Continue or run a completed SQL statement |

#### MariaDB Client: Important Concepts

- `Client vs server`: `mariadb-client` installs the command used to connect; it does not install a database server.
- `Host`: `-h` chooses the database server.
- `Port`: `-P 3306` uses the default MySQL or MariaDB port.
- `Password prompt`: `-p` asks for a password securely.

---

### pyenv (`pyenv`)

#### pyenv: Overview

`pyenv` manages multiple Python versions on one system.

#### pyenv: Why it's useful

- Lets you install newer Python versions without replacing the system Python.
- Helps different projects use different Python versions.
- Avoids breaking Ubuntu's system Python.
- Useful for development, testing, and tool compatibility.

#### pyenv: Installation and Verification Commands

```sh
# Installs dependencies needed to build Python versions
sudo apt update
sudo apt install -y make build-essential libssl-dev zlib1g-dev \
  libbz2-dev libreadline-dev libsqlite3-dev curl git \
  libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev \
  libffi-dev liblzma-dev

# Installs pyenv
curl https://pyenv.run | bash

# Adds pyenv to your Zsh configuration
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init - zsh)"' >> ~/.zshrc

# Reloads the configuration
source ~/.zshrc

# Finds, installs, and activates a Python version
pyenv install --list | grep 3.14
pyenv install 3.14.7
pyenv global 3.14.7

# Verifies the active Python version
python --version

# Updates pyenv
pyenv update
```

#### pyenv: Simple Examples

```sh
# Lists Python versions available to install
pyenv install --list

# Installs Python 3.14.7
pyenv install 3.14.7

# Sets Python 3.14.7 as the global default
pyenv global 3.14.7

# Shows the active Python version
python --version
```

#### pyenv: Essential Keystrokes

`pyenv` is non-interactive, so it has no essential keystrokes.

#### pyenv: Important Concepts

- `System Python`: Ubuntu uses its own Python; avoid replacing it directly.
- `Global version`: The default Python version for your user account.
- `Local version`: A project-specific Python version, usually set with `pyenv local`.
- `Build dependencies`: Python versions are compiled locally, so required libraries must be installed first.

---

### Docker Desktop (`docker`)

#### Docker Desktop: Overview

Docker Desktop provides Docker Engine, Docker CLI, Docker Compose, and a desktop user interface for running containers on Ubuntu.

#### Docker Desktop: Why it's useful

- Runs applications in isolated containers.
- Makes local development environments easier to reproduce.
- Common for databases, backend services, and development stacks.
- Improves on installing every service directly on your host system.

#### Docker Desktop: Installation and Verification Commands

See the official [Docker Desktop for Ubuntu installation guide](https://docs.docker.com/desktop/setup/install/linux/ubuntu/).

Download `docker-desktop-amd64.deb`, then install the `docker-ce-cli` dependency:

```sh
sudo apt install -y ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg \
  -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Verify that `docker-ce-cli` is available:

```sh
sudo apt update
apt-cache policy docker-ce-cli
```

Install and start Docker Desktop:

```sh
cd ~/Downloads
sudo apt install ./docker-desktop-amd64.deb

systemctl --user start docker-desktop
docker --version
docker compose version
docker run hello-world

systemctl --user status docker-desktop
```

Stop Docker Desktop:

```sh
systemctl --user stop docker-desktop
```

Prevent Docker Desktop from starting automatically:

```sh
systemctl --user disable docker-desktop
```

Enable automatic startup again:

```sh
systemctl --user enable docker-desktop
```

#### Docker Desktop: Simple Examples

```sh
# Shows the Docker CLI version
docker --version

# Runs Docker's test container to verify the setup
docker run hello-world

# Lists currently running containers
docker ps

# Shows the Docker Compose version
docker compose version
```

#### Docker Desktop: Essential Keystrokes

`docker` is non-interactive, so it has no essential keystrokes. Docker Desktop also provides a graphical interface.

#### Docker Desktop: Important Concepts

- `Image`: A packaged template used to create containers.
- `Container`: A running instance of an image.
- `Compose`: A way to run multi-container applications from a `compose.yaml` file.
- `Docker Desktop service`: Controlled with `systemctl --user`.

---

### JetBrains Toolbox (`jetbrains-toolbox`)

#### JetBrains Toolbox: Overview

JetBrains Toolbox manages JetBrains IDEs such as IntelliJ IDEA, PyCharm, WebStorm, Android Studio, and DataGrip.

#### JetBrains Toolbox: Why it's useful

- Installs and updates JetBrains IDEs from one place.
- Makes it easier to manage multiple JetBrains tools.
- Creates application launchers after the first launch.
- Is better than manually extracting and updating every IDE separately.

#### JetBrains Toolbox: Installation and Verification Commands

Download JetBrains Toolbox from the official [JetBrains Toolbox App page](https://www.jetbrains.com/toolbox-app/).

```sh
# Installs required dependencies
sudo apt update
sudo apt install -y \
  libxi6 \
  libxrender1 \
  libxtst6 \
  mesa-utils \
  libfontconfig1 \
  libgtk-3-bin \
  tar \
  dbus-user-session \
  libxcb-keysyms1

# Creates an applications folder and extracts Toolbox into it
mkdir -p ~/Applications
tar -xvf ~/Downloads/jetbrains-toolbox-3.7.2.87231.tar.gz -C ~/Applications
mv ~/Applications/jetbrains-toolbox-3.7.2.87231 ~/Applications/jetbrains-toolbox

# Starts JetBrains Toolbox
cd ~/Applications/jetbrains-toolbox/bin
./jetbrains-toolbox
```

Toolbox creates its application launcher after its first launch.

Toolbox stores application files here:

```text
~/.local/share/JetBrains/Toolbox
```

It also creates a desktop entry here:

```text
~/.local/share/applications
```

After the first launch, JetBrains Toolbox should be available from Ubuntu's application launcher.

#### JetBrains Toolbox: Simple Examples

```sh
# Starts JetBrains Toolbox from its extracted folder
./jetbrains-toolbox

# Checks whether Toolbox created its local files
ls ~/.local/share/JetBrains/Toolbox

# Checks for JetBrains desktop launchers
ls ~/.local/share/applications | grep -i jetbrains
```

#### JetBrains Toolbox: Essential Keystrokes

The command-line setup has no essential keystrokes. JetBrains Toolbox itself is a graphical application.

#### JetBrains Toolbox: Important Concepts

- `Toolbox app`: A manager for JetBrains IDE installations.
- `Application launcher`: Created after the first launch so you can open Toolbox from Ubuntu search.
- `Install location`: This setup places Toolbox under `~/Applications`.

---

### GitHub Desktop (`github-desktop`)

#### GitHub Desktop: Overview

GitHub Desktop is a graphical Git client for working with GitHub repositories.

#### GitHub Desktop: Why it's useful

- Easier for beginners than using only Git commands.
- Helps visualize branches, commits, and file changes.
- Useful for cloning, committing, pushing, and pulling from GitHub.
- Complements `git`; it does not replace learning basic Git commands.

#### GitHub Desktop: Installation and Verification Commands

Linux repository: [sarim/github-desktop](https://github.com/sarim/github-desktop)

```sh
sudo apt update
sudo apt install -y wget gpg
```

Add the repository signing key:

```sh
wget -qO - https://mirror.mwt.me/shiftkey-desktop/gpgkey | \
  gpg --dearmor | \
  sudo tee /etc/apt/keyrings/mwt-desktop.gpg > /dev/null
```

Add the repository:

```sh
sudo sh -c 'echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/mwt-desktop.gpg] https://mirror.mwt.me/shiftkey-desktop/deb/ any main" > /etc/apt/sources.list.d/mwt-desktop.list'
```

Install and verify GitHub Desktop:

```sh
sudo apt update
sudo apt install -y github-desktop
github-desktop --version
github-desktop
```

#### GitHub Desktop: Simple Examples

```sh
# Shows the installed GitHub Desktop version
github-desktop --version

# Opens GitHub Desktop
github-desktop

# Checks repository state in the terminal
git status
```

#### GitHub Desktop: Essential Keystrokes

GitHub Desktop is interactive:

| Key                | Action                                          |
| ------------------ | ----------------------------------------------- |
| `Ctrl + O`         | Add or open a repository                        |
| `Ctrl + Shift + O` | Clone a repository                              |
| `Ctrl + Enter`     | Commit changes                                  |
| `Ctrl + P`         | Push or pull, depending on the repository state |

#### GitHub Desktop: Important Concepts

- `Repository`: A Git-tracked project folder.
- `Commit`: A saved set of changes.
- `Push and pull`: Synchronize local work with GitHub.
- `GitHub Desktop vs git`: GitHub Desktop is a graphical interface built on top of Git workflows.

---

### Allure (`allure`)

#### Allure: Overview

Allure is a test reporting tool. It turns test result files into readable HTML reports.

#### Allure: Why it's useful

- Makes automated test results easier to inspect.
- Works with frameworks such as JUnit, TestNG, Pytest, Playwright, and Cucumber.
- Helps share test failures and trends with a team.

#### Allure: Installation and Verification Commands

```sh
npm install -g allure
allure --version
```

#### Allure: Simple Examples

```sh
# Shows the installed Allure version
allure --version

# Generates and opens a temporary report from allure-results
allure serve allure-results

# Generates a static report folder
allure generate allure-results -o allure-report

# Opens an already generated report
allure open allure-report
```

#### Allure: Essential Keystrokes

`allure` is non-interactive, so it has no essential keystrokes.

#### Allure: Important Concepts

- `Results folder`: Test frameworks usually write raw Allure files to `allure-results`.
- `Report folder`: `allure-report` contains the generated HTML report.
- `Serve vs generate`: `serve` is for a quick preview; `generate` creates reusable output.

---

### Vim (`vim`)

#### Vim: Overview

Vim is a powerful terminal text editor commonly available on Unix and Linux systems.

#### Vim: Why it's useful

- Works almost everywhere, including remote servers.
- Good for quick edits when no graphical editor is available.
- Very powerful once you learn the basics.
- More advanced than beginner-friendly editors such as `nano` or `micro`.

#### Vim: Installation and Verification Commands

```sh
sudo apt install -y vim
vim --version
```

#### Vim: Simple Examples

```sh
# Opens or creates file.txt
vim file.txt

# Edits your Zsh configuration
vim ~/.zshrc

# Edits a system file with administrator permissions
sudo vim /etc/hosts
```

#### Vim: Essential Keystrokes

| Key     | Action                |
| ------- | --------------------- |
| `i`     | Enter insert mode     |
| `Esc`   | Return to normal mode |
| `:w`    | Save                  |
| `:q`    | Quit                  |
| `:wq`   | Save and quit         |
| `:q!`   | Quit without saving   |
| `/text` | Search for `text`     |

#### Vim: Important Concepts

- `Modes`: Vim has normal mode and insert mode.
- `Normal mode`: Used for commands such as save, quit, delete, and search.
- `Insert mode`: Used for typing text.
- `Vim vs micro`: `micro` is easier for beginners; Vim is more universal and powerful.

---

### Zed (`zed`)

#### Zed: Overview

Zed is a modern code editor focused on speed and collaboration.

#### Zed: Why it's useful

- A fast graphical editor for code and projects.
- Useful alongside terminal tools such as `git`, `npm`, and `python`.
- Can be launched from the terminal after adding it to your `PATH`.

#### Zed: Installation and Verification Commands

```sh
# Installs Zed
curl -f https://zed.dev/install.sh | sh

# Adds Zed to your PATH for future Zsh sessions
echo 'export PATH=$HOME/.local/bin:$PATH' >> ~/.zshrc

# Reloads the Zsh configuration
source ~/.zshrc

# Verifies the installation and opens Zed
zed --version
zed
```

#### Zed: Simple Examples

```sh
# Shows the installed Zed version
zed --version

# Opens Zed
zed

# Opens the current folder as a project
zed .

# Opens a specific file
zed file.txt
```

#### Zed: Necessary Extensions

Click on 'Zed' on the apple menu bar -> 'Extensions' (`Shift + Command + X`)

- Dockerfile v0.3.0
- Docker Compose v0.1.0
- GraphQL v1.0.6 (Optional)
- Go Snippets v0.1.5
- HTML v0.3.2
- Java v6.8.27
- Java with Eclipse JDTLS v0.2.5
- JavaScript Snippets v0.1.0
- LOG v0.0.7
- Markdown Snippets v0.1.0
- Material Icon Theme v1.3.1
- One Dark Pro v0.0.11
- One Dark Pro Max v0.0.2
- One Dark Pro Monokai Darker Theme v0.1.1
- Python Snippets v0.1.3
- PHP v0.5.3
- Rainbow CSV v1.1.0
- SQL v1.1.8

#### Zed: Configuration

Click on 'Zed' on the apple menu bar -> 'Settings' -> 'Open Settings' (`Command + ,`)

```json
// Zed settings
//
// For information on how to configure Zed, see the Zed
// documentation: https://zed.dev/docs/configuring-zed
//
// To see all of Zed's default settings without changing your
// custom settings, run zed: open default settings from the
// command palette (cmd-shift-p / ctrl-shift-p)
{
  "buffer_font_family": "Cascadia Mono",
  "buffer_font_size": 15,
  "ui_font_size": 17,
  "icon_theme": "Material Icon Theme",
  "autosave": "off",
  "soft_wrap": "editor_width",
  "auto_indent_on_paste": true,
  "use_autoclose": true,
  "project_panel": {
    "dock": "left"
  },
  "terminal": {
    "dock": "right",
    "font_family": "MesloLGS NF",
    "font_size": 15
  },
  "theme": {
    "mode": "system",
    "light": "One Dark Pro Glass",
    "dark": "One Dark Pro Glass"
  },
  "telemetry": {
    "diagnostics": false,
    "metrics": false,
    "anthropic_retention": false
  }
}
```

#### Zed: Fix Saying Open After Closing on Linux

On some Linux desktops, Zed may stay running after the window is closed, delay relaunching, or appear as a lingering zombie/defunct process. This is often related to Wayland protocol integration behavior or a startup notification timeout.

This guide covers a simple desktop-entry fix: disabling `StartupNotify` for Zed.

**Problem**

After closing Zed, you may notice symptoms such as:

- Zed does not fully exit.
- Relaunching Zed is delayed.
- A leftover process appears in process tools.
- You need to run `pkill -f zed` before Zed opens normally again.

The issue can happen when the desktop environment keeps waiting for startup notification state that never resolves cleanly.

**Fix**

- First, close Zed completely:

  ```bash
  pkill -f zed
  ```

Then update Zed's desktop entry.

- Locate the Zed desktop file:

  ```bash
  ~/.local/share/applications/zed.desktop
  ```

  If it is not there, check:

  ```bash
  /usr/share/applications/zed.desktop
  ```

- Open the file in your text editor.

- Find this line:

  ```ini
  StartupNotify=true
  ```

- Change it to:

  ```ini
  StartupNotify=false
  ```

  You can also delete the line entirely.

- Log out and log back in, or restart your application launcher/desktop session.

**Verify**

Open Zed normally from your launcher, then close it.

Check that no Zed process remains:

```bash
pgrep -af zed
```

If the command returns no Zed process, the fix worked. You should also be able to relaunch Zed without needing `pkill -f zed`.

#### Zed: Essential Keystrokes

Zed is interactive:

| Key                | Action                   |
| ------------------ | ------------------------ |
| `Ctrl + O`         | Open a file or folder    |
| `Ctrl + S`         | Save                     |
| `Ctrl + P`         | Quickly open a file      |
| `Ctrl + Shift + P` | Open the command palette |
| `Ctrl + F`         | Search in the file       |

#### Zed: Important Concepts

- `Editor vs terminal`: Zed is a graphical code editor; Ghostty is a terminal application.
- `PATH`: Adding `~/.local/bin` lets you run `zed` from the terminal.
- `Project folder`: `zed .` opens your current folder as a project.

---

### uv (`uv`)

#### uv: Overview

`uv` is a fast Python package and project manager.

#### uv: Why it's useful

- Creates and manages Python project environments.
- Installs dependencies quickly.
- Useful for running Python tools without manually managing virtual environments.
- Replaces or improves on many common `pip` and `venv` workflows.

#### uv: Installation and Verification Commands

```sh
curl -LsSf https://astral.sh/uv/install.sh | sh
uv --version
```

#### uv: Simple Examples

```sh
# Shows the installed uv version
uv --version

# Installs dependencies for a project that uses uv
uv sync

# Runs Python inside the project environment
uv run python --version

# Starts Jupyter Notebook from the project environment
uv run jupyter notebook
```

#### uv: Essential Keystrokes

`uv` is non-interactive, so it has no essential keystrokes.

#### uv: Important Concepts

- `Project environment`: uv manages an environment for each project.
- `uv sync`: Installs dependencies defined by the project.
- `uv run`: Runs a command inside the uv-managed environment.
- `uv vs pip`: uv can handle package installation much faster than traditional `pip` workflows.

---

### Ollama (`ollama`)

#### Ollama: Overview

Ollama runs local AI models on your machine from the command line.

#### Ollama: Why it's useful

- Lets you download and run models locally.
- Useful for experimenting with local LLMs.
- Provides a simple local API at `http://127.0.0.1:11434`.
- Avoids needing a cloud API for basic local-model experiments.

#### Ollama: Installation and Verification Commands

```sh
curl -fsSL https://ollama.com/install.sh | sh
ollama --version
```

Check the Ollama service and local API:

```sh
systemctl status ollama
curl http://127.0.0.1:11434
```

Start the Ollama service:

```sh
sudo systemctl start ollama
```

Stop the Ollama service:

```sh
sudo systemctl stop ollama
```

Prevent Ollama from starting automatically:

```sh
sudo systemctl disable --now ollama
```

Enable Ollama to start automatically after reboot:

```sh
sudo systemctl enable --now ollama
```

Common Ollama commands:

```sh
ollama pull qwen3:8b
ollama run qwen3:8b
ollama list
ollama ps
ollama stop qwen3:8b
ollama rm qwen3:8b
ollama show qwen3:8b
ollama --version
ollama help
```

#### Ollama: Simple Examples

```sh
# Downloads the qwen3:8b model
ollama pull qwen3:8b

# Runs the model interactively
ollama run qwen3:8b

# Lists downloaded models
ollama list

# Shows currently running models
ollama ps
```

#### Ollama: Essential Keystrokes

When running a model interactively:

| Key        | Action                                   |
| ---------- | ---------------------------------------- |
| `Ctrl + D` | Exit the prompt                          |
| `Ctrl + C` | Cancel the current generation or command |
| `Enter`    | Send the prompt                          |

#### Ollama: Important Concepts

- `Model`: A downloaded AI model, such as `qwen3:8b`.
- `Service`: Ollama runs as a background service.
- `Local API`: Ollama listens on `127.0.0.1:11434`.
- `Model storage`: Downloaded models can take significant disk space.

---

### DBeaver Community (`dbeaver`)

#### DBeaver Community: Overview

DBeaver Community is a graphical database client for working with many database systems.

#### DBeaver Community: Why it's useful

- Connects to many databases from one application.
- Useful for browsing tables and running SQL queries.
- Friendlier than command-line database clients for visual inspection.
- Complements tools such as `mysql`, `psql`, and `aql`.

#### DBeaver Community: Installation and Verification Commands

```sh
# Adds the DBeaver signing key
sudo wget -q -O - https://dbeaver.io/debs/dbeaver.gpg.key \
  | sudo gpg --dearmor -o /usr/share/keyrings/dbeaver.gpg.key

# Adds the DBeaver Community repository
echo "deb [signed-by=/usr/share/keyrings/dbeaver.gpg.key] https://dbeaver.io/debs/dbeaver-ce /" \
  | sudo tee /etc/apt/sources.list.d/dbeaver.list

# Installs and verifies DBeaver Community
sudo apt update
sudo apt install -y dbeaver-ce
dbeaver-ce --version

# Opens DBeaver
dbeaver
```

Use `dbeaver -nosplash` if DBeaver crashes in `gtk_widget_realize()` while handling the splash screen.

#### DBeaver Community: Simple Examples

```sh
# Shows the installed DBeaver version
dbeaver-ce --version

# Opens DBeaver
dbeaver

# Opens DBeaver without the splash screen
dbeaver -nosplash
```

#### DBeaver Community: Essential Keystrokes

DBeaver is interactive:

| Key            | Action                            |
| -------------- | --------------------------------- |
| `Ctrl + Enter` | Execute the current SQL statement |
| `Ctrl + S`     | Save script                       |
| `Ctrl + O`     | Open file                         |
| `Ctrl + F`     | Search                            |

#### DBeaver Community: Important Concepts

- `Connection`: Saved details for a database server.
- `Driver`: Software DBeaver uses to connect to a database type.
- `SQL editor`: Where you write and run queries.
- `Splash workaround`: Use `-nosplash` if launch crashes around the splash screen.

---

### Studio 3T Community Edition (`studio-3t`)

#### Studio 3T Community Edition: Overview

Studio 3T Community Edition is a graphical client for MongoDB.

#### Studio 3T Community Edition: Why it's useful

- Makes browsing MongoDB databases easier.
- Useful for viewing collections and documents.
- Friendlier than using only the MongoDB shell for inspection.

#### Studio 3T Community Edition: Installation and Verification Commands

Request a download link from the [Studio 3T download page](https://robomongo.org/download.php).

Once you receive the download link by email and download the archive:

```sh
cd ~/Downloads
tar -xvzf studio-3t-community-edition-linux-x64.tar.gz
./studio-3t-community-edition-linux-x64.sh
```

#### Studio 3T Community Edition: Simple Examples

```sh
# Moves to your Downloads folder
cd ~/Downloads

# Extracts the downloaded archive
tar -xvzf studio-3t-community-edition-linux-x64.tar.gz

# Runs the installer
./studio-3t-community-edition-linux-x64.sh
```

#### Studio 3T Community Edition: Essential Keystrokes

Studio 3T is a graphical application:

| Key        | Action                                           |
| ---------- | ------------------------------------------------ |
| `Ctrl + O` | Open a file or dialog where supported            |
| `Ctrl + F` | Search                                           |
| `Ctrl + S` | Save the current editor or query where supported |

#### Studio 3T Community Edition: Important Concepts

- `MongoDB`: A document database that stores JSON-like documents.
- `Collection`: Similar to a table in relational databases.
- `Connection`: Saved MongoDB server details.
- `Archive install`: The downloaded `.tar.gz` file must be extracted before running the installer.

---

### Okular PDF Reader (`okular`)

#### Okular PDF Reader: Overview

Okular is a PDF and document reader for Linux.

#### Okular PDF Reader: Why it's useful

- Opens PDFs and many other document formats.
- Supports search, annotations, and page navigation.
- Lightweight and practical for reading technical documents.

#### Okular PDF Reader: Installation and Verification Commands

```sh
sudo apt install okular
okular --version
```

#### Okular PDF Reader: Simple Examples

```sh
# Shows the installed Okular version
okular --version

# Opens Okular
okular

# Opens a specific PDF file
okular file.pdf
```

#### Okular PDF Reader: Essential Keystrokes

Okular is interactive:

| Key         | Action        |
| ----------- | ------------- |
| `Ctrl + O`  | Open document |
| `Ctrl + F`  | Search        |
| `Page Down` | Next page     |
| `Page Up`   | Previous page |
| `Ctrl + Q`  | Quit          |

#### Okular PDF Reader: Important Concepts

- `PDF reader`: Okular is for viewing documents, not editing source files.
- `Annotations`: You can highlight and add notes to supported documents.
- `Search`: `Ctrl + F` is the fastest way to find text in long PDFs.

---

### Golang (`go`)

#### Golang: Overview

Go, also called Golang, is a programming language commonly used for backend services, command-line tools, and infrastructure software.

#### Golang: Why it's useful

- Produces fast standalone binaries.
- Common for cloud, DevOps, and backend tools.
- Includes built-in tooling for formatting, testing, and modules.

#### Golang: Installation and Verification Commands

```sh
sudo apt install golang-go
go version
```

#### Golang: Simple Examples

```sh
# Shows the installed Go version
go version

# Runs a Go program
go run main.go

# Runs tests in the current module
go test ./...

# Installs the Go language server
go install golang.org/x/tools/gopls@latest
```

#### Golang: Essential Keystrokes

`go` is non-interactive, so it has no essential keystrokes.

#### Golang: Important Concepts

- `Module`: A Go project is usually managed with a `go.mod` file.
- `go run`: Builds and runs a program immediately.
- `go install`: Installs Go command-line tools.
- `$HOME/go/bin`: A common location for installed Go binaries.

---

### Timeshift (`timeshift`)

#### Timeshift: Overview

Timeshift creates system snapshots that can help restore your Ubuntu system after a bad update or configuration mistake.

#### Timeshift: Why it's useful

- Useful before major system changes.
- Can restore system files to an earlier state.
- Helps recover from broken packages or desktop configuration issues.
- Complements backups, but does not replace backing up personal files.

#### Timeshift: Installation and Verification Commands

```sh
sudo apt install timeshift
timeshift --version
```

#### Timeshift: Simple Examples

```sh
# Shows the installed Timeshift version
timeshift --version

# Lists available snapshots
sudo timeshift --list

# Creates a snapshot using configured settings
sudo timeshift --create

# Starts the restore workflow
sudo timeshift --restore
```

#### Timeshift: Important Concepts

- `Snapshot`: A saved system state.
- `System restore`: Restores system files, not necessarily all personal files.
- `Before risky changes`: Create a snapshot before driver, desktop, or package changes.

---

### GNOME Tweaks (`gnome-tweaks`)

#### GNOME Tweaks: Overview

GNOME Tweaks is a graphical tool for changing GNOME desktop appearance and behavior settings that are not always available in the normal Settings application.

#### GNOME Tweaks: Why it's useful

- Makes font, theme, icon, and window settings easier to adjust.
- Useful for desktop customization.
- Works well with font and icon theme packages.

#### GNOME Tweaks: Installation and Verification Commands

```sh
# Installs GNOME Tweaks
sudo apt install gnome-tweaks
gnome-tweaks --version

# Installs and verifies Inter
sudo apt install fonts-inter
fc-list | grep -i "Inter"

# Installs and verifies JetBrains Mono
sudo apt install fonts-jetbrains-mono
fc-list | grep -i "JetBrains"
```

Open **Tweaks → Fonts** and set:

```text
Interface Text     → Inter Regular 11.5
Document Text      → Inter Regular 11.5
Monospaced Text    → JetBrains Mono 11.5
Hinting            → Full
```

Open **Tweaks** and set the appearance options:

```text
Cursor              → Adwaita (default)
Icons               → Yaru-blue-dark
Legacy Applications → Adwaita-dark
```

Tutorials:

- [GNOME Tweaks tutorial 1](https://www.youtube.com/watch?v=gCbeyd0ITsQ)
- [GNOME Tweaks tutorial 2](https://www.youtube.com/watch?v=uUg6OEswN9E)

#### GNOME Tweaks: Simple Examples

```sh
# Opens GNOME Tweaks
gnome-tweaks

# Shows the installed version
gnome-tweaks --version

# Checks whether Inter fonts are installed
fc-list | grep -i "Inter"

# Checks whether JetBrains Mono fonts are installed
fc-list | grep -i "JetBrains"
```

#### GNOME Tweaks: Important Concepts

- `Fonts`: Interface, document, and monospace fonts affect different parts of the desktop.
- `Hinting`: `Full` can make text sharper on some screens.
- `Themes and icons`: Installed packages become selectable in Tweaks.

---

### Extension Manager (`gnome-shell-extension-manager`)

#### Extension Manager: Overview

Extension Manager installs and manages GNOME Shell extensions.

#### Extension Manager: Why it's useful

- Adds desktop features not included by default.
- Lets you install, enable, disable, and update GNOME extensions.
- Useful for dock behavior, blur effects, tiling, clipboard history, and system monitors.

#### Extension Manager: Installation and Verification Commands

```sh
sudo apt install gnome-shell-extension-manager
dpkg -l gnome-shell-extension-manager
```

Popular Extensions to Install and Enable:

```text
1. Blur my Shell
2. Dash2Dock Animated
3. Search Light (Optional)
4. Add to Desktop (Optional)
5. Forge (Optional)
6. GNOME Fuzzy App Search
7. Kiwi (is not apple)
8. Clipboard Indicator (by Tudmotu)
9. Kiwi Menu
10. Compiz alike magic lamp effect
11. System Monitor (by naimur900) / Vitals
12. Tiling Shell
13. Caffeine
14. GSConnect
15. Bluetooth battery indicator
16. Just Perfection (Optional)
```

System Extensions to Disable:

```text
Ubuntu Dock
```

#### Extension Manager: Simple Examples

```sh
# Verifies that Extension Manager is installed
dpkg -l gnome-shell-extension-manager

# Opens Extension Manager
gnome-shell-extension-manager

# Lists installed GNOME extensions
gnome-extensions list
```

#### Extension Manager: Important Concepts

- `Extension`: A plugin that changes GNOME Shell behavior.
- `Enable/disable`: Turn extensions on only when you need them.
- `Compatibility`: Extensions may depend on your GNOME version.

---

### Software Properties GTK (`software-properties-gtk`)

#### Software Properties GTK: Overview

Software Properties GTK provides Ubuntu's graphical software sources and additional drivers settings.

#### Software Properties GTK: Why it's useful

- Helps manage software sources and drivers.
- Useful for installing recommended GPU, Wi-Fi, or hardware drivers.
- A graphical alternative to some `ubuntu-drivers` commands.

#### Software Properties GTK: Installation and Verification Commands

```sh
sudo apt install software-properties-gtk
```

Search for **Additional Drivers**, open the application, and install any additional drivers available for your system.

Command-line equivalent:

```sh
sudo ubuntu-drivers list
sudo ubuntu-drivers install
```

#### Software Properties GTK: Simple Examples

```sh
# Opens Software Properties
software-properties-gtk

# Lists recommended drivers
sudo ubuntu-drivers list

# Installs recommended drivers
sudo ubuntu-drivers install
```

#### Software Properties GTK: Important Concepts

- `Additional Drivers`: Ubuntu's tool for proprietary or recommended hardware drivers.
- `Drivers`: Needed for some GPUs, Wi-Fi cards, and other hardware.
- `GUI vs CLI`: `ubuntu-drivers` performs the same kind of task from the terminal.

---

### Media Codecs (`ubuntu-restricted-extras`)

#### Media Codecs: Overview

`ubuntu-restricted-extras` installs common media codecs and related packages that Ubuntu may not include by default.

#### Media Codecs: Why it's useful

- Helps play more audio and video formats.
- Useful after a fresh Ubuntu installation.
- Improves compatibility with common media files.

#### Media Codecs: Installation and Verification Commands

```sh
sudo apt install ubuntu-restricted-extras
```

#### Media Codecs: Simple Examples

```sh
# Installs common restricted media packages
sudo apt install ubuntu-restricted-extras

# Shows package details
apt show ubuntu-restricted-extras

# Checks whether the package is installed
dpkg -l ubuntu-restricted-extras
```

#### Media Codecs: Essential Keystrokes

Package installation may show license prompts:

| Key          | Action                           |
| ------------ | -------------------------------- |
| `Tab`        | Move between prompt buttons      |
| `Enter`      | Confirm the selected option      |
| `Arrow keys` | Navigate options where available |

#### Media Codecs: Important Concepts

- `Restricted extras`: Packages not always installed by default because of licensing.
- `Codec`: Software needed to decode audio and video formats.
- `Fresh install`: This is often installed early in a new Ubuntu setup.

---

### VLC (`vlc`)

#### VLC: Overview

VLC is a media player that supports many audio and video formats.

#### VLC: Why it's useful

- Plays most common media files.
- Useful when the default video player cannot open a file.
- Supports subtitles, streams, playlists, and many formats.

#### VLC: Installation and Verification Commands

```sh
sudo apt install vlc
vlc --version
```

#### VLC: Simple Examples

```sh
# Shows the installed VLC version
vlc --version

# Opens VLC
vlc

# Plays a video file
vlc video.mp4
```

#### VLC: Essential Keystrokes

VLC is interactive:

| Key        | Action            |
| ---------- | ----------------- |
| `Space`    | Play or pause     |
| `F`        | Toggle fullscreen |
| `M`        | Mute              |
| `Ctrl + O` | Open file         |
| `Ctrl + Q` | Quit              |

#### VLC: Important Concepts

- `Media player`: VLC is for playing audio and video files.
- `Codecs`: VLC includes broad format support.
- `Subtitles`: VLC can load subtitle files such as `.srt`.

---

### Firewall (`ufw`, `gufw`)

#### Firewall: Overview

UFW is Ubuntu's uncomplicated firewall. GUFW is a graphical interface for managing it.

#### Firewall: Why it's useful

- Helps control inbound network connections.
- Simple enough for everyday desktop use.
- Provides a graphical interface through the Firewall application.
- Useful for allowing specific applications such as GSConnect.

#### Firewall: Installation and Verification Commands

```sh
sudo apt install gufw
ufw --version

# Enables the firewall
sudo ufw enable

# Shows active firewall rules
sudo ufw status verbose
```

You can also search for **Firewall** and enable it through the GUFW graphical interface.

For the GSConnect extension:

```sh
sudo ufw allow 1714:1764/udp
sudo ufw allow 1714:1764/tcp
sudo ufw reload
```

For torrent clients, enable their ports manually through the Firewall application or with UFW rules.

#### Firewall: Simple Examples

```sh
# Shows firewall status and rules
sudo ufw status verbose

# Enables the firewall
sudo ufw enable

# Allows a TCP port range
sudo ufw allow 1714:1764/tcp

# Reloads firewall rules
sudo ufw reload
```

#### Firewall: Important Concepts

- `UFW`: Command-line firewall tool.
- `GUFW`: Graphical interface for UFW.
- `Port`: A numbered network entry point used by applications.
- `Allow rules`: Needed when a trusted application must receive incoming connections.

---

### TLP (`tlp`)

#### TLP: Overview

TLP is a Linux power-saving tool, especially useful for laptops.

#### TLP: Why it's useful

- Helps improve battery life.
- Applies power-saving settings automatically.
- Useful on laptops without much manual tuning.

#### TLP: Installation and Verification Commands

```sh
sudo apt install tlp tlp-rdw
systemctl status tlp
```

If the service is stopped, start it:

```sh
sudo systemctl start tlp
```

Enable it to start automatically at boot:

```sh
sudo systemctl enable tlp
```

Start the service now and enable it at boot:

```sh
sudo systemctl enable --now tlp
```

Check TLP status:

```sh
sudo tlp-stat -s
```

#### TLP: Simple Examples

```sh
# Shows whether the TLP service is running
systemctl status tlp

# Starts TLP now and enables it at boot
sudo systemctl enable --now tlp

# Shows TLP status information
sudo tlp-stat -s
```

#### TLP: Essential Keystrokes

`tlp` and `systemctl` are non-interactive command-line utilities, so they have no essential keystrokes.

#### TLP: Important Concepts

- `Service`: TLP runs in the background.
- `Enable vs start`: `enable` starts the service at boot; `start` starts it now.
- `Battery tuning`: TLP applies power profiles automatically.

---

### Thermald (`thermald`)

#### Thermald: Overview

Thermald is a Linux service that helps manage CPU temperature and thermal behavior.

#### Thermald: Why it's useful

- Helps reduce overheating.
- Can improve thermal stability on laptops.
- Runs automatically in the background after installation.

#### Thermald: Installation and Verification Commands

```sh
sudo apt install thermald
sudo systemctl enable --now thermald
```

#### Thermald: Simple Examples

```sh
# Shows whether Thermald is running
systemctl status thermald

# Starts Thermald now and enables it at boot
sudo systemctl enable --now thermald

# Restarts the service
sudo systemctl restart thermald
```

#### Thermald: Essential Keystrokes

`thermald` is managed through non-interactive command-line utilities, so it has no essential keystrokes.

#### Thermald: Important Concepts

- `Thermal management`: Helps control heat by applying system thermal policies.
- `Service`: Thermald runs in the background.
- `Enable at boot`: `enable --now` starts the service now and on future boots.

---

### Synaptic (`synaptic`)

#### Synaptic: Overview

Synaptic is a graphical package manager for native Ubuntu `.deb` packages.

#### Synaptic: Why it's useful

- Gives detailed control over package installation and removal.
- Better for native `.deb` package management than the App Center.
- Useful for searching package names, versions, and dependencies.
- Complements `apt`.

#### Synaptic: Installation and Verification Commands

```sh
sudo apt install synaptic
```

#### Synaptic: App Center vs Synaptic

```text
App Center:
- Installs applications.
- Good for Snap packages, but less suitable for detailed .deb package management.
- Snap packages are more isolated and can use more storage or start more slowly.

Synaptic:
- Gives detailed control over native .deb packages.
- Lets you search, install, remove, and manage packages.
```

#### Synaptic: Simple Examples

```sh
# Opens Synaptic

synaptic

# Installs Synaptic
sudo apt install synaptic

# Searches for a package from the terminal
sudo apt search package-name
```

#### Synaptic: Essential Keystrokes

Synaptic is interactive:

| Key        | Action                        |
| ---------- | ----------------------------- |
| `Ctrl + F` | Search packages               |
| `Ctrl + R` | Reload package information    |
| `Ctrl + P` | Apply marked changes          |
| `Esc`      | Close dialogs where supported |

#### Synaptic: Important Concepts

- `.deb package`: Native Debian and Ubuntu package format.
- `Snap`: A separate application package format that is often larger and more isolated.
- `Package manager`: A tool used to install, remove, and update software.
- `Synaptic vs apt`: Synaptic is a graphical package manager; `apt` is terminal-based.

---

### Preload (`preload`)

#### Preload: Recommendation

This tool is only recommended for low-performance or older systems.

#### Preload: Overview

Preload watches which applications you use often and tries to keep useful parts ready in RAM.

#### Preload: Why it's useful

- Can make frequently used applications open faster on older HDD-based systems.
- Works automatically after installation.
- Usually not recommended on newer SSD systems because gains are small and it uses RAM, CPU, and disk activity.

#### Preload: Installation and Verification Commands

Install and check the service:

```sh
sudo apt install preload
systemctl status preload
```

Remove Preload:

```sh
sudo apt remove preload
sudo apt purge preload
sudo apt autoremove
systemctl status preload
```

#### Preload: Simple Examples

```sh
# Shows whether Preload is running
systemctl status preload

# Installs Preload
sudo apt install preload

# Removes Preload and its generated configuration files
sudo apt purge preload
```

#### Preload: Essential Keystrokes

`preload` is managed through non-interactive command-line utilities, so it has no essential keystrokes.

#### Preload: Important Concepts

- `HDD vs SSD`: Preload is more useful on older hard drives than modern SSDs.
- `RAM usage`: Preload uses memory to speed up application startup.
- `Service`: It runs in the background after installation.

---

### Papirus Icon Theme

#### Papirus Icon Theme: Overview

Papirus is a popular icon theme for Linux desktops.

#### Papirus Icon Theme: Why it's useful

- Gives Ubuntu a cleaner, more customized icon style.
- Works with GNOME Tweaks.
- Easy to install from Ubuntu packages.

#### Papirus Icon Theme: Installation and Verification Commands

```sh
sudo apt install papirus-icon-theme
```

Open GNOME Tweaks and change the icon theme to `Papirus`.

#### Papirus Icon Theme: Simple Examples

```sh
# Installs the Papirus icon theme
sudo apt install papirus-icon-theme

# Opens GNOME Tweaks so you can select Papirus
gnome-tweaks

# Checks whether Papirus icon folders are installed
ls /usr/share/icons | grep -i papirus
```

#### Papirus Icon Theme: Important Concepts

- `Icon theme`: Controls how application and system icons look.
- `GNOME Tweaks`: The easiest place to switch icon themes.
- `System icon folder`: Themes are usually stored under `/usr/share/icons`.

---

### BleachBit (`bleachbit`)

#### BleachBit: Overview

BleachBit is a cleanup tool for removing caches, temporary files, and other unnecessary data.

#### BleachBit: Why it's useful

- Frees disk space.
- Helps clean browser and application caches.
- Useful for occasional system cleanup.

#### BleachBit: Installation and Verification Commands

```sh
sudo apt install bleachbit
bleachbit --version
```

#### BleachBit: Simple Examples

```sh
# Opens BleachBit as a normal user
bleachbit

# Opens BleachBit with administrator access
sudo bleachbit

# Shows the installed version
bleachbit --version
```

#### BleachBit: Important Concepts

- `Cache`: Temporary files that applications can recreate later.
- `Preview first`: Review what will be deleted before cleaning.
- `Normal vs root cleanup`: Use normal mode for user files; use administrator mode carefully.

---

### XAMPP (`lampp`)

#### XAMPP: Overview

XAMPP is a local web-development stack that includes Apache, MariaDB, PHP, and related tools.

#### XAMPP: Why it's useful

- A quick way to run PHP/MySQL-style projects locally.
- Includes Apache and phpMyAdmin.
- Useful for learning or testing traditional web applications.

#### XAMPP: Installation and Verification Commands

Download the Linux installer from the official [Apache Friends download page](https://www.apachefriends.org/download.html).

You can also download a specific version with `wget`:

```sh
wget https://www.apachefriends.org/xampp-files/8.2.12/xampp-linux-x64-8.2.12-0-installer.run
```

Check the official website for the latest version before downloading.

Make the installer executable:

```sh
cd ~/Downloads
chmod +x xampp-linux-x64-*-installer.run
```

Run the graphical installer:

```sh
sudo ./xampp-linux-x64-*-installer.run
```

For a terminal-only installation:

```sh
sudo ./xampp-linux-x64-*-installer.run --mode text
```

Start XAMPP and check its status:

```sh
sudo /opt/lampp/lampp start
sudo /opt/lampp/lampp status
```

Open these addresses in your browser to verify the installation:

```text
http://localhost
http://localhost/phpmyadmin
```

Manage XAMPP services:

```sh
sudo /opt/lampp/lampp start
sudo /opt/lampp/lampp stop
sudo /opt/lampp/lampp restart
```

Create a local web project:

```sh
sudo mkdir /opt/lampp/htdocs/myproject
```

Then open:

```text
http://localhost/myproject
```

If Apache does not start, another web server may already be using port `80`:

```sh
sudo systemctl stop apache2
sudo systemctl stop nginx
sudo /opt/lampp/lampp restart
```

Quick setup summary:

```sh
cd ~/Downloads
chmod +x xampp-linux-x64-*-installer.run
sudo ./xampp-linux-x64-*-installer.run
sudo /opt/lampp/lampp start
```

Then open:

```text
http://localhost
```

#### XAMPP: Simple Examples

```sh
# Starts XAMPP services
sudo /opt/lampp/lampp start

# Shows XAMPP service status
sudo /opt/lampp/lampp status

# Stops XAMPP services
sudo /opt/lampp/lampp stop

# Creates a local web project folder
sudo mkdir /opt/lampp/htdocs/myproject
```

#### XAMPP: Enable Error Display in PHP

If PHP executes a file but shows a blank screen even when there is a syntax or runtime error, PHP may be configured to suppress error messages.

**How to Enable Error Display**

- Locate your `php.ini` file.

  You can find the loaded configuration file with:

  ```bash
  php --ini
  ```

  Look for the line:

  ```bash
  Loaded Configuration File: /path/to/php.ini
  ```

  Example:

  ```bash
  Configuration File (php.ini) Path: /opt/lampp/etc
  Loaded Configuration File:         /opt/lampp/etc/php.ini
  Scan for additional .ini files in: (none)
  Additional .ini files parsed:      (none)
  ```

- Open the file `/opt/lampp/etc/php.ini` in a text editor.
- Enable error reporting and display errors.

  Find these lines and changed them to:

  ```ini
  error_reporting = E_ALL
  display_errors = On
  display_startup_errors = On
  ```

- Save the file.
- Restart your PHP/web server so the configuration takes effect.
- Verify the configuration

  ```bash
  php -i | grep -E "display_errors|display_startup_errors|error_reporting"
  ```

  You can also create a temporary PHP file:

  ```php
  <?php
    phpinfo();
  ```

  Open it in your browser and check the values for display_errors and error_reporting.

**File: `php.ini (Line 445-490)`**

```ini
; Common Values:
;   E_ALL (Show all errors, warnings and notices including coding standards.)
;   E_ALL & ~E_NOTICE  (Show all errors, except for notices)
;   E_ALL & ~E_NOTICE & ~E_STRICT  (Show all errors, except for notices and coding standards warnings.)
;   E_COMPILE_ERROR|E_RECOVERABLE_ERROR|E_ERROR|E_CORE_ERROR  (Show only errors)
; Default Value: E_ALL
; Development Value: E_ALL
; Production Value: E_ALL & ~E_DEPRECATED & ~E_STRICT
; http://php.net/error-reporting
error_reporting=E_ALL

; This directive controls whether or not and where PHP will output errors,
; notices and warnings too. Error output is very useful during development, but
; it could be very dangerous in production environments. Depending on the code
; which is triggering the error, sensitive information could potentially leak
; out of your application such as database usernames and passwords or worse.
; For production environments, we recommend logging errors rather than
; sending them to STDOUT.
; Possible Values:
;   Off = Do not display any errors
;   stderr = Display errors to STDERR (affects only CGI/CLI binaries!)
;   On or stdout = Display errors to STDOUT
; Default Value: On
; Development Value: On
; Production Value: Off
; http://php.net/display-errors
display_errors=On

; The display of errors which occur during PHP's startup sequence are handled
; separately from display_errors. We strongly recommend you set this to 'off'
; for production servers to avoid leaking configuration details.
; Default Value: On
; Development Value: On
; Production Value: Off
; http://php.net/display-startup-errors
display_startup_errors=On

; Besides displaying errors, PHP can also log errors to locations such as a
; server-specific log, STDERR, or a location specified by the error_log
; directive found below. While errors should not be displayed on productions
; servers they should still be monitored and logging is a great way to do that.
; Default Value: Off
; Development Value: On
; Production Value: On
; http://php.net/log-errors
log_errors=On
```

**When Should You Turn `display_errors` Off**

Turn display_errors off in production environments. This prevents PHP errors, warnings, and potentially sensitive information such as file paths, database details, or configuration information from being exposed to website visitors.

Instead, send errors to a log file and inspect the logs when debugging.

**Development Configuration**

```ini
error_reporting = E_ALL
display_errors = On
display_startup_errors = On
log_errors = On
```

**Production Configuration**

```ini
error_reporting = E_ALL & ~E_DEPRECATED & ~E_STRICT
display_errors = Off
display_startup_errors = Off
log_errors = On
```

#### XAMPP: Essential Keystrokes

The XAMPP installer is interactive:

| Key        | Action                         |
| ---------- | ------------------------------ |
| `Tab`      | Move between installer buttons |
| `Enter`    | Confirm the selected option    |
| `Ctrl + C` | Cancel the terminal command    |

#### XAMPP: Important Concepts

- `Apache`: The web server used by XAMPP.
- `phpMyAdmin`: A browser-based database administration tool.
- `htdocs`: The folder from which local web projects are served.
- `Port 80`: The default web-server port; conflicts can prevent Apache from starting.

---

### Neovim (`nvim`)

#### Neovim: Overview

Neovim is a modern, extensible terminal text editor based on Vim. It can be used for everything from editing configuration files to full software development.

#### Neovim: Why it's useful

- Edits files directly from the terminal.
- Fast and keyboard-driven.
- Provides powerful search, navigation, and editing.
- Highly customizable through Lua configuration.
- Works well for programming with plugins and language servers.

#### Neovim: Installation and Verification Commands

```sh
sudo apt update
sudo apt install -y neovim
nvim --version
```

Open Neovim and run `:checkhealth` to check optional providers and configuration:

```sh
nvim
```

#### Neovim: Simple Examples

```sh
# Opens or creates a file
nvim file.txt

# Edits your Zsh configuration
nvim ~/.zshrc

# Opens the current directory
nvim .
```

#### Neovim: Essential Keystrokes

| Key        | Action                       |
| ---------- | ---------------------------- |
| `i`        | Enter insert mode            |
| `Esc`      | Return to normal mode        |
| `:w`       | Save                         |
| `:q`       | Quit                         |
| `:wq`      | Save and quit                |
| `:q!`      | Quit without saving          |
| `dd`       | Delete the current line      |
| `yy`       | Copy the current line        |
| `p`        | Paste after the cursor       |
| `u`        | Undo                         |
| `Ctrl + R` | Redo                         |
| `/text`    | Search for text              |
| `n`        | Go to the next search result |
| `gg`       | Go to the top of the file    |
| `G`        | Go to the bottom of the file |
| `0`        | Go to the start of the line  |
| `$`        | Go to the end of the line    |

#### Neovim: Important Concepts

- `Modes`: Neovim has different modes; normal mode is for commands and navigation, while insert mode is for typing.
- `Configuration`: Your main configuration directory is usually `~/.config/nvim/`.
- `:checkhealth`: Reports whether optional Neovim features and integrations are correctly configured.

---

### eza (`eza`)

#### eza: Overview

`eza` is a modern replacement for `ls` with improved colors, icons, Git integration, and more readable output.

#### eza: Why it's useful

- Makes directory listings easier to read.
- Shows file types with colors and optional icons.
- Can display Git status.
- Provides more readable formatting than traditional `ls`.

#### eza: Installation and Verification Commands

On Ubuntu, eza's project provides an APT repository:

```sh
sudo apt update
sudo apt install -y eza
eza --version
```

#### eza: Simple Examples

```sh
# Lists files
eza

# Shows a detailed listing
eza -l

# Includes hidden files
eza -a

# Shows a detailed listing including hidden files
eza -la

# Shows Git status
eza -l --git

# Displays a directory tree
eza --tree

# Displays file icons; a Nerd Font is recommended
eza --icons
```

#### eza: Useful Aliases

```sh
alias ls='eza'
alias ll='eza -la'
alias tree='eza --tree'
```

#### eza: Essential Keystrokes

`eza` is non-interactive, so it has no essential keystrokes.

#### eza: Important Concepts

- `Icons`: Use a Nerd Font, such as MesloLGS NF, for the best icon display.
- `Git integration`: `--git` adds Git status information to listings inside repositories.
- `Aliases`: Add aliases to `~/.zshrc` and run `source ~/.zshrc` to make them available immediately.

---

### fd (`fdfind`)

#### fd: Overview

`fd` is a fast, user-friendly replacement for `find` for locating files and directories.

#### fd: Why it's useful

- Uses simpler syntax than `find`.
- Searches quickly.
- Respects `.gitignore` by default.
- Finds files and directories by name, type, or pattern.
- Works well with tools such as `fzf` and Neovim.

#### fd: Installation and Verification Commands

On Ubuntu, the package is named `fd-find` and the installed command is usually `fdfind`:

```sh
sudo apt update
sudo apt install -y fd-find
fdfind --version
```

Optional: create a short `f` alias for `fdfind`:

```sh
echo "alias f='fdfind'" >> ~/.zshrc
echo "alias fd='fdfind'" >> ~/.zshrc
source ~/.zshrc
f --version
fd --version
```

#### fd: Simple Examples

```sh
# Finds names containing "config"
fd config

# Finds package.json files
fd package.json

# Finds directories containing "projects"
fd -t d projects

# Finds Markdown files
fd -t f '\.md$'

# Searches from a specific directory
fd config ~/Documents

# Includes hidden files
fd -H config

# Includes hidden files and ignores .gitignore rules
fd -HI config
```

#### fd: Essential Keystrokes

`fd` is non-interactive, so it has no essential keystrokes.

#### fd: Important Concepts

- `fd vs fdfind`: On Ubuntu, use `fdfind` unless you create the optional `fd` symlink or created an alias.
- `Regular expressions`: `fd` treats patterns as regular expressions by default.
- `Hidden and ignored files`: `-H` includes hidden files; `-I` also ignores `.gitignore` rules.

---

### Ripgrep (`rg`)

#### Ripgrep: Overview

`rg`, also called ripgrep, is a fast text-search tool designed for directories and source-code projects.

#### Ripgrep: Why it's useful

- Searches entire projects quickly.
- Respects `.gitignore` by default.
- Supports regular expressions.
- Useful for finding where text, functions, variables, or configuration values are used.

#### Ripgrep: Installation and Verification Commands

```sh
sudo apt update
sudo apt install -y ripgrep
rg --version
```

#### Ripgrep: Simple Examples

```sh
# Searches for text in the current directory
rg "hello"

# Searches for TODO
rg "TODO"

# Searches a specific directory
rg "TODO" ~/projects

# Searches only Python files
rg "import" -t py

# Includes hidden files
rg -u "secret"

# Includes hidden files and files ignored by Git
rg -uu "secret"

# Shows filenames containing TODO
rg -l "TODO"

# Searches case-insensitively
rg -i "hello"
```

#### Ripgrep: Essential Keystrokes

`rg` is non-interactive, so it has no essential keystrokes.

#### Ripgrep: Important Concepts

- `Git ignore rules`: By default, ripgrep skips files ignored by `.gitignore`.
- `-u`, `-uu`, and `-uuu`: `-u` includes hidden files; `-uu` also includes ignored files; `-uuu` additionally searches binary files.
- `Regular expressions`: Search patterns are regular expressions by default.

---

### lf (`lf`)

#### lf: Overview

`lf` is a terminal-based file manager for navigating directories and managing files with the keyboard.

#### lf: Why it's useful

- Lets you browse directories without repeatedly typing `cd` and `ls`.
- Supports keyboard-driven copying, moving, renaming, and opening files.
- Fast and lightweight.
- Can be configured so your shell changes to the directory you were viewing when you quit.

#### lf: Installation and Verification Commands

```sh
sudo apt update
sudo apt install -y lf
lf -version
```

Optional: add this function to `~/.zshrc` to make your shell enter the last directory viewed in `lf`:

```sh
lfcd() {
  local tmp
  local dir

  tmp="$(mktemp)"
  lf -last-dir-path="$tmp" "$@"

  if [ -f "$tmp" ]; then
    dir="$(cat "$tmp")"
    rm -f "$tmp"
    [ -d "$dir" ] && cd "$dir"
  fi
}
```

Reload Zsh, then use `lfcd`:

```sh
source ~/.zshrc
lfcd
```

#### lf: Simple Examples

```sh
# Starts lf in the current directory
lf

# Starts lf in your Downloads folder
lf ~/Downloads

# Shows lf help
lf -help

# Shows lf documentation
lf -doc
```

#### lf: Essential Keystrokes

| Key                     | Action                                    |
| ----------------------- | ----------------------------------------- |
| `j` / `Down`            | Move down                                 |
| `k` / `Up`              | Move up                                   |
| `h` / `Left`            | Go to the parent directory                |
| `l` / `Right` / `Enter` | Open a file or enter a directory          |
| `q`                     | Quit                                      |
| `Space`                 | Select or unselect a file                 |
| `y`                     | Copy the selected file or files           |
| `d`                     | Cut the selected file or files for moving |
| `p`                     | Paste copied or cut files                 |
| `r`                     | Rename the current file                   |
| `/`                     | Search forward                            |
| `?`                     | Search backward                           |
| `:`                     | Enter an `lf` command                     |
| `f`                     | Find by filename                          |
| `g`                     | Go to a location/menu                     |

#### lf: Important Concepts

- `Copy vs cut`: `y` copies files; `d` marks files to be moved; `p` performs the copy or move.
- `Delete`: File deletion is deliberately not assigned to a default key. Configure it only after you understand the deletion command.
- `Shell wrapper`: Use `lfcd` if you want your shell to change into the last directory you viewed.
- `Configuration`: lf configuration files are commonly stored under `~/.config/lf/`.

#### lf: Navigation Pattern

```text
        k / Up
           ^
h / Left [you] l / Right
           v
        j / Down
```

Think of it as:

```text
h = back
l = enter
j = down
k = up
```

---

### eza, lf, nvim, fd, rg and bat

#### eza, lf, nvim, fd, rg and bat: How These Tools Fit Together

These tools are not really competing with each other. They complement each other.

```text
                 Your Terminal
                      |
        --------------+--------------
        |             |             |
      eza            lf           nvim
    list files    navigate       edit files
        |             |             |
        --------------+--------------
                      |
              --------+--------
              |               |
             fd              rg
         find files       find text
              |               |
              --------+--------
                      |
                     bat
                  read files
```

#### eza, lf, nvim, fd, rg and bat: Typical Workflow

```bash
eza -la              # What is here?
fd package.json      # Where is the file?
rg "DATABASE_URL"    # Where is this used?
bat config.py        # Inspect the file
nvim config.py       # Edit it
lf                   # Browse/manage files visually
```

### eza, lf, nvim, fd, rg and bat: Modern Unix Toolkit Mental Model

| Tool   | Think of it as  | Main job       |
| ------ | --------------- | -------------- |
| `eza`  | `ls`            | List files     |
| `bat`  | `cat`           | Read files     |
| `fd`   | `find`          | Find files     |
| `rg`   | `grep`          | Find text      |
| `lf`   | Finder/Explorer | Navigate files |
| `nvim` | VS Code/editor  | Edit files     |

Once you get comfortable with these six tools, a huge amount of everyday terminal work becomes much faster.

---

### net-tools (`net-tools`)

#### net-tools: Overview

`net-tools` is a package that provides classic Linux networking utilities, including `netstat`, `ifconfig`, `route`, `arp`, and `nameif`.

It is useful when working with older networking commands or software that depends on `netstat`.

#### net-tools: Why it's useful

- Provides the `netstat` command for viewing network connections and listening ports.
- Helps diagnose port conflicts and active network services.
- Includes utilities for viewing network interfaces and routing information.
- Required by some applications and scripts that still rely on legacy networking tools.
- Resolves the `netstat: command not found` error when starting XAMPP on Linux.

#### net-tools: Installation and Verification Commands

On Debian, Ubuntu, and other APT-based Linux distributions:

```sh
sudo apt update
sudo apt install net-tools
netstat --version
```

When starting XAMPP on Linux with:

```sh
sudo /opt/lampp/lampp start
```

you may see an error similar to:

```text
netstat: command not found
```

This occurs because XAMPP uses `netstat` to check services and ports, but `netstat` is not installed by default on many modern Linux distributions.

Install `net-tools` to resolve the issue:

```sh
sudo apt install net-tools
```

Then start XAMPP again:

```sh
sudo /opt/lampp/lampp start
```

#### net-tools: Simple Examples

```sh
# Shows all active network connections and listening ports
netstat -a

# Shows TCP connections and listening TCP ports
netstat -at

# Shows UDP connections and listening UDP ports
netstat -au

# Shows listening ports with their process ID and program name
sudo netstat -tulpn

# Checks whether Apache is using port 80
sudo netstat -tulpn | grep :80

# Checks whether MySQL is using port 3306
sudo netstat -tulpn | grep :3306

# Displays network interface details
ifconfig

# Displays the system routing table
route -n
```

#### net-tools: Essential Keystrokes

`net-tools` commands are non-interactive, so they have no essential keystrokes.

#### net-tools: Important Concepts

- `netstat`: Displays active network connections, listening ports, and routing information.
- `Listening ports`: Services such as Apache and MySQL listen on specific ports for incoming connections.
- `-t`: Displays TCP connections.
- `-u`: Displays UDP connections.
- `-l`: Displays only listening sockets.
- `-p`: Displays the process ID and program name associated with a connection or port.
- `-n`: Displays addresses and port numbers numerically instead of resolving names.
- `sudo`: Required with `-p` to view process details for all users.
- `ifconfig`: Displays or configures network interfaces; it is included in `net-tools`.
- `route`: Displays the network routing table; it is also included in `net-tools`.
- `net-tools` vs `iproute2`: `net-tools` provides older commands such as `netstat` and `ifconfig`, while modern Linux systems commonly use `ss` and `ip`.
- `netstat` vs `ss`: `ss` is the modern replacement for `netstat`, but XAMPP may still require `netstat`, making `net-tools` necessary.

---
