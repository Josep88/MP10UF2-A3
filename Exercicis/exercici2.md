### 1. Importa la BD Sakila com a taules InnoDB.  
Nos logueamos en mysql con la comanda:  
> mysql -u root -ppatata  

Una vez dentro ejecuto la comanda:  
> source /home/asix/sakila.sql;  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura1.JPG)  

Ahora dentro de MySQL y una vez cargada la bbdd sakila ejecutamos la siguiente consulta:  
>	&nbsp;SELECT TABLE_NAME, ENGINE  
>		&nbsp;&nbsp;FROM information_schema.TABLES  
>	&nbsp;WHERE TABLE_SCHEMA = ‘sakila’;  

>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura2.JPG)   

### 2. Quin/quins són els fitxers de dades? A on es troben i quin és la seva mida?  
Los ficheros de datos son los ibdata. Por defecto sólo hay un fichero ibdata1 de 12MB autoextensible  
Desde mysql con la comanda SHOW VARIABLES LIKE ‘%data_file%’ podremos verlos:  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura3.JPG)  

Los ficheros los podemos encontrar en la ruta /var/lib/mysql:  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura4.JPG)  

### 3. Canvia la configuració del MySQL perqurè:  
### Canviar la localització dels fitxers del tablespace de sistema per defecte a /discs-mysql/  
Creamos el directorio  
> $ mkdir /discs-mysql/  

Le damos permisos a mysql de rw  
> $ chmod 751 /discs-mysql/  
> $ chown mysql:mysql  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura8.JPG)  

### Tinguem dos fitxers corresponents al tablespace de sistema.  
### Tots dos han de tenir la mateixa mida inicial (1MB)   
### El tablespace ha de creixer de 1MB en 1MB.  
Para poder crear la configuración debemos eliminar los redolog de la carpeta /var/lib/mysql:  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura5.JPG)  

En el fichero de configuración (/etc/percona-server.conf.d/mysqld.cnf) tendremos que añadir las siguientes líneas:  
> innodb_file_per_table=0  
> innodb_data_home_dir=/discs-mysql/  
> innodb_autoextend_increment=1  
> innodb_data_file_path=ibdata1:5M;ibdata2:5M:autoextend  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura6.JPG)  

### Situa aquests fitxers (de manera relativa a la localització per defecte) en una nova localització simulant el següent:  
### · /discs-mysql/disk1/primer fitxer de dades → simularà un disc dur  
### · /discs-mysql/disk2/segon fitxer de dades → simularà un segon disc dur.  
Creamos los directorios y le damos permisos a mysql (los mismos que tiene en la carpeta /var/lib/mysql)  
> $ mkdir /discs-mysql/disk1  
>	$ mkdir /discs-mysql/disk2  
> $ chmod 751 /discs-mysql/disk1  
>	$ chmod 751 /discs-mysql/disk2  
>	$ chown mysql:mysql /discs-mysql/disk1  
>	$ chown mysql:mysql /discs-mysql/disk2  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura9.JPG)  

En el fichero de configuración  (/etc/percona-server.conf.d/mysqld.cnf)  tendremos que añadir la siguiente línea:  
> innodb_data_file_path=disk1/ibdata1:5M;disk2/ibdata2:5M:autoextend  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura7.JPG)  

***
|[Anterior](https://github.com/Josep88/MP10UF2-A3/blob/master/Exercicis/exercici1.md)|[Inici](https://github.com/Josep88/MP10UF2-A3)|[Següent](https://github.com/Josep88/MP10UF2-A3/blob/master/Exercicis/exercici3.md)|
|:-:|:-:|:-:|
