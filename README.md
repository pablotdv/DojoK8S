# Instalando o WSL 2

# Instalando o Docker Engine no WSL 2


```
sudo apt-get update

sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

sudo usermod -aG docker $USER
```

# Instalando o docker compose no WSL2

```
sudo apt-get update
 
sudo apt-get install docker-compose-plugin
```

# criando e rodando a imagem com docker

``` 
docker build -f DojoK8S/Dockerfile . -t dojok8s 
```

```
docker run -d -p 8080:80 dojok8s
```

fonte: https://docs.docker.com/compose/install/compose-plugin/

fonte: https://docs.docker.com/engine/install/ubuntu/