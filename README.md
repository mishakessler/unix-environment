# Unix Environment Setup <!-- omit in toc -->

**An extremely thorough guide to setting up a powerful software engineering Unix environment.**

> ⚠️ **This guide is written for non-M1 chip Unix computers, and tested on macOS Big Sur**. If you are on an M1 chip MacBook, please consult the [M1 Version]; if you are on Linux, please consult my [Linux Version]. If you are unsure, please consult my [Guide to Determining Your Environment].

<br>

## TABLE OF CONTENTS <!-- omit in toc -->

- [OVERVIEW](#overview)
  - [Some Tips Before You Start](#some-tips-before-you-start)
- [INSTALLATIONS](#installations)
  - [Your Core Package Manager](#your-core-package-manager)
    - [Homebrew](#homebrew)
  - [Your Terminal Shell](#your-terminal-shell)
    - [Zsh](#zsh)
    - [Oh-My-Zsh](#oh-my-zsh)
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
  - [Your Browser Environment](#your-browser-environment)
    - [Google Chrome Extensions](#google-chrome-extensions)
  - [Your Coding Environment](#your-coding-environment)
    - [VSCode Settings](#vscode-settings)
    - [VSCode Extensions](#vscode-extensions)
    - [VSCode Themes](#vscode-themes)

<br>

## OVERVIEW

This guide covers the core technologies your computer will need for a **powerful** software engineering and web dev environment. The guide includes "detail" drop-downs like the following:

<details><summary>Click Me!</summary><br>

I will use these dropdowns to keep the guide relatively clean and focused on installation steps, but to still include important context about what is happening with each download. 

Emoji Key: 

- 🔍 Learn More
- ⚠️ Warnings
- ❗ Errors
- ✅ Successes

</details><br>

### Some Tips Before You Start

Finally, before you start, I heavily recommend three things:

#### Familiarize Yourself With The Tools of the Trade <!-- omit in toc -->

If you're _brand_ new to software engineering, or if you aren't particularly comfortable with your computer, including the command line interface, please review the guide to [Tools of the Trade]. Even for experienced engineers, **focusing on these more basic tools can significantly level up one's coding prowess and productivity**.

#### Practice Researching Anything & Everything <!-- omit in toc -->

With the vast complexities of software engineering, it is simply impossible to know and memorize **everything** you will need on a daily basis. Get used to researching and confirming small details that will make a huge differences. 

In this spirit, open up the [Glossary] in a new tab so you can reference it at any time during setup. If you're unsure or confused about the technologies or concepts I reference, just hop over to the Glossary and look it up.

#### Be Thorough & Methodical <!-- omit in toc -->

Finally, and perhaps most importantly, you **must** use methodical, step-by-step attention to detail. This is integral to a career in software engineering, but especially when setting up your environment, **doing these steps out of order can have long-lasting, code-breaking implications**.

<br>

Let's dive in!

<br>

## INSTALLATIONS

This guide will be using **terminal** for all installations. Let's open terminal and get started!

<br>

### Your Core Package Manager

<img align="right" width="300" src="https://imgur.com/CDY3Eeu.png">

#### Homebrew 

[Brew Website] | [Brew Documentation] | [Brew GitHub] | [Brew Issue Tickets]

Homebrew is a _package manager_ for macOS. Most core software you will need for the Unix dev environment is installed via Homebrew.

<details><summary>Learn More 🔎</summary><br>

Homebrew is a package manager, meaning, it provides software packages and can handle safe updating and uninstalling as needed. Homebrew is considered essential for core software which macOS doesn't ship natively, but which are necessary for your work. 

Homebrew packages are divided into **formulae**, **casks**, **taps**, or **bottles**, which . For the time being, we'll only be using formulae and casks.

Homebrew utilizes the `brew` command in terminal. 

</details><br>

**STEP 1.** Copy and paste the following script into your terminal.

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**STEP 2.** Enter your password. 

> ⚠️ As you type, your cursor will not move and your typing won't be visible– simply type your full password and hit enter.

**STEP 3.** Once finished, review the response you received.

> ⚠️ While Homebrew is still installing, you won't be able to see your bash command line prompt. 

✅ **SUCCESS.** If Homebrew was successfully installed, you will see a large message that begins with `==> Installation successful!`.

❗ **ERROR.** It's highly unlikely that this will error out.

<br>

🔼 [back to top] 

<br>

### Your Terminal Shell

#### Zsh

#### Oh-My-Zsh

<br>

🔼 [back to top] 

<br>

### Your Version Control Manager

#### Git

#### Git Configurations

##### Git Security Token <!-- omit in toc -->

##### Git Author Information <!-- omit in toc -->

##### Git Branch Naming Convention <!-- omit in toc -->

##### Git Rebase Convention <!-- omit in toc -->

<br>

🔼 [back to top] 

<br>

### Your Frontend Scripting Languages

#### NVM

#### Node.js

#### NPM

#### JavaScript Add-Ons

##### TypeScript <!-- omit in toc -->

<br>

🔼 [back to top] 

<br>

### Your Database Management Programs

#### PostgreSQL

#### MongoDB

<br>

🔼 [back to top] 

<br>

### Your Backend Scripting Languages

#### Rbenv

#### Ruby

#### Ruby Gems

##### Pry <!-- omit in toc -->

##### Rspec <!-- omit in toc -->

##### Rails <!-- omit in toc -->

<br>

🔼 [back to top] 

<br>

### Your GUI Applications

#### Google Chrome

#### Visual Studio Code

#### PostMan

<br>

🔼 [back to top] 

<br>

***

## CUSTOMIZATIONS

### Your macOS Environment

#### macOS Plugins

##### Magnet <!-- omit in toc -->

<br>

🔼 [back to top] 

<br>

### Your Browser Environment

#### Google Chrome Extensions

##### React Dev Tools <!-- omit in toc -->

##### Color Picker <!-- omit in toc -->

##### JSON Viewer <!-- omit in toc -->

<br>

🔼 [back to top] 

<br>

### Your Coding Environment

#### VSCode Settings

#### VSCode Extensions

#### VSCode Themes

##### Color Theme <!-- omit in toc -->

##### Icon Theme <!-- omit in toc -->

<br>

🔼 [back to top] 

<br>

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

[back to top]: #table-of-contents