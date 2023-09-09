---
layout: post
title: Thymus experimental release 0.1.3.f1.e5
---

This time there are some noticeable changes were made. This experimental release is going to be the last one before the upcoming stable. The stable release will be based on this experimental without significant changes bringing better user experience and overall stability.

## Library updates

Textual is updated to __0.36.0__. This build brings nothing new, it's just a matter of being up to date.

_For every new experimental release pay attention to the requirements.txt file!_

## Keyboard navigation (cont.)

Previously, after you opened a file, the Open dialog was immediately hidden in the background and its next appearance had the focus on the same place where you had left it. With a keyboard navigation that means that the focus points on the Input field at the very bottom, where a filename lives. A mouse user probably opens a file with a dedicated button and won't face any issues. But for a keyboard-addicted user, when the Open dialog pops up again and its focus points to any input field, it breaks most of the hotkeys (especially, the `p`, `e`, and `t`). To prevent this issue the focus moves now a step back to the Directory tree field after the Open dialog disappears.

At the Working screen, the `Tab` key now appends a space after every completed keyword, it should save you some time and key-strokes. It does not work every time but only when the auto-completion system is sure that it won't break anything.

The sweetest addition. After you finish typing a keyword or the auto-completion system does it for you, the Left sidebar will show you all the next possible sections. From now you can finally discover what's next to type in. Frankly speaking, I was planning it from the very beginning and even made it at first. But the previous version of it was not satisfying and I got rid of it. It's time for Lannister to pay his debt.

## Context switching

The modal dialog for context switching shows a context name next to its platform type now instead of a path if the name is set by a user. It should facilitate navigation among different contexts.

![context_switching_upd]({{ site.baseurl }}/images/thymus_context_switch_dialog_upd.png)

## Fixes

As usual, some fixes were made. They are too difficult to explain here, but most of them are linked to a revised navigation explained above. Some chores should have been done a long time ago, and now they are.

## Plans

In parallel, I'm working on a config analyzing system which should ease some common network engineering tasks, such as planning, migration, config inspection. This job is long-term, but some preliminary results will be available in upcoming experimental releases. I've started with JunOS (again), because I have deeper understanding of this system comparing to the other systems.

Another concern I have is a network scraping library. At the moment, Thymus leans on Netmiko. I decided to use it because of its battle-proveness and continuous support. Netmiko is a great tool that works well on many platforms, including Windows. But its powerfulness raises some side-effects. There are too many features and dependencies in it for such a small task that Thymus completes. I'd love to find something more lightweight for that. The second concern is that Netmiko is an async-less library. I have to wrap its calls with the threading, which has some limitations. Upcoming stable releases will use Netmiko until I find a more suitable solution. I've discovered two neat libraries: Scrapli and NetDev. The latter is lightweight and async-full, but was completely abandoned several years ago :( The former is alive and well-done, it is also async-full, but I can't name it lightweight. There is also no official support for Windows. Let's see what the future brings us, I'm in a centimeter (inch, for any poor soul who does not use the metric system) from developing my own solution (probably, based on a corpse of NetDev).

Textual developers don't stay at the same spot and they promise that the most expected (well, at least by me) widget -- TextArea -- is coming soon. That means I will interrupt all current Thymus-related tasks and start adopting this widget into it which gives us a powerful config editor. As I said previously, there are several nice features in a gift box for this occasion :)

Stay ~~tuna~~tuned!