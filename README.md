# Fan controller for amdgpus

If you experience problems please create an issue.

## Installation:

### Arch Linux, Manjaro and derivatives
```
$ git clone https://github.com/zzkW35/amdgpu-fan.git
$ cd amdgpu-fan
$ makepkg -si
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
