## Neg-Dark

This is a darker version of the Arc theme. 
I did not want to call this Arc-Dark, so I created a new repository

### Examples

####Lollypop:

![Lollypop](https://i.imgur.com/fJk0q2z.png)

####Firefox filechooser:

![Firefox](https://i.imgur.com/E9XcdVs.png)

### Requirements

* Gnome/GTK3 3.14 - 3.22
* The `gnome-themes-standard` package
* The murrine engine. This has different names depending on your distro.
  * `gtk-engine-murrine` (Arch Linux)
  * `gtk2-engines-murrine` (Debian, Ubuntu, elementary OS)
  * `gtk-murrine-engine` (Fedora)
  * `gtk2-engine-murrine` (openSUSE)
  * `gtk-engines-murrine` (Gentoo)

Main distributions that meet these requirements are

* Arch Linux and Arch Linux based distros
* Ubuntu 15.04 or newer (**Ubuntu 14.04 and 14.10 are not supported**)
* elementary OS Freya/Loki
* Debian 8, Testing or Unstable
* Gentoo
* Fedora 21 or newer
* openSUSE 13.2, Leap 42.1 and Tumbleweed

Derivatives of these distributions should work, as well.

If your distribution isn't listed, please check the requirements yourself.

### Installation

**Important:** Remove all older versions of the theme from your system before you proceed any further.

    sudo rm -rf /usr/share/themes/{Arc,Arc-Darker,Arc-Dark}
    rm -rf ~/.local/share/themes/{Arc,Arc-Darker,Arc-Dark}
    rm -rf ~/.themes/{Arc,Arc-Darker,Arc-Dark}

#### Packages

Prebuilt packages for Ubuntu, Debian, Fedora and openSUSE are available at  
http://software.opensuse.org/download.html?project=home%3AHorst3180&package=arc-theme  

A non-transparent version of the theme is available here  
http://software.opensuse.org/download.html?project=home%3AHorst3180&package=arc-theme-solid  

**Note:** elementary OS Freya users can install the package for Ubuntu 15.04, Loki user can install the package for Ubuntu 16.04

--

Arch Linux users can install the theme from the AUR

**Official Releases**: https://aur.archlinux.org/packages/gtk-theme-arc/  

**Development Releases**: https://aur.archlinux.org/packages/gtk-theme-arc-git/  

**Note:** If you're having trouble with the AUR packages please email the package maintainer at zach@zach-adams.com before creating an issue.

--

Gentoo/Funtoo users can install `x11-themes/arc-theme` from the [Scriptkitties Overlay][sk-overlay].

--

#### Manual Installation

To build the theme you'll need 
* `autoconf`
* `automake`
* `pkg-config` or `pkgconfig` if you use Fedora
* `libgtk-3-dev` for Debian based distros or `gtk3-devel` for RPM based distros
* `git` if you want to clone the source directory

If your distribution doesn't ship separate development packages you just need GTK 3 instead of the `-dev` packages.

Install the theme with the following commands

**1. Get the source**

If you want to install the latest version from git, clone the repository with

    git clone https://github.com/horst3180/arc-theme --depth 1 && cd arc-theme

**2. Build and install the theme**

    ./autogen.sh --prefix=/usr
    sudo make install

Other options to pass to autogen.sh are

    --disable-transparency     disable transparency in the GTK3 theme
    --disable-light            disable Arc Light support
    --disable-darker           disable Arc Darker support
    --disable-dark             disable Arc Dark support
    --disable-cinnamon         disable Cinnamon support
    --disable-gnome-shell      disable GNOME Shell support
    --disable-gtk2             disable GTK2 support
    --disable-gtk3             disable GTK3 support
    --disable-metacity         disable Metacity support
    --disable-unity            disable Unity support
    --disable-xfwm             disable XFWM support

    --with-gnome=<version>     build the theme for a specific Gnome version (3.14, 3.16, 3.18, 3.20)
                               Note: Normally the correct version is detected automatically and this
                               option should not be needed.

After the installation is complete you can activate the theme with `gnome-tweak-tool` or a similar program by selecting `Arc`, `Arc-Darker` or `Arc-Dark` as Window/GTK+ theme and `Arc` or `Arc-Dark` as Gnome-Shell and Xfce-Notify theme.

**Uninstall the theme**

Run

    sudo make uninstall

from the same directory as this README resides in, or

    sudo rm -rf /usr/share/themes/{Arc,Arc-Darker,Arc-Dark}

### Troubleshooting

If you have Ubuntu with a newer GTK/Gnome version than the one included by default (i.e Ubuntu 14.04 with GTK 3.14 or Ubuntu 15.04 with GTK 3.16, etc.) the prebuilt packages won't work properly and you have to install the theme manually as described above.
This is also true for other distros with a different GTK/Gnome version than the one included by default

--

If you get artifacts like black or invisible backgrounds under Unity, disable overlay scrollbars with

    gsettings set com.canonical.desktop.interface scrollbar-mode normal


### License
Arc is available under the terms the GPL-3.0. See `COPYING` for details.
