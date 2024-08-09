---
title: Using a Package Manager
---
# What are Package Managers?

Package Managers are tools that handle installing software for you.

A package manager sits on your computer and can download, install, and update software for you. 
## Repositories
In order for package managers to work, they need to know about the software. This is their primary advantage. Instead of software being just... out on various websites, somewhere, somebody controls a centralized and public database.

These databases are usually public and community managed. While Apple's App Store can be thought of as a package manager for iPhones, the database of what software is in their repository of tools is heavily controlled and moderated by Apple.

Software repositories also have systems for moderation and control, usually in a decentralized and community-run way. The repository for [Winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/), a package manager for Windows, allows [community submissions](https://learn.microsoft.com/en-us/windows/package-manager/package/repository).

## Trusting The Tools
The submissions have an automated verification to see that the software adheres to various [product and content policies](https://learn.microsoft.com/en-us/windows/package-manager/package/windows-package-manager-policies).
One of these steps is that the installer is run through malware and other threat detection tools. If something malicious does manage to slip through the automatic checks, the public nature and community overview of the packages means that it can get resolved very quickly.

All in all, it is usually a more pleasant, safer, and less spammy way to install software than to download it from various websites.

> The backup software "SyncBackFree" is great. It's [website and download page](https://www.2brightsparks.com/download-syncbackfree.html) is not. It's much easier to type "winget install 2BrightSparks.SyncBackFree" into a terminal than it is to deal with that website, and it's *not* full of malicious advertisements or fake download buttons.

Accidentally downloading viruses  is a serious problem. Package Managers handle this threat in a much more rigorous way than, say, [hoping that google results are trustworthy](https://www.reddit.com/r/blender/comments/vvrxko/warning_fake_blender_website_paying_for_priority/). 

## Ease of Updating
By far the best reason to use a package manager is that it makes it **way** easier to update software than otherwise. Every single software individually checking for updates and asking to be updated? gross! Running one command? Easy!

# Package Managers
> While multiple package managers will be listed per operating system, it is advisable to use just one. I.E.: If something says to "install via scoop", check to see if winget has it first.

## Windows

### Winget
[Winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/) is an official and well-supported package manager by Microsoft, and it is recommended. It is already installed on most modern Windows machines.

If you prefer, there is even a [GUI](https://www.marticliment.com/unigetui/) for it.

### Others
Besides WinGet, you may see [Chocolatey](https://chocolatey.org/) and [scoop](https://scoop.sh/) are popular.. 

## Mac

### Homebrew
[Homebrew](https://brew.sh/) calls itself "The Missing Package Manager for macOS (or Linux)", and it's overwhelming popularity among Mac developers earns the title. 

### Others
The only serious competitor to Homebrew is [MacPorts](https://www.macports.org/), which has been around since 2002!

## Linux
Many different linux distributions come with their own package manager. Arch (pacman), Ubuntu (apt or apt-get), Fedora (DNF or Yum), OpenSUSE (Zypper), Gentoo (portage), all have their own systems. They are not always mutually incompatible, depending on the roots of the distribution or software.

Thankfully, this means that while "Package Managers on Linux" is complex, "Package Managers for Your Linux Machine" is simple. You can generally just use the ones that come with the system.

## What about Package Managers for Programming Languages?
If you are using python, go, rust, javascript/node, or other popular programming languages, you might be able to install software (that was written in this language) via that communities' package manager.

Generally, these tools are for _internal_ use. Using another software packages as a building block for writing your own in the same language. [NuGet](https://learn.microsoft.com/en-us/nuget/what-is-nuget) for C#/.NET is great, but you don't use it to install software, you use it to create software.

There are exceptions. Python ([PIP](https://packaging.python.org/en/latest/guides/tool-recommendations/#installing-packages)), Rust ([Cargo](https://doc.rust-lang.org/cargo/getting-started/first-steps.html)), and Javascript's NodeJS ([NPM](https://www.npmjs.com/)) will let you install software that you might just run on your computer.

> There are technical reasons for this involving how and when programming languages get compiled/run, and how the respective runtimes work.

