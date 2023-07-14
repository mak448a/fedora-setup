# Setup Fedora on a brand new computer
[Aseprite](https://github.com/mak448a/compile-aseprite-fedora)

## DNF Configuration
```shell
sudo nano /etc/dnf/dnf.conf
```
Write this into the end of the file

max_parallel_downloads=10
defaultyes=True
keepcache=True

## Enable rpm fusion
```shell
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
sudo dnf groupupdate core
```

## Install media codecs
```shell
sudo dnf groupupdate multimedia --setop="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin
sudo dnf groupupdate sound-and-video
```

## Add flatpak
```shell
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

## Install essential apps
```shell
dnf copr enable phracek/PyCharm
sudo dnf install vlc pycharm-community dolphin-emu steam blender gimp
flatpak install flathub org.libretro.RetroArch
flatpak install flathub io.gitlab.gregorni.ASCIIImages
flatpak install flathub org.upscayl.Upscayl
```

## Other essentials
- Android Studio
- Godot Engine
- 


## Change hostname
```shell
sudo hostnamectl set-hostname "MyLaptop"
```

You're done!
