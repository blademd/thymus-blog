---
layout: post
title: Thymus experimental release 0.1.3.f1.e3
---

Not so long after the first post about experimental features there is a new one.

## Library updates

Textual is updated to __0.34.0__. This build brings nothing new, it's just a matter of being up to date.

_For every new experimental release pay attention to the requirements.txt file!_

## Enhanced Tab

For the Working screen moving a focus between the Text and the Input fields can be considered as tricky. From now, when the Input field is empty you can use `Tab` to move the focus to the Text field. However, when something is in this field, `Tab` works as usual (i.e., automatically completes an input).

Previously, when in the Left sidebar there were several elements (at least two), `Tab` replaced a part of a user's input to the sidebar's highlighted value. The first option in the Left sidebar is highlighted by default, and, by moving the highlighting by the `Down` arrow key, a user can select the desired one. Actually, I can't name this logic broken, it is by design.
Nevertheless, I added a new global setting `sidebar_strict_on_tab` which is enabled by default. Now, if there are two or more options in the Left sidebar, `Tab` completes an input to the most common beginning part among all elements of the sidebar. For example, if a user's input is "r" and there are two options in the sidebar, "routing-options" and "routing-instances", `Tab` completes the "r" to the "routing-". After that, the user must decide which char is the next one and insert it.

## IOS's heuristics

As described in the documentation, IOS-like platforms have two heuristics algorithms, one is basic and is enabled by default, another is more advanced and is disabled by default (but I'm pretty sure the latter deserves to be turned on forever). There is option to switch on and off the advanced mode, and now I added an option to do the same with the basic algorithm. This option is named as `base_heuristics`. When you switches it off, the parser won't aggregate interfaces and route-maps into accessible sections.

Stay ~~tuna~~tuned!