---
layout: post
title:  "Ubuntu in the color of your choice"
date:   2020-04-30 10:15:56 +0200
categories: Ubuntu 20.04 Gnome 3.36 Yaru Theme Color 
---

[![Yaru-Anycolor](/assets/Yaru-Anycolor-compare.png)](/assets/Yaru-Anycolor-compare.png)

I really like Ubuntu's [Yaru theme](https://github.com/ubuntu/yaru). Compared to most other linux desktop environments / themes it just looks, well..., good. It uses colors consistently, has a beautiful icon set and uses proportions / forms that look and feel right. There's only one problem, and it's the colors it uses. Ubuntu's branding uses orange, purple and aubergine as accent colors which makes it easily recognizable and sets it apart from other distos / operating systems. I can't help it, I just don't like looking at these colors all day long. Especially the bright orange is really present in the UI and distracts from other things that should get my attention (e.g. orange warnings or red errors).

It seems like I'm not the only one. There's a fork of the Yaru theme named [Yaru-Colors](https://github.com/Jannomag/Yaru-Colors) that provides a selection of alternative colors and has 100+ stars on GitHub. I've been using the blue variant for almost a year now and really enjoyed the calmness of it. It really helps me focus on what's imporant and also looks way cooler in my opinion.

I wanted to upgrade to Ubuntu 20.04 a couple of days ago but remembered that this would require an updated Yaru-Blue theme. As of now, the Yaru-Colors fork hasn't been updated to match the current Yaru upstream design and open issues show that it doesn't play nicely with 20.04 currently. I thought about upgrading the Yaru-Colors repo, but didn't really know where to start and how to pull the upstream changes in. Yaru-Colors' repository layout looks different from the upstream version, so upgrading without additional information would've been a challenging task. This is where I had the idea for Yaru-Anycolor:

## Yaru-Anycolor

Yaru-Anycolor is a basically just a small python script that takes the upstream Yaru theme and replaces its accent colors by color codes of your choice. This approach has a couple of advantages. The script changes as little as possible in the original theme which should make it relatively robust to future changes to the upstream theme. Using a script also allows one to specify any colors instead of providing a fixed set of color themes. Finally, this approach also means that the original build system of the yaru theme can be reused.

The [Yaru-Anycolor](https://github.com/fkohlgrueber/yaru-anycolor) project is available on Github. The repository contains step-by-step instructions on how to install a colored theme and a couple of screenshots.

The screenshot below shows how Yaru-Anycolor looks using the default color (which, as you might have guessed, is my favorite blue variant):

[![Yaru-Anycolor-Blue](https://raw.githubusercontent.com/fkohlgrueber/yaru-anycolor/master/docs/YaruBlue-Theme.png)](https://raw.githubusercontent.com/fkohlgrueber/yaru-anycolor/master/docs/YaruBlue-Theme.png)


