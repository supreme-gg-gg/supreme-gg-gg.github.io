---
title: Instagram CLI
subtitle: THe ultimate weapon against brainrot
date: 2025-02-15
tags: ["personal-projects"]
---

Ever opened Instagram just to send a quick message, only to find yourself doomscrolling for hours? Introducing the world's first TUI + CLI client for Instagram, putting an end to the brainrot hell and turning it back into a productive social networking tool. **Download from PyPI and star our [GitHub repo](https://github.com/supreme-gg-gg/instagram-cli) (we're got 3k downloads already)!**

```bash
pip install instagram-cli
```

{{< columns >}}
{{< figure link="/img/instagram/home.png">}}
{{< column >}}
{{< figure link="/img/instagram/example.png">}}
{{< endcolumns >}}

<!--more-->

## What does it do

- We transform Instagram from a brainrot hell into productivity tool

- We give back control of social media to the user

- We enable user to do more with less

- We celebrate the art and simplicity of terminal UI

- We preserve the core of social media and protect your attention

> Use Instagram with 100% keyboard control - no mouse clicks or touchscreen taps needed! Perfect for developers and Linux users who love staying on the keyboard

## Installation and Usage

You can install from PyPI, install from source, build using Docker, or build executables. I will not go over any detail here but the full documentation is on our GitHub repository.

Our features include both CLI commands and in-chat TUI commands (like discord bots). The entire application supports fuzzy search and vim syntax.

Here is a list of base commands:

```bash
instagram                                  # display title art
instagram --help                           # view available commands

# Authentication
instagram auth login -u                    # login with username and password
instagram auth logout                      # logout and removes session

# Chat Features
instagram chat start                       # start chat interface
instagram chat search -u <username>        # search and open chat by username
instagram chat search -t <text>           # search and open chat by chat title

# Utility Commands
instagram notify                           # view notifications (inbox, followers, mentions)
instagram schedule ls                      # view scheduled messages
instagram stats --days <last_n_days>       # view usage analytics (default: 14 days)
instagram config --get --set --edit        # manage custom configuration
instagram cleanup -t                       # cleanup media and session cache files
```

Our in-chat TUI commands include view images and videos, replying to messages, scheduling messages, uploading media, opening URLs, **directly rendering and sending LaTeX** and more.

We built this with `curses, typer` and we would like to acknowledge `instagrapi` for reverse engineering the Instagram API.

{{< button url="https://github.com/supreme-gg-gg/instagram-cli/tree/main" >}}Star our repo!{{< /button >}}
