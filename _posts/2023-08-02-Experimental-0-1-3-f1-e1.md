---
layout: post
title: Thymus experimental release 0.1.3.f1.e2
---

Here it is, the first post about the experimental stuff! Below there are some development notes.

## Library updates

With every experimental release, I will try to synchronize versions of all dependencies to their current stable. With that release, Textual is aligned to 0.33.0. Please, note that the 0.32.0 version has breaking changes. Also, for some features (see below) Thymus requires Netmiko now. With all of that, I set a Python version more precisely in the package requirements, it is 3.8.1 now.

    For every new experimental release pay attention to the requirements.txt file!

## NX-OS support

Several changes were required to adapt the IOS context module to support the NX-OS platform. The structure of the latter is the pretty same as the former but has some nitty differences. For example, an NX-OS context does not support a promiscuous setting, because this platform's configuration always comes without the end keyword at its bottom.

## From network

Using Thymus on a daily basis, I must admit it's not always convenient to connect to network devices, save their configuration to files, and open them later in Thymus. Sometimes we don't have a choice, but for the opposite case, I totally reduced an intermediate step, and Thymus can fetch a configuration by an SSH or Telnet connection. This feature requires Netmiko to be installed.

![from_network]({{ site.baseurl }}/images/thymus_from_network.png)

In the Open dialog window now there are two tabs. By default, the From file tab is shown and it offers you the usual experience. The From network tab has several controls that allow you to set up a connection with a selected network device. You have to choose the platform on the left because it is not automatically deduced. After the connection is established, Thymus fetches a running configuration via this connection, closes the connection, and opens a configuration.

    A fetched configuration is only present in memory! To save it on a disk use the `show | save ...` combination.

## Contains sub-command

Imagine you need to find all VPLS instances or all instances with a specific RT pattern. The `filter` sub-command can show you lines that contain some keywords, but it is absolutely absent of a context. You never know where this line is stored. A wildcard matching can show you some sections by a pattern which is good, but it can't look deeper into these sections.

The new sub-command `contains` recursively searches all pattern matches for sections and finite instructions. For example, `show | contains "instance-type vpls;"` gives you all sections where this pattern lives. Narrowing your pattern gives you a more precise output! And yes, it supports PCRE!

![contains]({{ site.baseurl }}/images/thymus_contains.png)

## QoE

I also pay attention to the quality of the experience. Not so far one of my friends who is totally new to Thymus was surprised by an emptiness of a working screen. Fair enough I must say. As the author, I perfectly understand what to do next, but not every user is also aware of these steps. For that reason after the start, there is help information on a screen. This information contains a list of all commands and their description. You can call this guide by the `help` command at any time.

![help]({{ site.baseurl }}/images/thymus_help.png)

The Left sidebar of a working screen is also slightly modified. Now it shows all sections of a current path. If you start typing something, the Left sidebar will work as usual, but when it's empty, the sections will be shown again.

The `save` sub-command now saves data into a dedicated folder by default. The path is `thymus/saves`. Before that, all files were saved in the root folder which created a lot of mess.

JunOS context's `go` command now is case-insensitive!

There is a new alias for the `filter` sub-command: `grep`.

When the Input field is empty the Up and Down arrow keys now scroll a configuration if it is longer than your screen. This nitty change brings more flexibility to your navigation experience, but the next section brings much more to it!

## Improved keyboard navigation

There are changes to the navigation through the Open dialog and the Working screen. The main goal here is to ease the experience of those users who prefer to use a keyboard rather than a mouse.

Inside the Open dialog there are additional keyboard hotkeys now:

* `p` sets a focus to the platform selection block (the top-left element of the screen).
* `e` sets a focus to the encoding selection block.
* `t` sets a focus to the directory tree.
* `l` moves to a left tab.
* `r` moves to a right tab.

The Working screen was also redesigned. First, all its elements, except the Text and Input fields, are not focusable anymore. So, despite a user still should use `Shift`+`Tab` to escape the Input field, now it sets the focus to the Text field immediately, with no more intermediate elements! When the Text field is focused, it's possible to use either `Tab` or `Shift`+`Tab` to move the focus back to the Input.

As the documentation states the only way to fully display long outputs is to use a mouse wheel. But now the Text field also supports the `n` hotkey which appends data to its tail. So, no more barriers for the keyboard users!

## Screenshots

Yes! Textual has native support for screenshots. Use the `Ctrl`+`p` hotkey. Screenshots are saved into `thymus\saves\screenshots` folder in SVG format.

## Fixed bugs

Platforms that are derived from its predecessor could be compared among themselves. For example, it was possible to compare EOS with IOS, NX-OS with EOS, etc.

For IOS-like platforms the `set spaces` command was too naive, I made it in a hurry. Now, it works as expected.

Lots of fixes for syntax highlighting. This process is endless I believe.


Stay ~~tuna~~tuned!