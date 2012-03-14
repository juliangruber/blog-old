---
layout: post
title: installing arch
---

### installing

* burn netinstall disk
* partition harddrives with gparted
* login as root
* run dhcpcd
* choose mirror: ftp://ftp.hosteurope.de
* set clock: ucp ntp
* fstab: add noatime to / and /home
* rc.conf: hostname, dhcp, daemons: @alsa, dbus, hal
* mkinitcpio.conf: add usbinput
* pacman.d/mirrorlist: http://mirror.rit.edu/archlinux (us)
* pick root password
* grub: add other operating systems, install on first entry

### base

    pacman-db-upgrade && pacman -Sy
    pacman -S curl vim sudo xf86-input-evdev xf86-video-ati mesa mesa-demos xorg-server xorg-xinit xorg-twm xorg-xclock xterm dbus wgetpaste xclip (ttf-dejavu) openssh (alsa-utils alsa-plugins libsamplerate) (surf libhspell) autocutsel (chromium) hal libgnome git texlive-core htop gtk-engines tango-icon-theme gcc make patch cmake gperf pkg-config net-tools xorg-xmessage vlc (apvlv) (urxvt) (transmission-gtk)

### office

    pacman -Slibreoffice artwiz-fonts openjdk6 alsa-lib virtualbox
    gpasswd -a julian vboxusers
    rc.d setup vboxdrv
    sudo modprobe vboxdrv
    virtualbox

New host: Windows 7, 1024mb ram, 20gb dynamic hdd

### sha512 passwords

* /etc/pam.d/passwd: replace md5 with sha512 and add rounds=65536
* /etc/default/passwd: change crypt=des to crypt=sha512
* /etc/login.defs: add ENCRYPT_METHOD SHA512

    passwd (for each user)

### users

* adduser, groups: wheel, games, audio, video, power, log, lp, optical
* visudo: uncomment %wheel ALL=(ALL) ALL

### x-server
  
    rc.d start dbus
    echo "autocutsel -fork &" >> /etc/X11/xinit/xinitrc.d/40-autocutsel
    echo "autocutsel -selection PRIMARY -fork &" >> /etc/X11/xinit/xinitrc.d/40-autocutsel

### ssh

* restrict ssh to protocol 2 in /etc/ssh/ssh_config

### sound

    alsamixer

Unmute master and pcm

    alsactl -f /var/lib/alsa/asound.state store
    echo "defaults.pcm.rate_converter \"samplerate_best\"" >> /etc/asound.conf

### aur

* install packer

    packer -S flashplugin-prerelease (without license)
    packer -S ttf-ms-fonts urxvt-clipboard urxvt-url-select

### screensaver

    echo "/usr/bin/xscreensaver -no-splash &" > ~/.xinitrc

### window manager & gtk

* download and compile awesome from git
* download awesome-themes from git
* lxappearance: clearlooks
* qtconfic: gtk+

### java
* uncomment last line in /etc/profile.d/openjdk6.sh and run

### bittorrent

    add blocklist: http://list.iblocklist.com/?list=bt_level1
