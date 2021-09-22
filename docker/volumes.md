# Volumes no Docker

Os Volumes são formas de compartilharmos dados entre a maquina host e os containers.

> **A dois tipos de vínculos que podemos ter para compartilhar dados com os containes**
>
> **Bind** = Associa uma pasta já existente a uma pasta interna do do contêiner
>
> **Volumes** = Esses são os volumes gerenciados.

### Montando volumes do tipo Bind

```bash
# O paramentro --mount é o responsavel por associarmos o volume local para o container
docker run -it --name meu_container --mount type=bind,src=/pasta_local,dst=/pasta_destino ubuntu:latest
# type = tipo de montagem
# source \ src = pasta local
# destination \ dst = pasta do container
```

> Também e possível definir o volume como só de leitura para a quele contêiner

##### Definindo volume como só leitura

```bash
# No final do argumeto para o paramentro --mount adicionamos o "ro" para definir como "Read Only"
docker run -it --name meu_container --mount type=bind,src=/pasta_local,dst=/pasta_destino,ro ubuntu:latest
```

### Criando Volumes

O Docker permite gerenciarmos volumes de uma foram simples com a cli, com os volumes gerenciados será bem mais fácil controlarmos os container

que utilizaram estes.

#### Criando Volumes gerenciados

```bash
# Cria volume
docker volume create meu_volume
# lista volumes
docker volume ls
# pega informaçõe dos volumes
docker volume inspect
```

### Montando volume do tipo Volume

```bash
# Monta volume meu_volume no container
docker run -it --name meu_container --mount type=volume,src=meu_volume,dst=/pasta_destino ubuntu:latest
```
