# Cheet Sheet Docker



## Comandos relacionados às informações



#### Exibe a versão do docker que está instalada.

```bash
docker version 
```

#### Pegar informações sobre o container.

``````bash
docker inspect ID_CONTAINER
``````

#### Exibir todos os containers em execução no momento.

````````bash
docker ps
````````

#### Exibir todos os containers, independentemente de estarem em execução ou não.

``````bash
docker ps -a
``````



## Comandos relacionados à execução



#### cria um container com a respectiva imagem passada como parâmetro.

``````bash
docker run NOME_DA_IMAGEM
``````

#### conecta o terminal que estamos utilizando com o do container.

``````````bash
docker run -it NOME_DA_IMAGEMb
``````````



#### Define uma porta aleatória.

```
docker run -d -P --name NOME dockersamples/static-site
```



#### define a porta 80 do container, e direciona a porta 12345 para a porta do contêiner.

```bash
docker run -d -p 12345:80 dockersamples/static-site
```



#### cria um volume no respectivo caminho do container.

```bash
docker run -v "CAMINHO_VOLUME" NOME_DA_IMAGEM
```

 #### cria um container especificando seu nome e qual rede deverá ser usada.

``````bash
docker run -it --name NOME_CONTAINER --network NOME_DA_REDE NOME_IMAGEM		
``````

## Comandos relacionados à inicialização/interrupção



#### inicia o container com id em questão.

```
docker start ID_CONTAINER 
```



#### inicia o container com id em questão e integra os terminais, além de permitir interação entre ambos.

````````bash
docker start -a -i ID_CONTAINER		
````````



#### interrompe o container com id em questão.

````````bash
docker stop ID_CONTAINER
````````



## Comandos relacionados à remoção



#### remove o container com id em questão.

````````bash
docker rm ID_CONTAINER 
````````



#### remove todos os containers que estão parados.

``````bash
docker container prune
``````



#### remove a imagem passada como parâmetro.

````````bash
docker rmi NOME_DA_IMAGEM
````````



## Comandos relacionados à construção de Dockerfile



#### Cria uma imagem a partir de um Dockerfile.

``````bash
docker build -f Dockerfile
``````

#### Constrói e nomeia uma imagem não-oficial.

``````bash
docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM 
``````



#### Constrói e nomeia uma imagem não-oficial informando o caminho para o Dockerfile.

````````bash
docker build -f Dockerfile -t NOME_USUARIO/NOME_IMAGEM CAMINHO_DOCKERFILE
````````



## Comandos relacionados ao Docker Hub



#### inicia o processo de login no Docker Hub.

````````bash
docker login
````````

#### envia a imagem criada para o Docker Hub.

``````bash
docker push NOME_USUARIO/NOME_IMAGEM 	
``````



#### Baixa a imagem desejada do Docker Hub.

````````bash
docker pull NOME_USUARIO/NOME_IMAGEM
````````



## Comandos relacionados à rede



#### cria uma rede especificando o driver desejado.

````bash
docker network create --driver bridge NOME_DA_REDE 
````





## Comandos relacionados ao docker-compose



#### Realiza o build dos serviços relacionados ao arquivo docker-compose.yml, assim como verifica a sua sintaxe.

``````bash
docker-compose build
``````

####  Sobe todos os containers relacionados ao docker-compose, desde que o build já tenha sido executado.

```bash
docker-compose up 
```



####  Para todos os serviços em execução que estejam relacionados ao arquivo docker-compose.yml.

```bash
docker-compose down
```

 