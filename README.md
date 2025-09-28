# 🚀 Azure VM Docker Setup & Deployment Guide

This guide walks you through launching an Azure VM, installing Docker, running containers, and building/pushing your own images.

---

## 1️⃣ Launch Azure VM – Linux

* Create an **Ubuntu Server** VM (e.g., Ubuntu 24.04 LTS) in Azure.
* Configure **NSG rules** to allow:

  * SSH (22)
  * HTTP (80)
  * Any custom port you want (e.g., 1000)

---

## 2️⃣ Connect via SSH

```bash
cd Downloads
chmod 400 key.pem
ssh -i key.pem atul@20.64.238.166
```

---

## 3️⃣ Install Docker

```bash
sudo apt update -y
sudo apt install docker.io -y
docker --version

sudo systemctl start docker
sudo systemctl enable docker
sudo systemctl status docker
```

---

## 4️⃣ Docker Hub Login

* Sign up at [Docker Hub](https://hub.docker.com/).

```bash
sudo docker login
```

---

## 5️⃣ Pull & Run NGINX

```bash
sudo docker images
sudo docker pull nginx
sudo docker images

# Run on port 80
sudo docker run -d -p 80:80 nginx
```

🌐 Access in browser:
`http://<vm-public-ip>:80`

---

## 6️⃣ Manage Containers

```bash
sudo docker container ls
sudo docker container stop <container_id>
sudo docker container start <container_id>
sudo docker container rm <container_id>
```

---

## 7️⃣ Manage Images

```bash
sudo docker images
sudo docker rmi <image_id>
sudo docker images
```

---

## 8️⃣ Run NGINX on Custom Port

```bash
sudo docker run -d -p 1000:80 nginx
```

🌐 Access in browser:
`http://<vm-public-ip>:1000`

---

## 9️⃣ Container Control

```bash
sudo docker container ls
sudo docker container stop <container_id>
sudo docker container start <container_id>
```

---

## 🔟 Clone & Build Python HelloWorld App

```bash
git clone https://github.com/atulkamble/docker-python-helloworld.git
cd docker-python-helloworld

# Build Docker image
sudo docker build -t atuljkamble/pythonhelloworld .
```

---

## 1️⃣1️⃣ Push to Docker Hub

```bash
sudo docker push atuljkamble/pythonhelloworld
```

---

## 1️⃣2️⃣ Run Your Image

```bash
docker pull atuljkamble/pythonhelloworld
docker run atuljkamble/pythonhelloworld
```

---


Would you like me to **convert this into a polished `README.md`** with emojis, section dividers, and commands formatted for GitHub repo documentation?
