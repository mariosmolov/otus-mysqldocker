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
        "topology": {
            "node1:3306": {
                "address": "node1:3306",
                "mode": "n/a",
                "readReplicas": {},
                "role": "HA",
                "shellConnectError": "MySQL Error 2005 (HY000): Unknown MySQL server host 'node1' (2)",
                "status": "ONLINE",
                "version": "8.0.15"
            },
            "node2:3306": {
                "address": "node2:3306",
                "mode": "n/a",
                "readReplicas": {},
                "role": "HA",
                "shellConnectError": "MySQL Error 2005 (HY000): Unknown MySQL server host 'node2' (2)",
                "status": "ONLINE",
                "version": "8.0.15"
            },
            "node3:3306": {
                "address": "node3:3306",
                "mode": "n/a",
                "readReplicas": {},
                "role": "HA",
                "shellConnectError": "MySQL Error 2005 (HY000): Unknown MySQL server host 'node3' (2)",
                "status": "ONLINE",
                "version": "8.0.15"
            }
        },
        "topologyMode": "Single-Primary"
    },
    "groupInformationSourceMember": "e5d7c9d41d5e:3306"
}
```
