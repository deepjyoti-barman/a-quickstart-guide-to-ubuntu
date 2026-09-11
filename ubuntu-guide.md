# A Quickstart Guide to Ubuntu

## Table of Contents

- [A Quickstart Guide to Ubuntu](#a-quickstart-guide-to-ubuntu)
  - [Table of Contents](#table-of-contents)
  - [Set Up Ubuntu, Resolve Issues and Tweaks](#set-up-ubuntu-resolve-issues-and-tweaks)
    - [Install the Perfect Terminal Font: MesloLGS NF](#install-the-perfect-terminal-font-meslolgs-nf)
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
    - [Powerlevel10k](#powerlevel10k-p10k)
    - [SDKMan](#sdkman-sdk)
    - [Java](#java-java)
    - [Gradle](#gradle-gradle)
    - [Maven](#maven-mvn)
    - [JMeter](#jmeter-jmeter)
    - [AQL](#aql-aql)
    - [NVM](#nvm-nvm)

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

# This shell snippet configures man to use bat (or Debian/Ubuntu’s batcat) as its pager,
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
alias find='fdfind'
alias f='fdfind'
alias rm='rm -i'
alias cp='cp -i'
alias mv='mv -i'
alias bat='batcat'

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

Make sure `zsh` is your current active shell first:

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

### Powerlevel10k (`p10k`)

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

#### Powerlevel10k: `zsh-autocomplete` Fix

```sh
mkdir -p ~/.local/share/zsh
touch ~/.local/share/zsh/chpwd-recent-dirs
exec zsh
cd /tmp
cd ~
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
