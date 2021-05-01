# lembre-me
Projeto feito para cadastrar e lembrar usuários de assinaturas de softwares e outros.

# Instalação
Este projeto foi feito com Docker, portanto todos os códigos devem ser feitos dentro do container. Vamos iniciar a aplicação usando:

```
    docker-compose up -d --build
```

Ele irá criar um network chamado lembre-me, e dentro dele irão ter 3 containers: o nginx, o php, e o mysql (que pode ser retirado caso necessário).

# Usando o artisan
Para usar o artisan, precisamos utilizar um comando de dentro do container, visto que o mysql está containerizado:

```
    docker-compose exec php php /var/www/html/artisan migrate
```

# Usuário do MySQL
Os dados de acesso ao Container do MySQL estão no arquivo docker-compose.yml
```
    MYSQL_DATABASE: lembreme
    MYSQL_USER: lembreme
    MYSQL_PASSWORD: senhalembreme
    MYSQL_ROOT_PASSWORD: senhalembreme
```

Além disso, o projeto precisa utlizar o DB_HOST como mysql, que é o nome do container.

```
    DB_HOST=mysql
```