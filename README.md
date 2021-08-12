# MySQL + Adminer
#### _Configuración basica para entorno de desarrollo_
-----------------------

## Comandos basicos

#### Ver contenedores que se estan ejecutando
```sh
docker ps
```
_*Salida:*_

| CONTAINER ID | IMAGE | COMMAND | CREATED | STATUS | PORTS | NAMES |
| ------------ | ----- | ------- | ------- | ------ | ----- | ----- |
| eebe69ae582e | mysql | "docker-entrypoint.s…" | 3 weeks ago | Up 43 hours | 0.0.0.0:3306->3306/tcp, :::3306->3306/tcp, 0.0.0.0:33060->33060/tcp, :::33060->33060/tcp |  mysql_db_1 |
| d5bf26e5827a | adminer | "entrypoint.sh docke…" | 3 weeks ago | Up 43 hours | 0.0.0.0:8080->8080/tcp, :::8080->8080/tcp | mysql_adminer_1 |

#### Detener un contenedor
```sh
docker stop [CONTAINER ID]
```
----------------------------------

## pasos para la ejecutar docker-compose MySQL - Adminer

#### 1.- Clonar repositorio

```
git clone https://github.com/elcascarudo-dev/docker-mysql-adminer.git
```

#### 2.- Cambiar la contraseña de root

En el archivo docker compose se encuentra la siguiente etiqueta:
```
MYSQL_ROOT_PASSWORD: password
```
Si no  se cambia este valor, por defecto las credenciales seran "root / password"

#### 3.- Ingresar al directorio creado

```
cd docker-mysql-adminer
```

#### 4.- Levantar contenedores

```
docker-compose up -d
```

#### 5.- Acceder al Adminer

Una vez levantados los contenedores podremos ingresar al Adminer mediante el navegador con la siguiente URL con las credenciales que se detallan en el punto 2:

```
http://localhost:8080
```

----------------------------------

## Otros comandos

#### Ver logs del contenedor

```
docker-compose logs -f --tail=100
```

#### Detener contenedor

```
docker-compose stop
```

#### Detener y destruir el contenedor

```
docker-compose down
```

