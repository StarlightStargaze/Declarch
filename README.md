# Declarch
A CLI system management tool written in Rust, that simplifies the process of configuring and maintaining your system.
## Documentation
Documentation for how to use Declarch is available on the [Declarch Wiki](https://starlightstargaze.github.io/declarch_wiki/).

The **Declarch Wiki** contains instructions for installing and configuring.
## Features
### File and Directory Management
`declarch` allows you to store the configuration for your system all in one place and manages them. So you can have the piece of mind that you won't lose your configuration across reinstalls.
### Package Management
`declarch` acts as a wrapper for a number of package managers.
All you do is list the packages, and Declarch will install them in order.
Declarch supports Arch, Debian and OpenSUSE, more yet to come.

### Service Management
`declarch` also acts as a wrapper for service managers like systemctl.
List the services under their manager in the config, and they will be enabled/disabled.
Declarch only supports systemd currently.

**These are:**
- pacman
- zypper
- apt
- paru
- yay

**Declarch also manages some extensions/managers found on a wide range of distros:**
- Flatpak
- Visual Studio Code
- Vscodium
## Example Config:
```toml
[aliases]
"[drive]" = "mnt/SecDrive"

[paths]
[paths.system]
home = [
    [".zshrc", ".zshrc"],
    [".themes", ".themes"]
]

generic = [
    ["[drive]Music", "[home]Music"]
]
    
[paths.special_system]
root = [
    ["firefox", "/usr/lib/firefox"]
]
    
[install]
paru = [
    "code",
    "flatpak",
    "mpd-discord-rpc"
]

flatpak = [
    "com.sindresorhus.Caprine"
]
    
vsc = [
    "aaron-bond.better-comments",
    "bungcip.better-toml",
    "catppuccin.catppuccin-vsc",
    "esbenp.prettier-vscode"
]

[services]
[services.systemd]
user = [
    "pipewire",
    "mpd"
]

root = [
    "NetworkManager"
]
```
