<p align=center>
<br>
<a href="http://makeapullrequest.com"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg"></a>
<img src="https://img.shields.io/badge/os-linux-brightgreen">
<img src="https://img.shields.io/badge/os-mac-brightgreen">
<img src="https://img.shields.io/badge/os-windows-brightgreen">
<img src="https://img.shields.io/badge/os-android-brightgreen">
<br>
<a href="https://discord.gg/aqu7GpqVmR"><img src="https://invidget.switchblade.xyz/aqu7GpqVmR"></a>
<br>
<a href="https://github.com/ura43"><img src="https://img.shields.io/badge/lead-ura43-lightblue"></a>
<a href="https://github.com/CoolnsX"><img src="https://img.shields.io/badge/maintainer-CoolnsX-blue"></a>
<a href="https://github.com/RaynardGerraldo"><img src="https://img.shields.io/badge/maintainer-RayGL-blue"></a>
<br>
<a href="https://github.com/71zenith"><img src="https://img.shields.io/badge/maintainer-71zenith-blue"></a>
<a href="https://github.com/iamchokerman"><img src="https://img.shields.io/badge/maintainer-iamchokerman-blue"></a>
<a href="https://github.com/Derisis13"><img src="https://img.shields.io/badge/maintainer-Derisis13-blue"></a>

</p>

<h3 align="center">
A cli to browse and watch anime. This tool scrapes the site <a href="https://gogoplay4.com">gogoplay.</a>

Latest stable version: 2.0.0
</h3>
	
<h1 align="center">
	Showcase
</h1>

https://user-images.githubusercontent.com/44473782/160729779-41fe207c-b5aa-4fed-87db-313c83caf6bb.mp4

## Table of Contents

- [Fixing errors](#Fixing-errors)
- [Install](#Installation)
  - [Arch](#Arch)
  - [Linux](#Linux)
  - [Mac](#Mac)
  - [Windows](#Windows)
  - [Android](#Android)
- [Uninstall](#Uninstall)
- [Dependencies](#Dependencies)
- [Contribution Guidelines](./CONTRIBUTING.md)
- [Disclaimer](./disclaimer.md)

## Fixing errors

if you encounter "Video url not found" or any breaking issue, then make sure you are on latest version by typing
`sudo ani-cli -U` to update on linux, mac and android. On windows, run gitbash as administrator then there type `ani-cli -U`.
If after this the issue persists then open an issue.
<br>
If you see sed warnings or your history entries have disappeared after updating, then update your history file with the history
transition script (history_transition.sh). Download it: `git clone https://github.com/pystardust/ani-cli` then run: `./ani-cli/hist-transition.sh`
It doesn't work for all anime, but the ones it can't find will print out alongside their episode numbers. In the end clean up: `rm -rf ./ani-cli`

## Install

### Arch

Also consider ani-cli-git

```sh
yay -S ani-cli
```
### Linux

Install dependencies [(See below)](#Dependencies)

```sh
git clone https://github.com/pystardust/ani-cli && cd ani-cli
sudo cp ani-cli /usr/local/bin/ani-cli
```

*Note that mpv installed through flatpak is not compatible*

### Mac

Install homebrew [(Guide)](https://brew.sh/)

```sh
brew tap iamchokerman/ani-cli
brew install ani-cli
```
*If you are upgrading from the old manual install process, you may have to remove the old ani-cli by running `sudo rm /usr/local/bin/ani-cli`*

### Windows

*Note that the installation instruction below must be done inside 
Powershell as **administrator**, not in Command Prompt*

Install scoop [(Guide)](https://scoop.sh/)
```
scoop bucket add extras
mkdir -p "$env:USERPROFILE/.cache"
scoop install ani-cli -g
```

*Make sure git bash is installed [(Install)](https://git-scm.com/download/win)*

Exit Powershell, then in Git Bash, run 
```
echo "export MSYS_NO_PATHCONV=1" >> ~/.bashrc
source ~/.bashrc
```

*Run ani-cli in Git Bash (Running it in cmd or powershell may or may not work)*

### Android

Install termux [(Guide)](https://termux.com/)

```sh
pkg update
pkg install git termux-tools ncurses-utils openssl-tool ffmpeg -y
git clone https://github.com/pystardust/ani-cli && cd ani-cli
cp ani-cli $PREFIX/bin/ani-cli
echo 'am start --user 0 -a android.intent.action.VIEW -d "$1" -n is.xyz.mpv/.MPVActivity' > $PREFIX/bin/mpv
chmod +x $PREFIX/bin/mpv
```

Install mpv-android [(Link)](https://play.google.com/store/apps/details?id=is.xyz.mpv)

*Add ```referrer="https://gogoplay5.com"``` to mpv.conf (Open mpv app, goto three dots top right->Settings->Advanced-->Edit mpv.conf)* 

*Note: VLC android doesn't support referrer option. So it will not work*

## Uninstall

* Arch Linux: ```yay -R ani-cli```
* Other Linux: Just remove the thing from path
* Mac: ```brew uninstall ani-cli```
* Windows: ```scoop uninstall ani-cli```
* Android: Just remove the thing from path

## Dependencies

- grep
- sed
- curl
- openssl
- mpv - Video Player
- aria2 - Download manager
- ffmpeg - m3u8 Downloader
