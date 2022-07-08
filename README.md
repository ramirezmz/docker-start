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

## Port mapping
