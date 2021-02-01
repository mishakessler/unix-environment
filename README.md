# Unix Environment Setup <!-- omit in toc -->

**An extremely thorough guide to setting up a powerful software engineering Unix environment.**

<br>

> ⚠️ **This guide is written for non-M1 chip Unix computers, and tested on macOS Big Sur**. If you are on an M1 chip MacBook, please consult the [M1 Version] (Coming Soon); if you are on Linux, please consult my [Linux Version] (Coming Soon). If you are unsure, please consult my [Guide to Determining Your Environment] (Coming Soon).

<br>

## TABLE OF CONTENTS <!-- omit in toc -->

- [OVERVIEW](#overview)
  - [Some Tips Before You Start](#some-tips-before-you-start)
- [INSTALLATIONS](#installations)
  - [Your Terminal Toolbox](#your-terminal-toolbox)
    - [Command Line Tools](#command-line-tools)
  - [Your Primary Package Manager](#your-primary-package-manager)
    - [Homebrew](#homebrew)
  - [Your Terminal Shell](#your-terminal-shell)
    - [Zsh](#zsh)
    - [Oh My Zsh](#oh-my-zsh)
  - [Your Version Control Manager](#your-version-control-manager)
    - [Git](#git)
    - [Git Configurations](#git-configurations)
  - [Your Frontend Scripting Languages](#your-frontend-scripting-languages)
    - [NVM](#nvm)
    - [Node.js](#nodejs)
    - [NPM](#npm)
    - [JavaScript Add-Ons](#javascript-add-ons)
  - [Your Database Management Programs](#your-database-management-programs)
    - [PostgreSQL](#postgresql)
    - [MongoDB](#mongodb)
  - [Your Backend Scripting Languages](#your-backend-scripting-languages)
    - [Rbenv](#rbenv)
    - [Ruby](#ruby)
    - [Ruby Gems](#ruby-gems)
  - [Your GUI Applications](#your-gui-applications)
    - [Google Chrome](#google-chrome)
    - [Visual Studio Code](#visual-studio-code)
    - [PostMan](#postman)
- [CUSTOMIZATIONS](#customizations)
  - [Your macOS Environment](#your-macos-environment)
    - [macOS Plugins](#macos-plugins)
  - [Your Shell Environment](#your-shell-environment)
    - [Terminal Settings](#terminal-settings)
    - [Zsh Plugins](#zsh-plugins)
      - [Zsh Completions](#zsh-completions)
    - [Oh My Zsh Themes](#oh-my-zsh-themes)
  - [Your Integrated Development Environment](#your-integrated-development-environment)
    - [VSCode Settings](#vscode-settings)
    - [VSCode Extensions](#vscode-extensions)
    - [VSCode Themes](#vscode-themes)
  - [Your Browser Environment](#your-browser-environment)
    - [Google Chrome Extensions](#google-chrome-extensions)

<br>

***

<br>

## OVERVIEW

This guide covers the core technologies your computer will need for a **powerful** software engineering and web dev environment; I'm including "detail" drop-downs like the following:

<details><summary>Click Me!</summary><br>

I will use these dropdowns to keep the guide relatively clean and focused, but to still include important details and context about what is happening with each download; I've used this **emoji key** to help with visual indicators:

- **📋 View Installation Steps** – Self-explanatory.
- **🔎 Learn More** – More information on the software and its purpose.
- **⚠️ Warning** – Warnings to avoid common mistakes.
- **❗ Common Errors** – Common errors and how to resolve them.

</details><br>

<br>

### Some Tips Before You Start

Before you start, I **heavily** recommend three things:

#### 1) Familiarize Yourself With The Tools of the Trade <!-- omit in toc -->

If you're _brand_ new to software engineering, or if you aren't particularly comfortable with your computer, including the command line interface, please review the guide to [Tools of the Trade]. Even for experienced engineers, **focusing on these more basic tools can significantly level up one's coding prowess and productivity**.

#### 2) Practice Researching Anything & Everything <!-- omit in toc -->

With the vast complexities of software engineering, it is simply impossible to know and memorize **everything** you will need on a daily basis. Get used to researching and confirming small details that will make a huge differences. 

In this spirit, open up the [Glossary] in a new tab so you can reference it at any time during setup. If you're unsure or confused about the technologies or concepts I reference, just hop over to the Glossary and look it up.

#### 3) Be Thorough & Methodical <!-- omit in toc -->

Finally, and perhaps most importantly, you **must** use methodical, step-by-step attention to detail. This is integral to a career in software engineering, but especially when setting up your environment, **doing these steps out of order can have long-lasting, code-breaking implications**.

<br>

Let's dive in!

<br>

***
***

<br>

## INSTALLATIONS

This guide will be using **terminal** for all installations. One quick warning:

> **⚠️ Warning**: While installing, **never** use the `sudo` command, unless specifically told to do so. `sudo`, meaning "Super User DO", will install software in a different file/folder location on your hard drive, causing issues in the future.

Let's open terminal and get started!

<br>

***

<br>

### Your Terminal Toolbox

<img align="right" width="300" src="">

#### Command Line Tools

[Command Line Tools Instructions] | [Command Line Tools Downloads] | [Xcode Documentation] | [Xcode Resources]

Xcode is Apple's native Integrated Development Environment, or IDE. We won't be using Xcode, but we _will_ be using a subset of the Xcode app, called the _Command Line Tools_ package.

> ⚠️ Warning: If you have the full Xcode suite installed already, skip to the Verify Installation steps.

<details><summary>🔎 Learn More</summary><br>

At over 12GB, Xcode is a beast of an IDE, and we just don't need to use up that disk space. Instead, we'll use Command Line Tools, which is a smaller package within Xcode. Command Line Tools includes the most commonly used utilities and compilers (_make_, _GNU compiler collection_, _perl_, _git_, etc.), and we will be needing these.

In Terminal, Command Line Tools uses `xcode-select` command prefix.

</details>

<details><summary>📋 View Installation Steps</summary><br>

**STEP 1.** Copy and paste the following script into your terminal.

```shell
xcode-select --install
```

**STEP 2.** Follow the UI prompt to install the Command Line Tools.

</details>

<details><summary>✅ Verify Installation</summary><br>

To confirm installation, run the command `xcode-select -v`. The output should state `xcode-select version 2384` or higher.

To confirm installation location, run the command `xcode-select -p`. The output should state `/Library/Developer/CommandLineTools`.

</details>

<details><summary>❗ Common Errors</summary><br>

If Command Line Tools are already installed, you will receive `xcode-select: error: command line tools are already installed, use "Software Update" to install updates`.

If Command Line Tools is installed at the wrong path, try running the following command to reset the path location.

```shell
xcode-select -r
```

</details>

<br>

[back to top ⤴️]

***

<br>

### Your Primary Package Manager

<img align="right" width="300" src="https://imgur.com/CDY3Eeu.png">

#### Homebrew

[Brew Website] | [Brew Documentation] | [Brew GitHub] | [Brew Issue Tickets]

Homebrew is a _package manager_ for macOS. Most core software you will need for the Unix dev environment is installed via Homebrew.

<details><summary>🔎 Learn More</summary><br>

Homebrew is a _package manager_, meaning, it provides software packages and can handle safe updating and uninstalling as needed. Homebrew is considered essential for core software which macOS doesn't ship natively, but which are necessary for your work.

Homebrew packages are divided into **formulae**, **casks**, **taps**, or **bottles**; for the time being, we'll only be using formulae and casks.

_Formulae_ installations handle softwares that you'll only interact with through the terminal– meaning, software that doesn't have an "App" interface in the GUI, such as Node. _Cask_ installations, on the other hand, are softwares that you interact with in your GUI, such as the Chrome internet browser.

In terminal, Homebrew utilizes the `brew` command prefix.

</details>

<details><summary>📋 View Installation Steps</summary><br>

**STEP 1.** Copy and paste the following script into your terminal.

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**STEP 2.** If prompted, enter your Admin password. (This is the password you use when booting your computer and logging into your user account.)

> ⚠️ Warning: As you type, your cursor will not move and your typing won't be visible– simply type your full password and hit enter.

**STEP 3.** Once finished, review the response you received.

> ⚠️ Warning: While Homebrew is still installing, you won't be able to see your bash command line prompt.

If Homebrew was successfully installed, you will see a large message that begins with `==> Installation successful!`.

</details>

<details><summary>✅ Verify Installation</summary><br>

To confirm, run the command `brew -v`. The output should state `Homebrew 2.7.7` or higher.

If this is not the case, view the next section, _Common Errors_.

</details>

<details><summary>❗ Common Errors</summary><br>

It's highly unlikely that this will error out. Even when it's already installed, Homebrew will take the opportunity to install a clean version and update any outdated dependencies.

</details>

<br>

[back to top ⤴️]

***

<br>

### Your Terminal Shell

<img align="right" width="300" src="https://imgur.com/CDY3Eeu.png">

#### Zsh

[Zsh Website] | [Zsh Documentation] | [Zsh Users Project]

Zsh, pronounced by the acronym Z-S-H, is a Unix _shell_ and command interpreter for shell scripting. It serves as a replacement for _Bash_, the default Unix Terminal shell.
 
<details><summary>📋 View Installation Steps</summary><br>

**STEP 1.** Copy and paste the following Homebrew command in your terminal.

```shell 
brew install zsh
```

If Zsh was successfully installed, you will see a large message that begins with `==> Installation successful!`.

**STEP 2.** Copy and paste the following script to make Zsh your default Terminal shell.

```shell
chsh -s /usr/local/bin/zsh
```

**STEP 3.** If prompted, enter your password.

> ⚠️ Warning: As you type, your cursor will not move and your typing won't be visible– simply type your full password and hit enter.

</details>

<details><summary>✅ Verify Installation</summary><br>

To confirm installation, run the command `zsh -v`. The output should be `zsh 5.8` or higher.

To confirm Zsh has been made your default shell, run `echo $SHELL`. The output should be `bin/zsh`.

If this is not the case, view the next section, _Common Errors_.

</details>

<details><summary>❗ Common Errors</summary><br>

It's highly unlikely that this will error out– if Zsh is already installed, Homebrew will take the opportunity to upgrade any Brew packages before stating:

```shell
Warning: zsh <version> is already installed and up-to-date.
To reinstall <version>, run:
  brew reinstall zsh
```

If running `echo $SHELL` returned `bin/bash`, this means your default shell has not changed. First, try hard quitting your terminal. (Do not simply close the Terminal window. This doesn't quit the application. Use _command + Q_ to quit.) Once it has quit, reopen terminal and re-run `echo $SHELL`. This should fix the issue.

</details>

#### Oh My Zsh

[Oh My Zsh Website] | [Oh My Zsh Documentation] | [Oh My Zsh Github] | [Oh My Zsh Issue Tickets]

Oh My Zsh is a community-driven framework for the Z shell. It helps us customize and configure our Z shell.

<details><summary>📋 View Installation Steps</summary><br>

**STEP 1.** Copy and paste the following command in your terminal.

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

**SUCCESS.**

</details>

<details><summary>✅ Verify Installation</summary><br>

</details>

<details><summary>❗ Common Errors</summary><br>

</details>

<br>

[back to top ⤴️]

***

### Your Version Control Manager

#### Git

[Git Website] | [Git Documentation] | [Git Github]

Git is a free, open-source version control system, meaning, it allows a distributed approach to collaboration on code and built-in tools for avoiding conflicting updates.

#### Git Configurations

##### Git Security Token <!-- omit in toc -->

##### Git Author Information <!-- omit in toc -->

##### Git Branch Naming Convention <!-- omit in toc -->

##### Git Rebase Convention <!-- omit in toc -->

<br>

[back to top ⤴️]

***
### Your Frontend Scripting Languages

#### NVM

#### Node.js

#### NPM

#### JavaScript Add-Ons

##### TypeScript <!-- omit in toc -->

<br>

[back to top ⤴️]

***

<br>

### Your Database Management Programs

#### PostgreSQL

#### MongoDB

<br>

[back to top ⤴️]

***

<br>

### Your Backend Scripting Languages

#### Rbenv

#### Ruby

#### Ruby Gems

##### Pry <!-- omit in toc -->

##### Rspec <!-- omit in toc -->

##### Rails <!-- omit in toc -->

<br>

[back to top ⤴️]

***

<br>

### Your GUI Applications

#### Google Chrome

#### Visual Studio Code

#### PostMan

<br>

[back to top ⤴️]


***
***

<br>

## CUSTOMIZATIONS

<br>

***

<br>

### Your macOS Environment

#### macOS Plugins

##### Magnet <!-- omit in toc -->

<br>

[back to top ⤴️]

***

<br>

### Your Shell Environment

#### Terminal Settings

#### Zsh Plugins

##### Zsh Completions

#### Oh My Zsh Themes

<br>

[back to top ⤴️]

***

<br>

### Your Integrated Development Environment

#### VSCode Settings

#### VSCode Extensions

##### Bracket Pair Colorizer <!-- omit in toc -->

##### Indent Rainbow<!-- omit in toc -->

#### VSCode Themes

##### Color Themes <!-- omit in toc -->

##### Icon Themes <!-- omit in toc -->

<br>

[back to top ⤴️]

***

<br>

### Your Browser Environment

#### Google Chrome Extensions

##### React Dev Tools <!-- omit in toc -->

##### Color Picker <!-- omit in toc -->

##### JSON Viewer <!-- omit in toc -->

<br>

[back to top ⤴️]

***

<!-- Links -->
[Guide to Determining Your Environment]: github.com/mishakessler/determine-your-environment
[Unix Version]: github.com/mishakessler/unix-environment
[M1 Version]: github.com/mishakessler/m1-environment
[Linux Version]: github.com/mishakessler/linux-environment
[Tools of the Trade]: github.com/mishakessler/tools-of-the-trade
[Glossary]: github.com/mishakessler/glossary

[Command Line Tools Instructions]: https://osxdaily.com/2014/02/12/install-command-line-tools-mac-os-x/
[Command Line Tools Downloads]: https://developer.apple.com/download/more/?=command%20line%20tools
[Xcode Documentation]: https://developer.apple.com/documentation/xcode/
[Xcode Resources]: https://developer.apple.com/xcode/resources/

[Brew Website]: https://brew.sh/
[Brew Documentation]: https://docs.brew.sh/
[Brew GitHub]: https://github.com/Homebrew/
[Brew Issue Tickets]: https://github.com/Homebrew/brew/issues

[Zsh Website]: http://zsh.sourceforge.net/
[Zsh Documentation]: http://zsh.sourceforge.net/Doc/Release/zsh_toc.html
[Zsh Users Project]: https://github.com/zsh-users

[Oh My Zsh Website]: https://ohmyz.sh/
[Oh My Zsh Documentation]: https://docs.OhMyZsh.sh/
[Oh My Zsh GitHub]: https://github.com/ohmyzsh/
[Oh My Zsh Issue Tickets]: https://github.com/ohmyzsh/ohmyzsh/issues

[Git Website]: https://git-scm.com/
[Git Documentation]: https://git-scm.com/doc
[Git Github]: https://github.com/git/git



[back to top ⤴️]: #table-of-contents-