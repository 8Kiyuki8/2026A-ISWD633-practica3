## Esquema para el ejercicio
![Imagen](esquema-ejercicio3.PNG)

### Crear red net-wp
docker network create net-wp

docker run -d --name mysql-db --network net-wp -e MYSQL_ROOT_PASSWORD=password123 -e MYSQL_DATABASE=wordpress_db -v "%cd%/db:/var/lib/mysql" mysql:5.7

docker run -d --name wordpress-site --network net-wp -p 9500:80 -e WORDPRESS_DB_HOST=mysql-db -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=password123 -e WORDPRESS_DB_NAME=wordpress_db -v "%cd%/www:/var/www/html" wordpress:latest
# COMPLETAR CON EL COMANDO COMANDO

### Para que persista la información es necesario conocer en dónde mysql almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/
En el esquema del ejercicio carpeta del contenedor (a) es /var/lib/mysql

Ruta carpeta host: .../ejercicio3/db

### ¿Qué contiene la carpeta db del host?
La base de datos: Una carpeta llamada wordpress_db. 

Archivos de sistema: Carpetas como mysql y performance_schema. 

Archivos de datos: Archivos grandes como ibdata1 e ib_logfile
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Crear un contenedor con la imagen mysql:8  en la red net-wp, configurar las variables de entorno: MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER y MYSQL_PASSWORD
docker run -d --name mysql-db --network net-wp -e MYSQL_ROOT_PASSWORD=root_pass -e MYSQL_DATABASE=wordpress_db -e MYSQL_USER=anna_user -e MYSQL_PASSWORD=user_pass -v "%cd%/db:/var/lib/mysql" mysql:8


# COMPLETAR CON EL COMANDO

### ¿Qué observa en la carpeta db que se encontraba inicialmente vacía?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Para que persista la información es necesario conocer en dónde wordpress almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/
En el esquema del ejercicio la carpeta del contenedor (b) es (COMPLETAR CON LA RUTA)

Ruta carpeta host: .../ejercicio3/www

### Crear un contenedor con la imagen wordpress en la red net-wp, configurar las variables de entorno WORDPRESS_DB_HOST, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD y WORDPRESS_DB_NAME (los valores de estas variables corresponden a los del contenedor creado previamente)
# COMPLETAR CON EL COMANDO

### Personalizar la apariencia de wordpress y agregar una entrada

### Eliminar el contenedor y crearlo nuevamente, ¿qué ha sucedido?

# COMPLETAR CON LA RESPUESTA A LA PREGUNTA 

