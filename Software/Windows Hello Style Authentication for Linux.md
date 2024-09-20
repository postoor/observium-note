
## Install howdy

```shell
yay -S howdy --noconfirm

# (beta)
yay -S howdy-beta-git --noconfirm
```

## Add IR sensor

```shell
# list IR sensor
v4l2-ctl --list-devices

sudo EDITOR=vim howdy config
... Change this
device_path = {$path_to_device}
```

## Setup Gnome password
```shell
# On Gnome
sudo vim /etc/pam.d/gdm-password
.... 
auth sufficient pam_python.so /lib/security/howdy/pam.py

# (beta)
auth sufficient /lib/security/pam_howdy.so

```

## Add face
```shell
sudo howdy -u $USER add
```