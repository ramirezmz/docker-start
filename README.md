# DOCKER

### Que es un contenedor?

Es una forma de empaquetar nuestra aplicaciones.

Podemos tener una aplicacion:

- HTML
- Nodejs
- .env

Los contenedores son `portables`, para poder compartir

### Donde se almacenan?

- Repositórios de contenedores
  - Privados
  - Públicos (Docker Hub, Github,etc)

### Con Contenedores:

Primero necesitamos descargar la imagen basada en linux y podemos usarlo con un comando probablemente.

## Qué es una imagen?

- Dependencias
- Código
- Lo que se comparte

      	Que es un contenedor?

  Alpine = version de linux más liviana

VM: Virtual Machine

- Hardware
- Kernel
- Aplicaciones

Docker:

- Aplicaciones

      Para virtualización

Host: nosotros
Guess: clientes

    	Virtualizacion Parcial
    	Virtualizacion COmpleta

## Comandos

- Create a docker image with port and name:
  `docker create -p27017:27017 --name monguito mongo`

Ele nos deve retornar o ID do container
`b3492768277854472045429fe22d703a4e40be488a59e8669ded32192edc7760 `

- Follow logs by terminal
  `docker log --follow monguito`

- Rodar algun docker
  `docker run nome_do_docker`

  Si deseamos usar nuevamente el docker, podemos adicionar `-D` al comando de `docker run -D nome_do_docker`

- Rodar una imagen que creamos
  `docker run --name monguito -p27017:27017 -d mongo`

- Remover docker
  `docker rm nome_docker`

## Creando una imagen docker para nuestra aplicacion

`docker pull mongo`

`docker create -p27017:27017 --name monguito -e MONGO_INITDB_ROOT_USERNAME=nico -e MONGO_INITDB_ROOT_PASSWORD=password mongo`

`docker ps`
`docker start monguito`

## Port mapping

## Dockerfile

El archivo Dockerfile sirve para crear la configuracion de nuestra imagen.

## Como crear una red

Create a red
`docker network create mired`

Delete a red
`docker network rm mired`

List all reds
`docker network ls`

Montar uma imagen docker a partir de um Dockerfile
`docker build -t nombreDeLaImagen:1 rutaDelProjectoDockerfile`

levantar docker com compose

`docker compose up`

Remover docker compose e limpar

`docker compose down`

### Usando MongoDB + node18

Levantar MongoDB
`docker create -p27017:27017 --name monguito --network mired -e MONGO_INITDB_ROOT_USERNAME=nico MONGO_INITDB_ROOT_PASSWORD=password mongo`

Levantar NodeJS e apontar para nossa red
`docker create -p3000:3000 --name chanchito --network mired myapp:1`

Depois, startar as duas, começando pelo DB
`docker start monguito`
`docker start chanchito`

Docker compose levantar
`docker compose up`
Docker compose limpar e remover dados
`docker compose down`

## Recapitulando

Docker conteiners:

- Descargar imagen
- Crear una red
- Crear contenedor
  - asignar puertos
  - Asignar nombre
  - Asignar variables de entorno
  - Especificar red
  - Indicar imagen:etiqueta

Todo eso para cada contenedor.

OBS.
chanchito es nuestra app
monguito es nuestro DB

## VOLUMES

Tipos:

- Anonimo: solo indicas la ruta
- De anfitrion o host: tu decides que carpeta montar y usar
- Nombrado
