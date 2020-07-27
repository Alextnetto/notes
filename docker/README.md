# Learn_Docker
Repositório para fixar o aprendizado da ferramenta Docker

  - [Docker build](#docker-build)
  - [Docker run](#docker-run)
  - [Manipulando containers e imagens](#Manipulando-containers-e-imagens)
  - [Docker push](#docker-push)

> Ótimo [link](https://www.alura.com.br/artigos/desvendando-o-dockerfile)

<p  align="center">
    <img alt="Imagem vs Container" src="https://www.alura.com.br/artigos/assets/desvendando-o-dockerfile/imagem1.jpg">
</p>

## docker build

Constrói uma imagem a partir do Dockerfile:

```bash
docker build -t username/tag:version .
```

>    **-t** = Atribui uma tag a imagem para ficar mais fácil de manipular a imagem depois
>    **.**  = Refere ao Dockerfile na pasta atual


## docker run

Cria um container em cima de uma imagem:

```bash
docker run -d -t -p host:container --name my-container my-imagem
```

>    **-d** = Roda o container no background(Rodar sem esse comando a primeira vez, para ver o output da execução)
>    **-t** = Adiciona um terminal ao container
 >   **-p** = Mapeia as portas do container


## Manipulando containers e imagens

**Abrir o terminal dentro do container:**
```bash
docker exec -it my-container bash
```

**Listar**
```bash
docker ps     # os containers em execução
docker ps -a  # todos os containers
docker images # todas as imagens
```

**Remover**
```bash
docker rm my-container   # containers
docker rmi my-imagem     # imagens
```
Se o container estiver em execução, é preciso interromper para remove-lo
```bash
docker stop my-container
```

## docker push

Com a conta do dockerhub é possível subir as imagens para nuvem

```bash
# Construindo a imagem
docker build -t username/tag:version . 
# Logando no dockerhub
docker login -u "username" -p "password" docker. io
# Subindo a imagem
docker push username/tag:version
```