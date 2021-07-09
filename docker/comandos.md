# Comandos de Controle


#### Verifica se a Containers ativos

```bash
sudo docker ps 
```

#### Lista imagens baixadas 

```bash
docker images 
```
#### iniciar uma imagem docker 

- -i = interativo
- -t = terminal

```bash
docker -i -t image-name /path/start/process
docker -i -t ubuntu:14.10 /bin/bash
```

#### Sair do contêiner sem matar o processo

CTRL + p + q 

#### matar processo docker
CTRL + d

#### inicia container

```bash
docker start id-conteiner
```
#### para container

```bash
docker stop id-conteiner
```

#### voltar pra o conteiner 

```bash
docker attache id-container
```

#### Mostrar alterações efetuadas no conteiner deis da inicialização

```bash
docker diff id-container
```

#### cria container passando uma porta para ele

```bash
docker run -i -t -p 8080:80 ubuntu:14.10 /bin/bash  
```

#### Salvar alterações na imagem 

```bash
docker commit id-container criador/nome_desejado:1.0
```



#### Executar comando dentro do container 

```bash
docker exec id-container comando
docker exec 23ga2r4 ps
```

#### detalha container  em execução

```bash
docker inspect id-container
```

#### Detalha consumo de recurso do container

```bash
docker stats id-container
```

#### Remover container

```bash
docker rm id-container
```

#### forçar remoção

```bash
docker rm -f id-container
```

#### remover Imagem do container

```bash
docker rmi id-imagem
docker rmi -f id-imagem
```

#### comunicação entre container

```bash
docker run -it --name web02 --link grave_mcclane:web1 badtux/ngnx-ubuntu / bin/bash
```



# Docker file

- `docker build -f Dockerfile` **-** cria uma imagem a partir de um Dockerfile.
- `docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM` **-** constrói e nomeia uma imagem não-oficial.
- `docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM CAMINHO_DOCKERFILE` **-** constrói e nomeia uma imagem não-oficial informando o caminho para o Dockerfile.

#### cria imagem a partir da dockerfile no diretório atual passando o nome e versão

`-t = tag`

```bash
docker build -t pedroferreira/apache:1.0
```



# Controle de Recursos



#### limitar memoria do container ao iniciar

```bash
docker run -ti -m 512M debian /bin/bash
```


### limitar cpu no container
```bash
docker run -ti --cpu-shares 1024 debian /bin/bash # 50% da cpu
docker run -ti --cpu-shares 512 debian /bin/bash # 25% da cpu
docker run -ti --cpu-shares 512 debian /bin/bash # 25% da cpu
```


### docker update
```bash
docker update -m 256M  id-container # atualiza memoria em execução
docker update --cpu-shares 512 id-container # atualiza os cpus em execução
```

### Flags extras 

> ​	-w = **Working director** serve para passar a pasta que o contêiner iniciarar.



# Docker Hub

Comandos relacionados ao Docker Hub

- `docker login` **-** inicia o processo de login no Docker Hub.
- `docker push NOME_USUARIO/NOME_IMAGEM` **-** envia a imagem criada para o Docker Hub.
- `docker pull NOME_USUARIO/NOME_IMAGEM` **-** baixa a imagem desejada do Docker Hub.