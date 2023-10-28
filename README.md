# PilaLAMPen2niveles
## Creación y edición del VagrantFile y los ficheros de aprovisionamiento

### VagrantFile

### Script de la maquina SQL

### Script de la maquina Apache


### SECCIÓN VAGRANT
Tras completar el fichero VagrantFile y provisionarlo con los scrips correspondientes podemos poner en funcionamiento nuestras máquinas con `vagrant up`

Para comprobar el estado de las máquinas usamos `vagrant status`, siempre y cuando estemos en la ruta donde se encuentra nuestro Vagrant File.
Y finalmente para conectarnos a una de las dos máquinas, `vagrant ssh apache` o `vagrant ssh sql` (en mi caso).

### SECCIÓN MYSQL
1. Modificamos el fichero /etc/mysql/mariadb.conf.d/50-server.cnf de la siguiente forma
2. Siendo root (entramos a la base de datos con `sudo mysql -u root`) creamos un usuario con la ip de la maquina apache (192.168.3.14) con todos los permisos para poder acceder a ella desde la otra máquina.
3. Clonación del repositorio git
4. Descarga de la base de datos "database.sql" y carga en MARIADB.

### SECCIÓN APACHE
1. Creamos una carpeta y metemos todos los archivos .php que clonamos del repositorio que nos van a servir para administrar la base de datos
2. Editamos el fichero /etc/apache2/sites-available/000-default.conf para que el documento raíz que aparezca en la página web sea nuestra pequeña base de datos
3. Editamos el fichero config.php con los datos de nuestra base de datos de la siguiente forma
4. Y finalmente podemos entrar en nuestra base de datos lamp_db desde nuestro servidor apache con `mysql -u nombredeusuario -p -h ipdelamaquinasql`

