# Networks (Controlan el acceso y comunicación de los contenedores)

### Tipos de redes

```
Bridge (Default o Nombrada), host y none
```

### Bridge Default

```
docker exec -it test01 sh
ping 172.17.0.4
```

### Bridge Nombrada

```
docker exec -it test01 sh
ping 172.17.0.4
```

### Crear una red de tipo bridge nombrada y luego vincularla a un contenedor a crear

```
docker network create net-sql -d bridge
docker run -d --name test03 --network net-sql nginx:alpine
```

### Vincular una red a un contenedor existente

```
docker network connect net-sql test01
```

### Desvinculación de un contenedor de una red específica

```
docker network disconnect net-sql test01
```

### Para listar redes

```
docker network ls
docker network | grep sql
docker network | findstr sql
```

### Para inspeccionar redes

```
docker network inspect net-sql
```

### Para eliminar una red
```
docker network rm net-sql
```

### Red de tipo Host

```
Esta ocupa el mismo segmento de red de tu máquina
La red de tipo de host no puede ocuparse en windows
```

### Red de tipo None

```
La red de tipo de none no puede ocuparse en windows
Solo en ella puedes vincular solo un contenedor
```
