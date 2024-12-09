---
page-title: "How to Configure Gaming Mouse on Linux Using Piper"
url: https://itsfoss.com/piper-configure-gaming-mouse-linux/
date: "2024-08-17 02:19:03"
tags: [a/sw, f/, c/, p/pwf]
about: ["[[Logitech]]","[[linux]]",]
aliases: 
- 
by: Ankush Das
length: 4418
dir: 
---

Replacing Ubuntu With Newer Version in Dual Boot Setup

[![Warp Terminal](https://itsfoss.com/assets/images/warp-terminal.webp)](https://www.warp.dev/?utm_source=its_foss&utm_medium=display&utm_campaign=linux_launch)

Usually, when you [switch from Windows to Linux](https://itsfoss.com/reasons-switch-linux-windows-xp/), you lose access to many [GUI](https://en.wikipedia.org/wiki/Graphical_user_interface?ref=itsfoss.com) (Graphical User Interface) tools that you use to manage gaming peripherals.

You can still enjoy [playing games on Linux](https://itsfoss.com/linux-gaming-guide/), but the ability to configure your mouse is a big deal if you are more than a casual gamer.

*I am looking at you, competitive gamers* 😝

Recently, I came across a handy tool that lets you configure your gaming mouse on Linux. Allow me to share how it works and whether it is worth giving a try.

[![a screenshot of the piper gui](https://itsfoss.com/content/images/wordpress/2020/06/piper-gui.png)](https://itsfoss.com/content/images/wordpress/2020/06/piper-gui.png)

[Piper](https://github.com/libratbag/piper?ref=itsfoss.com) is **an open-source tool** that you can use to configure gaming peripherals on Linux. Technically, Piper is a graphical frontend to the [ratbagd DBus daemon](https://github.com/libratbag/libratbag?ref=itsfoss.com) — but you don’t need to worry about it if you aim to use the GUI only.

In this article, I’ll give you a brief overview as I test it on my [Logitech G502 Hero](https://www.logitechg.com/en-in/products/gaming-mice/g502-hero-gaming-mouse.html?ref=itsfoss.com) gaming mouse.

## Features of Piper

It’s a dead simple tool. You will be able to configure the following features of your gaming mouse with Piper:

-   **Map Buttons**
-   **Control LEDs**
-   **Add Multiple Profiles**
-   **Change** [**DPI**](https://en.wikipedia.org/wiki/Dots_per_inch?ref=itsfoss.com) **(Resolution) and** [**Polling rate**](https://wiki.archlinux.org/index.php/Mouse_polling_rate?ref=itsfoss.com)

Please note that **not all gaming mice work with Piper** at this time. Please check the [list of support devices](https://github.com/libratbag/libratbag/tree/master/data/devices?ref=itsfoss.com) before you set out to install it.

**Here’s how it works and looks:**

### Changing DPI & Polling Rate

[![a screenshot of piper dpi changing screen](https://itsfoss.com/content/images/wordpress/2020/06/piper-dpi.png)](https://itsfoss.com/content/images/wordpress/2020/06/piper-dpi.png)

With Piper, you get to **set different DPI levels** in line with what your mouse supports. It is effortless to fine tune the DPI levels thanks to the provided slider.

Not just limited to the DPI settings, but you can also control the polling rate (or the sensitivity). Of course, depending on your mouse, the option may look different, but you don’t really need to change the sensitivity of your mouse for the most part.

### Configuring Buttons

[![a screenshot showing how to configure gaming mouse buttons in linux with piper](https://itsfoss.com/content/images/wordpress/2020/06/piper-buttons.png)](https://itsfoss.com/content/images/wordpress/2020/06/piper-buttons.png)

This is an essential functionality to have for most users. Especially, if you want to utilize [macros](https://en.wikipedia.org/wiki/Macro_\(computer_science\)?ref=itsfoss.com) or want to change the mapping of your buttons.

As you can observe in the screenshot above, I was able to tweak every button on my gaming mouse, similar to what I could do on [Logitech G HUB](https://www.logitechg.com/en-in/innovation/g-hub.html?ref=itsfoss.com).

I’ve re-mapped the DPI increase/decrease button and replaced it with a macro to dabble between multiple workspaces on Pop!\_OS. You can do something like that for your workflow.

### Controlling RGB Lighting

[![a screenshot of piper led control](https://itsfoss.com/content/images/wordpress/2020/06/piper-led-control.png)](https://itsfoss.com/content/images/wordpress/2020/06/piper-led-control.png)

Well, there’s no use of having RGB lighting if you can’t tweak or control them. With Piper, you can **easily control the LED lights of your gaming mouse** (if your mouse has that functionality). It works pretty well for my **Logitech G502 Hero**.

### Multiple Profiles

You also get the ability to manage multiple profiles to switch from — so you don’t have to fiddle around with the settings regularly.

In case you didn’t know, each profile can have different button mapping, LED settings, and DPI settings.

## Installing Piper On Linux

To get started, you need to ensure that you have [libratbag](https://github.com/libratbag/libratbag?ref=itsfoss.com) installed. Some Linux distributions have it pre-installed, like Pop!\_OS.

For Ubuntu-based distros, you can type in the following command to install it if you didn’t have it already:

```
sudo apt install ratbagd
```

For Debian, Arch, or Fedora, you can follow the [official installation instructions](https://github.com/libratbag/libratbag/wiki/Installation?ref=itsfoss.com).

Once done, you can finally **install Piper by typing the following command** (for Ubuntu-based distros):

```
sudo apt install piper
```

You can get **installation instructions for other Linux distributions** on Piper's [wiki on GitHub](https://github.com/libratbag/piper/wiki/Installation?ref=itsfoss.com).

You can also opt for the [Flatpak package](https://flathub.org/apps/details/org.freedesktop.Piper?ref=itsfoss.com) if using the terminal is not your thing. In case you don’t know how to use Flatpaks, I suggest you refer to our [Flatpak guide](https://itsfoss.com/flatpak-guide/) to know more.

**Suggested Read 📖**

[

Using Flatpak on Ubuntu and Other Linux Distributions \[Complete Guide\]

Flatpak is a universal packaging format from Fedora. Enabling Flatpak will give you access to the easy installation of many Linux applications. Here’s how to use Flatpak in Ubuntu and other Linux distributions.

![](https://itsfoss.com/content/images/size/w256h256/2022/12/android-chrome-192x192.png)It's FOSSAbhishek Prakash

![](https://itsfoss.com/content/images/wordpress/2018/05/use-flatpak-linux.jpeg)

](https://itsfoss.com/flatpak-guide/)

## Wrapping Up

Piper is a fantastic GUI tool to easily configure gaming mice on Linux, just make sure that you have a supported device. You will find many supported devices from **Logitech**, **ASUS**, **Glorious**, **ROCCAT**, and **SteelSeries**.

If you ask me, Piper is the way to go if your gaming mouse manufacturer doesn't officially provide an app to control it on Linux.

*💬 Have you tried Piper yet? Please share your thoughts with me in the comments section below.*

About the author

 [![Ankush Das](https://secure.gravatar.com/avatar/d098097d2a43d2fc1f0d31327f8288a6?s=512&d=mm&r=g)](https://itsfoss.com/author/ankush/)

## [Ankush Das](https://itsfoss.com/author/ankush/)

A passionate technophile who also happens to be a Computer Science graduate. You will usually see cats dancing to the beautiful tunes sung by him.