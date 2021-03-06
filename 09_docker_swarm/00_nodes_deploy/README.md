# Guia

Obtener en el nodo maestro el comando para adicionar un nuevo nodo al swarm
```
docker swarm join-token worker
```

Adicionar el nodo
```
docker swarm join \
  --token  SWMTKN-1-49nj1cmql0jkz5s954yi3oex3nedyz0fb0xx14ie39trti4wxv-8vxv8rssmk743ojnwacrr2e7c \
  192.168.99.100:2377
```

Ver el estado del swarm
```
docker info
```

Ver el estado de los nodos
```
docker node ls
```

Crear una tarea en el swarm
```
docker service create --replicas 1 --name <SERVICE-ID> alpine ping docker.com
```

Validar que se ha desplegado la tarea
```
docker service ls
```

Despliegue los detalles de un servicio
```
docker service inspect --pretty <SERVICE-ID>
```

Observe los nodos que estan ejecutando el servicio
```
docker service ps <SERVICE-ID>
```

Actualice la cantidad de replicas del servicio
```
docker service scale <SERVICE-ID>=<NUMBER-OF-TASKS>
```

Observe los cambios
```
docker service ps
```

Desactive uno de los nodos
```
docker node update --availability drain <NODE-ID>
```

Verifique la disponibilidad del nodo
```
docker node inspect --pretty <NODE-ID>
```

Observe nuevamente el estado del servicio en el swarm
```
docker service ps <SERVICE-ID>
```

Reactive el nodo
```
docker node update --availability active <NODE-ID>
```

Verifique la disponibilidad del nodo
```
docker node inspect --pretty <NODE-ID>
```

Elimine el servicio
```
docker service rm <SERVICE-ID>
```

# Referencias
https://docs.docker.com/engine/swarm/swarm-tutorial/rolling-update/

