<h1 align="center">Deploy de Aplicações</h1>

> Esse repositório é dedicado à guardar todos os passos e arquivos necessários para deploy das aplicações do projeto de forma **CONJUNTA**.

> **AVISO:** Ao realizar deploy de poucas aplicações, recomendamos que utilize o Dockerfile de cada aplicação.

---

## 🚀 Instalação

[Docker no Linux](https://docs.docker.com/engine/install/ubuntu/)

[Docker no Windows](https://docs.docker.com/desktop/release-notes/)

---

## 👩🏻‍💻 Uso

### Exemplo de Uso com o Eureca

> Troque o nome dos diretórios, arquivos, containers e imagens quando for realizar o mesmo para outras aplicações

Iniciar do zero:

```bash
cd EurecaChat/

vim .env
# Preencher .env

docker build --build-arg GITUSER="" --build-arg GITPASSWORD="" --build-arg BRANCH="branch-requisitada" -t eureca_chat .

docker run -it --name eureca_chat -p 5000:5000 --env-file .env eureca_chat
```

Iniciar container já criado anteriormente:

```bash
docker start eureca_chat
```

Se for necessário entrar no container para ajustes dentro do ambiente:

```bash
docker exec -it eureca_chat /bin/sh
```

---

## 🤝 Contribuição

---
