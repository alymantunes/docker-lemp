# Docker Compose Ambiente LEMP

Este repositório contém uma pequena configuração `docker-compose` para iniciar o Ambiente ` LEMP (Linux, Nginx, MariaDB, PHP) ` com php já otmizado para GLPI.

## Detalhes

Verções

* PHP 7.2 (FPM) - custom
* Nginx 1.13.6
* MariaDB 10.3.9

Este projeto funciona nas seguintes portas:

| Servidor   | Porta |
|------------|-------|
| Nginx      | 80    |
| PHP-FPM    | 9000  |
| MySQL      | 3306  |

* [Referência do Docker Compose versão 3](https://docs.docker.com/compose/compose-file/)

### Estrutura do Projeto

```sh
.
├── app
│   └── '* arquivos do glpi'
├── dados
│   └── '* persistencia do banco de dados'
├── config
│   └── nginx
│       └── nginx.conf
├── docker
│   └── php.Dockerfile
├── .env
├── docker-compose.yml
└── README.md
```


## Configuração

A configuração do Nginx esta em `config/nginx/`.

Você precisa inserir as variáveis no arquivo `.env` , conforme exemplo `.env-exemplo`

| Key | Description |
|-----|-------------|
|APP_NAME|The name used when creating a container.|
|MYSQL_ROOT_PASSWORD|Senha do ususario root|

##### Clonando o repositório.

comando: `git clone https://github.com/alymantunes/docker-lemp.git`.

##### Iniciando os servidores

`docker-compose up`.

## Acessando um Container

`docker exec -ti {CONTAINER_NAME} /bin/bash`

* `{APP_NAME}-php`
* `{APP_NAME}-nginx`
* `{APP_NAME}-mariadb`
