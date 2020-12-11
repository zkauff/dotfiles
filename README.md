# i3-configurations
The various configuration files I use for my personal i3 wm setup on my Linux machine. 
Core packages I use are 
- `i3-wm` for core window manager behavior
- `xorg-xrdb` for use of `.Xresources` in customization
- `i3status` for status bar within i3
- `urxvt` for terminal


## Making changes take effect
After making any of the changes that follow in this document, certain steps must first be taken to apply the changes.
1. After modifying any files in `~/.xcolors/` or `~/.Xresources`, you must run 
```
xrdb ~/.Xresources
```
2. After changing any file, including `~/.config/i3/config` and `~/.config/i3/.i3status.conf`, the hotkeys corresponding to the `restart` command in the i3 configuration file must be run.
My configuation file is as follows, so I need to execute ALT+Shift+r to restart i3 and ensure all changes (whether to i3 config or Xresources) reload.
```
~/.config/i3/config
...
# restart i3 inplace (preserves your layout/session, can be used to upgrade i3)
bindsym $mod+Shift+r restart
```

## Color scheme management
I keep a directory of colorschemes at `~/.xcolors/`. The color scheme files are as follows:

```
~/.xcolors/default
#define FOREGROUND #6dced1
#define BACKGROUND #100c1f
//light purple
#define COLOR0  #8b6dd1
#define COLOR10 #8b6dd1
//light teal
#define COLOR1  #2a9d8f
#define COLOR9  #2a9d8f
//maroon
#define COLOR2  #502651
#define COLOR8  #502651
//white
#define COLOR3  #ffffff
#define COLOR11 #ffffff
//blue
#define COLOR4  #2d52da
#define COLOR12 #2d52da
//soft indigo
#define COLOR5  #818ee1
#define COLOR13 #818ee1
//offwhite
#define COLOR6  #f1ecf9
#define COLOR14 #f1ecf9
//light blue 
#define COLOR7  #6dced1
#define COLOR15 #6dced1

```

These colors get pulled by `~/.Xresources`. An easy way I manage color schemes is by simply changing the import statement.

```
#include "/home/zkauff/.xcolors/default"

*.foreground:  FOREGROUND
*.background:  BACKGROUND
*.cursorColor: FOREGROUND
*.color0:      COLOR0
*.color8:      COLOR8
*.color1:      COLOR1
*.color9:      COLOR9
*.color2:      COLOR2
*.color10:     COLOR10
*.color3:      COLOR3
*.color11:     COLOR11
*.color4:      COLOR4
*.color12:     COLOR12
*.color5:      COLOR5
*.color13:     COLOR13
*.color6:      COLOR6
*.color14:     COLOR14
*.color7:      COLOR7
*.color15:     COLOR15
```
