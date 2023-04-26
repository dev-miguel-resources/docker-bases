# Volúmenes (me permiten agregarle persistencia a los contenedores)

### Tipos de volúmenes (para trabajo local)

```
Host, Anónimo y Nombrado
```

#### Creación y ejemplo de tipo Host

```
1. Defines un directorio de persistencia en tu máquina de manera manual
2. Trabajan fuera de la red virtual de docker por tanto no puedes mediante comandos: listarlos, inspeccionarlos y eliminarlos
3. De acceso visible y manipulable por gestiones humanas

docker run -d -p 3310:3306 -v E:\docker_examples\docker\volumen\mysql:/var/lib/mysql --name mysqlserver -e MYSQL_ROOT_PASSWORD=12345 -e MYSQL_USER=user -e MYSQL_PASSWORD=12345 -e MYSQL_DATABASE=cursonode mysql:8
4c239c7ab1a0141250860e519a672606d6c643214668d32c0b9e2dae29fb7005
```

#### Para listar los volúmenes

```
docker volume ls
docker volume ls | grep nginx
docker volume ls | findstr nginx
```

#### Para inspeccionar los volúmenes

```
docker volume inspect <nombre del volumen>
```

#### Para eliminar volúmenes

```
docker volume rm <nombre del volumen>
```

#### Creación y ejemplo de volúmen anónimo

```
1. No se le asigna ninguna ruta o nombre al volumen
2. La persistencia se genera bien, pero si el contenedor se vuelve a construir, la definición del volumen}
anónimo se vuelve a crear pero con un nombre diferente
3. Es sentido práctico es solo para jugar
4. Si se pueden eliminar por terminal, listar e inspeccionar
5. Es que son díficiles de identificar
6. Los volúmenes de tipo anónimo, son los únicos que los puedes eliminar en conjunto con el contenedor

docker run -d -p 3310:3306 -v :/var/lib/mysql --name mysqlserver -e MYSQL_ROOT_PASSWORD=12345 -e MYSQL_USER=user -e MYSQL_PASSWORD=12345 -e MYSQL_DATABASE=cursonode mysql:8
4c239c7ab1a0141250860e519a672606d6c643214668d32c0b9e2dae29fb7005
```

#### Para eliminar volúmenes anónimos en conjunto del contenedor

```
docker rm -fv <nombre del contenedor>
```