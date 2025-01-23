# dwm - dynamic window manager

dwm is an extremely fast, small, and dynamic window manager for X.

## Patches applied

- [monocle symbol](https://dwm.suckless.org/patches/monoclesymbol/) -> only display monocle symbol not number of clients
- [attach bottom](https://dwm.suckless.org/patches/attachbottom/) -> attach new clients to bottom of the stack
- [full gaps](https://dwm.suckless.org/patches/fullgaps/) -> adds gaps
- [winview](https://dwm.suckless.org/patches/winview/) -> makes Mod+0 more useful
- [move stack](https://dwm.suckless.org/patches/movestack/) -> move windows with Mod+Shift+J/K
- [tab + pertag](https://dwm.suckless.org/patches/pertag/) -> allows for separate layout rules per tag
- [preserve on restart](https://dwm.suckless.org/patches/preserveonrestart/) -> prevents clients mixing on tag 1

## Requirements

In order to build dwm you need the Xlib header files.

## Installation

Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

```bash
make clean install
```

## Running dwm

Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm

## Configuration

The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.
