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
~/.xcolors/example
! special
*.foreground:   #c5c8c6
*.background:   #1d1f21
*.cursorColor:  #c5c8c6

! black
*.color0:       #282a2e
*.color8:       #373b41

! red
*.color1:       #a54242
*.color9:       #cc6666

! green
*.color2:       #8c9440
*.color10:      #b5bd68

! yellow
*.color3:       #de935f
*.color11:      #f0c674

! blue
*.color4:       #5f819d
*.color12:      #81a2be

! magenta
*.color5:       #85678f
*.color13:      #b294bb

! cyan
*.color6:       #5e8d87
*.color14:      #8abeb7

! white
*.color7:       #707880
*.color15:      #c5c8c6
```

These colors get pulled by `~/.Xresources`. An easy way I manage color schemes is by simply changing the import statement.

A great site to get these color schemes is https://terminal.sexy. You can generate color schemes and see how they look with some common programs you use. Then, go to the export tab and export format Xresources. You can download this and leave it in `~/.xcolors` and point to it in the `~/.Xresources` import statement.
