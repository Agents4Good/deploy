## 👩🏻‍💻 Uso

### Exemplo de Uso com o Eureca

> Troque o nome dos diretórios, arquivos, containers e imagens quando for realizar o mesmo para outras aplicações

Iniciar do zero:

```bash
vim .env
# Preencher .env

docker build --build-arg GITUSER="" --build-arg GITPASSWORD="" --build-arg BRANCH="branch-requisitada" -t eureca_chat .

docker run -it --name eureca_chat -p 5000:5000 eureca_chat
```

Iniciar container já criado anteriormente:

```bash
docker start eureca_chat
```

Se for necessário entrar no container para ajustes dentro do ambiente:

```bash
docker exec -it eureca_chat /bin/sh
```
