# 🚀 Instalação do Passbolt via Docker

Este repositório contém um guia completo e um `docker-compose.yml` funcional para instalar o Passbolt Community Edition usando Docker.

## 📌 Pré-requisitos

- Docker
- Docker Compose

## 📁 Passos de Instalação

```bash
mkdir passbolt
cd passbolt/
nano docker-compose.yml
```

Cole o conteúdo do arquivo `docker-compose.yml` disponível neste repositório.

```bash
docker-compose up -d

chown -R 33:33 ./gpg_volume
chmod -R 700 ./gpg_volume
chown -R 33:33 ./jwt_volume
chmod -R 700 ./jwt_volume

docker-compose down
docker-compose up -d
docker ps
```

## 👤 Criar usuário administrador

```bash
docker exec -it passbolt su -m -c "/usr/share/php/passbolt/bin/cake passbolt register_user -u seu_email@dominio.com.br -f Seu_Primeiro_Nome -l Seu_Ultimo_Nome -r admin" -s /bin/bash www-data
```

## 🌐 Acesso ao sistema

- http://localhost:8080
- ou https://seu-dominio.com.br

## 📄 Documentação

Acesse a documentação em PDF em [`docs/Guia_Instalacao_Passbolt_Docker.pdf`](docs/Guia_Instalacao_Passbolt_Docker.pdf)
