# otus-mysqldocker

mysql cluster
развернуть InnoDB кластер в docker

# Работоспособность

Поднимаем контейнеры `docker-compose up -d`

Заходим `mysqlsh -u root -P6446 -h 127.0.0.1 -pmysql`

И чекаем кластер

```
 MySQL  127.0.0.1:6446 ssl  JS > var cluster = dba.getCluster(); cluster.status()
{
    "clusterName": "TestCluster",
    "defaultReplicaSet": {
        "name": "default",
        "primary": "node1:3306",
        "ssl": "REQUIRED",
        "status": "OK",
        "statusText": "Cluster is ONLINE and can tolerate up to ONE failure.",
        ...
```
