# Fan controller for amdgpus

If you experience problems please create an issue.

<a href="https://aur.archlinux.org/packages/amdgpu-fan/"><img src="https://raw.githubusercontent.com/CorvetteCole/amdgpu-fan/master/download_aur.png" height="54"></a>

## Installation:

### Arch Linux, Manjaro and derivatives
Install from the [AUR](https://aur.archlinux.org/packages/amdgpu-fan/) using your favorite helper, or build manually as shown below:
```
$ git clone https://github.com/zzkW35/amdgpu-fan.git
$ cd amdgpu-fan
$ makepkg -si
```
### Alpine Linux and derivatives
Install from the
[repositories](://pkgs.alpinelinux.org/packages?name=amdgpu-fan&branch=edge) or
build from source via aports:

```
$ git clone https://gitlab.alpinelinux.org/alpine/aports.git
$ cd aports/*/amdgpu-fan
$ abuild -r
```

## Usage:
`$ sudo amdgpu-fan`  
Start the daemon with `$ sudo systemctl start amdgpu-fan`  
Make it with run at startup with `$ sudo systemctl enable amdgpu-fan`


## Configuration:
Edit `/etc/amdgpu-fan.yml` to create the desired fan curve

```
# /etc/amdgpu-fan.yml
# eg:

speed_matrix:  # -[temp(*C), speed(0-100%)]
- [0, 0]
- [40, 30]
- [60, 50]
- [80, 100]

# optional
# cards:  # can be any card returned from
#         # ls /sys/class/drm | grep "^card[[:digit:]]$"
# - card0

# optional
# temp_drop: 5  # how much temperature should drop before fan speed is decreased
```
