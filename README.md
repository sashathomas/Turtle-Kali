# Turtle-Kali Installation and Usage Guide

Last year at Purdue, many of you saw my customized version of Kali. I've had to redo this installation and configuration process a bunch of times so I decided to automate it. I hope this guide is useful for anyone who is curious or wants to try my custom Kali setup! 

<img width="1840" alt="Screenshot 2023-12-10 at 3 22 49 PM" src="https://gist.github.com/assets/59403796/ce28c4ea-f44a-4f61-9322-34f81683934f">

## Overview

The biggest change this script introduces is installing i3 as a window manager. i3 is a dynamic tiling window manager, meaning it will automatically arrange the windows to occupy the whole screen in a non-overlapping way. i3 has a number of advantages over standard desktop environments (in my opinion):

1. i3 is lightweight. It's easy to run in a VM and doesn't take up a lot of resources. 
2. i3 is fast. Opening the terminal, switching workspaces, resizing the window, changing the layout, and anything else you might want to do is just one shortcut away. 
3. i3 is flexible. All the shortcuts can be changed to fit your liking. The status bar is fully customizable. Individual workspaces can be assigned to specific applications (I personally have a dedicated workspace for Firefox and Burp). Almost all of i3's behavior and feel can be customized. 

In addition to a different desktop environment, this script will also install a custom `zsh` config and a different terminal emulator called `alacritty`. The `zsh` config, besides adding some emojis and color to the terminal prompt, will also grep for your `tun0` interface IP and add it to the prompt. For me, this is really nice because I always forget my IP when doing HackTheBox or other CTFs where I'm on a VPN. `alacritty` is a fast and lightweight terminal emulator written in Rust. 

There are a couple more tweeks to the UI, `zsh`, and `alacritty`, such as different fonts, changes to the file manager `thunar`, and so on. If you don't like these changes, you can absolutely substitute them for something you like more!  
## Installation
0. Consider creating a snapshot or backup of your current VM in case you want to revert. 
1. Clone the repo at: https://github.com/sashathomas/Turtle-Kali
2. Run `bash install.sh`.
3. After the script is finished, run `sudo reboot now`.
4. Before you log in, click the triple bar menu at the top right, and select `i3`.
5. After you log in, open a terminal by pressing: `ctrl+enter`

## Usage

### Resolution
You may need to fix the resolution. The current settings match my laptop but might not match your setup. To change the resolution, there are two files you can edit:

1. `~/.Xresources`

This changes the DPI, which makes GUI programs like Firefox and Burp scale up. 

2. `~/.config/i3/config`

Line 3: `exec "xrandr --output Virtual-1 --primary --mode 2880x1800 --pos 0x0 --rotate normal --output Virtual-2 --off --output Virtual-3 --off --output Virtual-4 --off --output Virtual-5 --off --output Virtual-6 --off --output Virtual-7 --off --output Virtual-8 --off"`

This changes the actual resolution. Replace `--mode 2880x1800` with the resolution you want. You can also test different resolutions out by running `arandr`. 

### i3
The default MOD key is `ctrl`. The basics are: 

1. `MOD+enter`: Open/split terminal
2. `MOD+[num]`: Switch workspaces
3. `MOD+d`: Open application 

Here's a reference with all the shortcuts: https://i3wm.org/docs/refcard.html
