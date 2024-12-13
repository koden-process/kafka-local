# kafka-local

Lancer les services  
```shell
docker-compose up -d
```

Arrêter les services  
```shell
docker-compose down
```

Ouvrez un navigateur et accédez à http://localhost:9000. 
Vous pourrez y voir les topics, partitions et messages.  

Créer un topic  
```shell
docker exec -it kafka kafka-topics --create \
  --topic example-topic \
  --bootstrap-server localhost:9092 \
  --partitions 1 \
  --replication-factor 1
```

lister les topics  
```shell
docker exec -it kafka kafka-topics --list --bootstrap-server kafka:9092
```