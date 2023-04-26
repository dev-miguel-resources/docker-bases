# Crear un servidor de MYSQL usando Docker

### Descargar la imagen de MYSQL

```
docker pull mysql:8
```

### Para listar imágenes

```
docker images
docker images | grep mysql (linux y mac)
docker images | findstr mysql (windows)
```

### Crear un contenedor de Docker

```
docker create mysql:8 (crear un contenedor con una imagen pero que docker le de el nombre)
docker create --name mysqlserver mysql:8 (crear un contenedor con un nombre que yo defina)
```

### Para listar contenedores

```
docker ps (solo me lista los que están con status: running)
docker ps -a (me traigo la lista independiente del status)
docker ps | findstr mysqlserver (esto es para filtrar los con status running)
docker ps -a | findstr mysqlserver (esto es para filtrar los con cualquier status)
```

### Para visualizar las ejecuciones de procesos del contenedor una vez se eche a correr

```
docker logs <nombre del contenedor> | identificador>
```

### Para iniciar un contenedor
```
docker start <nombre del contenedor> | identificador>
```

### Crear un contenedor mezclando el docker pull, docker create y el docker start
```
docker run -d --name test -e MYSQL_ROOT_PASSWORD=12345 -e MYSQL_USER=user -e MYSQL_PASSWORD=12345 -e MYSQL_DATABASE=cursonode mysql:8 (con definición de variables de entorno)
docker run -d -p 3310:3306 --name mysqlserver -e MYSQL_ROOT_PASSWORD=12345 -e MYSQL_USER=user -e MYSQL_PASSWORD=12345 -e MYSQL_DATABASE=cursonode mysql:8 (con definición de puertos)
```

### Para inspeccionar el contenido de un contenedor

```
docker inspect <nombre del contenedor> | identificador>
```

### Vincularme mediante la terminal con un contenedor

```
docker exec -it mysqlserver sh
```
