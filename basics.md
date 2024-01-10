# Checar la version
docker --version

# listar todas la imagenes
docker images

# buscar imagenes en docker hub
docker search [nombre_imagen]

# listar los contenedores en ejecucion
docker ps

# listar todos los contenedores
docker ps -a

# correr doom como ejemplos

* docker run docker/whalesay cowsay Hello, Docker!

* docker run --rm -t callumhoughton22/doom-in-docker:0.1

# ejecutar contenedor

# stop al contenedor
# eliminar el contenedor
# eliminar una imagen


---
# Creando una imagen

## Ejecutando contenedor desde imagen

docker run --rm -p 5001:80 docker-course:nginx-example

# Ejecutarlo en una linea

docker run --name mi-nginx -p 8080:80 -v $(pwd)/index.html:/usr/share/nginx/html/index.html:ro -d nginx

---

# Multilayer y multistage



---

# Levantando un wordpress

docker network create wordpress-net

docker run --name mysql-wordpress --network wordpress-net -e MYSQL_ROOT_PASSWORD=somewordpress -e MYSQL_DATABASE=wordpress -e MYSQL_USER=wordpress -e MYSQL_PASSWORD=wordpress -v mysql_data:/var/lib/mysql -d mysql:5.7

docker run --name wordpress --network wordpress-net -e WORDPRESS_DB_HOST=mysql-wordpress -e WORDPRESS_DB_USER=wordpress -e WORDPRESS_DB_PASSWORD=wordpress -e WORDPRESS_DB_NAME=wordpress -p 8000:80 -v wordpress_data:/var/www/html -d wordpress:latest





