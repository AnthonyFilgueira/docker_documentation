# docker_documentation
Documentacion de Curso de Docker

# Comandos Iniciales
- listar carpetas que tiene la imagen en el directorio raiz
  - `docker run nombre_imagen:version ls /`

- iniciar consola dentro de la imagen
  - `docker run -i -t nombre_imagen:version sh`

- ver listado de contenedores
  - `docker ps`

- ejecutar contenedor en background
  - `docker run -d nombre_imagen:version` 

- conectarse a un contenedor en ejecucion
  - `docker exec -i -t nombre_imagen comando`

- Logearse en el docker hub
  - `docker login`

- Subir imagen al docker hub
  - `docker push nombre_imagen`

- Ejemplo de ejecutar php en windows
  - `docker run --rm -d --name php -v C:\laragon\www\suite_tooth\suite_tooth:/var/www/html/public innodite_suite_tooth/php`

- Ejemplo de ejecutar nginx en windows
  - `docker run --rm -d --name nginx -p 80:80 -v C:\laragon\www\suite_tooth\suite_tooth:/var/www/html/public --link php innodite_suite_tooth/nginx`

- ejecutar redis
  - `docker run --rm  -d  --name redis redis:alpine`

- Ejecutar mysql
  - `docker run -d --name=mysql -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_DATABASE=suite_tooth -e MYSQL_USER=innodite -e MYSQL_PASSWORD=123456 mysql:5.7`

- Ejecutar php enlazando redis y mysql
  - `docker run --rm -d --name php -v C:\laragon\www\suite_tooth\suite_tooth:/var/www/html/public --link redis:redis --link mysql:mysql innodite_suite_tooth/php`

- Crear una red 
  - `docker network create nombre_red`

- Conectar un contenedor a una red 
  - `docker network connect nombre_red nombre_contenedor`

- ejecutar redis conectado a una red
  - `docker run --rm  -d  --name redis --network innodite redis:alpine`

- ejecutar mysql conectado a una red
  - `docker run -d --name=mysql --network innodite -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_DATABASE=suite_tooth -e MYSQL_USER=innodite -e MYSQL_PASSWORD=123456 mysql:5.7`

- ejecutar php conectado a una red
  - `docker run --rm -d --name php -v C:\laragon\www\suite_tooth\suite_tooth:/var/www/html/public --network innodite innodite_suite_tooth/php`

- ejecutar nginx conectado a una red
  - `docker run --rm -d --name nginx -p 80:80 -v C:\laragon\www\suite_tooth\suite_tooth:/var/www/html/public --network innodite --link php innodite_suite_tooth/nginx`

- Ejecutar mysql con un volumen nombrado
  - `docker run -d --name=mysql --network innodite -v mysqldata:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -e MYSQL_DATABASE=suite_tooth -e MYSQL_USER=innodite -e MYSQL_PASSWORD=123456 mysql:5.7`

- Ejecutar servicios docker compose
  - `docker compose up`

- Detenerservicios docker compose
  - `docker compose down`


