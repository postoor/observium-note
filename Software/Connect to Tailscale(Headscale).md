## Install tailscale
```shell
# Clinet
yay -S tailscale --noconfirm
sudo systemctl enable --now tailscale
```

## Create _Pre_-authentication keys

```shell
# headscale Server
sudo headscale --user USERNAME preauthkeys create --reusable --expiration 24h
```

## Connect server

```shell
sudo tailscale up --accept-routes=true  --accept-dns=false  --login-server={$URL} --auth-key={$KEY}
```