
## Install EMQX
```bash
curl -s https://assets.emqx.com/scripts/install-emqx-deb.sh | sudo bash

sudo apt install emqx -y -qq

sudo systemctl enable --now emqx.service

```

## Dashboard Listen On 80, 443 Port
```bash
sudo setcap 'CAP_NET_BIND_SERVICE=+ep' /usr/lib/emqx/erts-{version}/bin/beam.smp 

sudo vim /etc/emqx/emqx.conf
.... Change dashboard.listeners.http.bind
dashboard.listeners.http.bind = 80


sudo systemctl restart emqx.service
```
