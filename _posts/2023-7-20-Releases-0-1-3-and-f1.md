---
layout: post
title: Thymus releases 0.1.3 and 0.1.3-f1
---

Recently a [major](https://github.com/blademd/thymus/releases/tag/v0.1.3-alpha) Thymus update and [the fast fix](https://github.com/blademd/thymus/releases/tag/v0.1.3.f1-alpha) just right after that have been posted. So, I believe, it's time to talk about the project and its development perspectives.

First of all, Thymus is at its alpha stage. I'm steadily increasing testing time, but nevertheless, there are still possible problems. Anyway, I believe the current release is pretty stable, and hypothetical bugs should not crash the app and influence its stability, but never believe a developer! Thymus tested with Python 3.8.5 release, but it should also work with 3.7 and later releases, although it is not tested. Releases under 3.7 do not support. Later I'm going to make a package for PyPI registry. That should facilitate testing the app for a variety of releases.

Thymus is planned as a full-blown editor then just a browser. At this moment of time, Textual, the lib Thymus uses for its UI, does not support text editing capabilities. Textual's developers have plans to release a text editing widget, and I hope, sooner than later it will happen. As soon it happens Thymus also will bring it. I have plans for some interesting features for this.

The next important point is that the project has detailed documentation which you can find on [GitHub's Wiki](https://github.com/blademd/thymus/wiki) pages.

I'm not going to spam with frequent releases. The main branch is pretty stable and won't change often. There is no strict schedule for any type's release, but I suppose a window of one to two months. For every major release, there are possible fixing releases with the f-prefix. For more frequent releases I created the experimental branch. Some features from this branch will shape the next major release, some will be skipped forever. If you want to be more in touch switch to the experimental.

Thymus supports the most popular systems (probably except Huawei) and I'm not going to add others in the nearest time. Now, I want to concentrate on config analysis features. So the next releases will bring some features from this field.

Stay ~~tuna~~tuned!