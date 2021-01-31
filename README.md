# Unix Environment Setup <!-- omit in toc -->

**An extremely thorough guide to setting up a powerful software engineering Unix environment.**

<br>

> ⚠️ **This guide is written for non-M1 chip Unix computers, and tested on macOS Big Sur**. If you are on an M1 chip MacBook, please consult the [M1 Version] (Coming Soon); if you are on Linux, please consult my [Linux Version] (Coming Soon). If you are unsure, please consult my [Guide to Determining Your Environment] (Coming Soon).

<br>

## TABLE OF CONTENTS <!-- omit in toc -->

- [OVERVIEW](#overview)
  - [Some Tips Before You Start](#some-tips-before-you-start)
- [INSTALLATIONS](#installations)
  - [Your Core Package Manager](#your-core-package-manager)
    - [**Homebrew**](#homebrew)
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
    - [Oh My Zsh Plugins](#oh-my-zsh-plugins)
    - [Oh My Zsh Themes](#oh-my-zsh-themes)
  - [Your Coding Environment](#your-coding-environment)
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

### Your Core Package Manager

<img align="right" width="300" src="https://imgur.com/CDY3Eeu.png">

#### **Homebrew**

[Brew Website] | [Brew Documentation] | [Brew GitHub] | [Brew Issue Tickets]

Homebrew is a _package manager_ for macOS. Most core software you will need for the Unix dev environment is installed via Homebrew.

<details><summary>🔎 Learn More</summary><br>

Homebrew is a _package manager_, meaning, it provides software packages and can handle safe updating and uninstalling as needed. Homebrew is considered essential for core software which macOS doesn't ship natively, but which are necessary for your work.

Homebrew packages are divided into **formulae**, **casks**, **taps**, or **bottles**; for the time being, we'll only be using formulae and casks.

_Formulae_ installations handle softwares that you'll only interact with through the terminal– meaning, software that doesn't have an "App" interface in the GUI, such as Node. _Cask_ installations, on the other hand, are softwares that you interact with in your GUI, such as the Chrome internet browser.

In terminal, Homebrew utilizes the `brew install <formula name>` command; if you're installing a cask, you use the `brew install --cask <cask name>` command and cask flag.

</details>

<details><summary>📋 View Installation Steps</summary><br>

**STEP 1.** Copy and paste the following script into your terminal.

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**STEP 2.** Enter your password.

> ⚠️ Warning: As you type, your cursor will not move and your typing won't be visible– simply type your full password and hit enter.

**STEP 3.** Once finished, review the response you received.

> ⚠️ Warning: While Homebrew is still installing, you won't be able to see your bash command line prompt.

**SUCCESS.** If Homebrew was successfully installed, you will see a large message that begins with `==> Installation successful!`.

</details>

<details><summary>✅ Verify Installation</summary><br>

To confirm, run the command `brew -v`. The output should state `Homebrew 2.7.7` or higher.

</details>

<details><summary>❗ Common Errors</summary><br>

It's highly unlikely that this will error out. Even when it's already installed, Homebrew will take the opportunity to install a clean version and update any outdated dependencies.

</details>

<br>

[back to top ⤴️]

***

<br>

### Your Terminal Shell

#### Zsh

[Zsh Website] | [Zsh Documentation] | [Zsh Users Project]

Zsh, pronounced by the acronym Z-S-H, is a Unix _shell_ and command interpreter for shell scripting. It serves as a replacement for _Bash_, the default Unix Terminal shell.

<details><summary>📋 View Installation Steps</summary><br>

**STEP 1.** Copy and paste the following Homebrew command in your terminal.

```shell
brew install zsh
```

**SUCCESS.** 

</details>

<details><summary>✅ Verify Installation</summary><br>

To confirm, run the command `zsh -v`. The output should be `zsh 5.8` or higher.

</details>

<details><summary>❗ Common Errors</summary><br>

It's highly unlikely that this will error out– if Zsh is already installed, Homebrew will take the opportunity to upgrade any Brew packages before stating:

```shell
Warning: zsh <version> is already installed and up-to-date.
To reinstall <version>, run:
  brew reinstall zsh
```

</details>

#### Oh My Zsh

[Oh My Zsh Website] | [Oh My Zsh Documentation] | [Oh My Zsh Github] | [Oh My Zsh Issue Tickets]

Oh My Zsh is a community-driven framework for the Zsh shell. It helps us customize and configure our Z shell.

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

#### Oh My Zsh Plugins

#### Oh My Zsh Themes

<br>

[back to top ⤴️]

***

<br>

### Your Coding Environment

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

[Name Website]: 
[Name Documentation]: 
[Name GitHub]: 
[Name Issue Tickets]: 

[back to top ⤴️]: #table-of-contents-