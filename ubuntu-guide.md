# A Quickstart Guide to Ubuntu

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
