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

fonte: https://docs.docker.com/engine/install/ubuntu/

# Instalando o docker compose no WSL2

```
sudo apt-get update
 
sudo apt-get install docker-compose-plugin
```

fonte: https://docs.docker.com/compose/install/compose-plugin/

# Instalando o MiniKube

```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

sudo install minikube-linux-amd64 /usr/local/bin/minikube

minikube start --vm-driver=docker
```

fonte: https://minikube.sigs.k8s.io/docs/start/

# Instalando o kubectl 

```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

fonte: https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

# criando e rodando a imagem com docker

``` 
docker build -f DojoK8S/Dockerfile . -t dojok8s 

docker run -d -p 8080:80 dojok8s
```