# kafka-local

Il faut que les dockers qui doivent communiquer soient sur le même réseau : karned !

Lancer les services  
```shell
docker-compose up -d
docker network connect karned kafka
docker network inspect karned | grep '"Name": "kafka"' -A 5
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