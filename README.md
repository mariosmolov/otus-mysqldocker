# otus-mysqldocker

mysql cluster
развернуть InnoDB кластер в docker

# Работоспособность

Поднимаем контейнеры `docker-compose up -d`

Далее смотрим ID контейнера mysql-router и заходим в него `docker exec -it 7d34bf1256b5 bash`

![1](https://github.com/mariosmolov/otus-mysqldocker/blob/master/Screenshot_6.png)

Устанвливаем mysql-shell `yum install mysql-shell -y` и заходим в него `mysqlsh`

Коннектимся к базе `shell.connect('root@otus-mysqldocker_mysql-router_1:6446', 'mysql')`

Чекаем кластер

![2](https://github.com/mariosmolov/otus-mysqldocker/blob/master/Screenshot_5.png)
