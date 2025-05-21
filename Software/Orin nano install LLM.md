Pure Version
``` bash
%% Upgrade %%
sudo apt udpate && sudo apt dist-upgrade -y -qq

%% Install JetPack %%
sudo apt install nvidia-jetpack -y -qq

# install the container tools
git clone https://github.com/dusty-nv/jetson-containers
bash jetson-containers/install.sh

%% Install Docker %%
sudo apt install docker docker-compose-v2
sudo usermod -a -G docker $USER

sudo systemctl enable --now docker.service
```

Run ollama
```bash
jetson-containers run -d --name ollama $(autotag ollama) ollama serve

%% Pull llama3.2 models %%
jetson-containers run $(autotag ollama) ollama pull llama3.2:1b
jetson-containers run $(autotag ollama) ollama pull llama3.2:3b

```

Run open-webui

```bash
docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```