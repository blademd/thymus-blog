---
layout: post
title: Thymus experimental release 0.1.3.f1.e4
---

Some minor changes were brought, and I'm hurrying to share them with you.

## Library updates

Textual is updated to __0.35.1__. This build brings nothing new, it's just a matter of being up to date.

_For every new experimental release pay attention to the requirements.txt file!_

## Keyboard navigation (cont.)

I'm constantly searching for a better solution for keyboard navigation. This time I changed the `Up` and `Down` arrow keys' behavior when the Enhanced Tab mode is activated. Now it does not move a cursor over a list of choices in the Left sidebar. Moving a cursor didn't make any sense actually, now it moves a screen of the Text field independent of the content of the Input field.

## Night mode

I've noticed that the Night mode's setting hadn't been preserved across the App runs. From this moment, there is a global setting `night_mode` in the `settings.json`. Any changes for the mode inside Thymus are also saved in the file and will be active at the next run.

## Fixes

Notorious case insensitive navigation drained much blood. There are again several fixes on that. Also, some overall stability fixes were made.

Stay ~~tuna~~tuned!