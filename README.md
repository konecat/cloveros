# cloveros
![CloverOS GNU/Linux](https://raw.githubusercontent.com/chiru-no/cloveros/master/logo.png "CloverOS GNU/Linux")

CloverOS GNU/Linux is a GNU/Linux distro that runs on Gentoo GNU/Linux. It consists of the install script and the CloverOS GNU/Linux packages repo (Binhost) that contains unique USE flags and CFLAGS. You can download CloverOS GNU/Linux here https://github.com/chiru-no/cloveros/releases

## Cheat sheet

### Installing program
`emerge filezilla`

### Upgrading system
`emerge --sync`

`emerge -uavD world`

### Installing a program when emerge gives an error
`emerge -uavD filezilla world`

`dispatch-conf`

`emerge -uavD filezilla world`

### Installing DE
`emerge mate` / `emerge plasma-desktop` / `emerge lxde-meta` / `emerge xfce-meta`

`sed -i "s/twm/startxfce4/" ~/.bash_profile`

## FAQ

### Is this an overlay?
No, this uses regular Gentoo Portage only. Same versions and USE flag options.

### What makes CloverOS different/special/why is it made/what is it/who/where/when/how

CloverOS is a prericed out-of-the-box Gentoo with an altered default `/etc/portage/make.conf`. It's as close to default Gentoo as possible, unlike Gentoo-based distros like Sabayon. The scripts can be used to install it to hard drive, generate a LiveCD and create the CloverOS repo. The CloverOS repo is built with custom CFLAGS for optimum performance, and the USE flags are configured for desktop use. It focuses on speed and low ram usage, doesn't have systemd or other service bloat, and has software out of the box. There's some dotfiles in the home directory by default to save time. CloverOS should be an all-around good desktop distro while remaining simple, similar to CrunchBang. The default WM is twm, which allows you to move, resize, minimize/restore windows and launch programs.

CloverOS is an out of the box desktop. If you use Gentoo, you're probably gonna come to a similar conclusion as CloverOS (package.use, installed packages). The real question is why run this over CrunchBang/BunsenLabs, and the answer is better speed, ram use and programs/configuration being targeted to the average /g/ user.

### Why twm?

Low ram footprint. You can move windows by holding alt+leftclick, resize windows with alt+rightclick and close windows with ctrl+alt+rightclick. The taskbar minimizes and restores windows. twm's settings are in `~/.twmrc`.

### What programs does this come with?

Terminal - urxvt
File manager - xfe
Wifi configuration - wpa_gui
Browser - firefox
Text editor - emacs
Graphic editor - gimp
Video player - smplayer / mpv
FTP client - filezilla
Torrent client - rtorrent
IRC client - weechat

### Package isn't available
Make an issue so I can add the package. In the meantime, edit /etc/make.conf and edit the following line:

`EMERGE_DEFAULT_OPTS="--keep-going=y --autounmask-write=y --jobs=2 -G"`

to

`EMERGE_DEFAULT_OPTS="--keep-going=y --autounmask-write=y --jobs=2"`

This disables the binhost and uses Portage's ebuilds for packages.
