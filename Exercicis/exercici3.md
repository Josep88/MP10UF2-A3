### Partint de l'esquema anterior configura el Percona Server perquè cada taula generi el seu propi tablespace en una carpeta anomenada tspaces (aquesta pot estar situada a on vulgueu). 
### 1. Indica quins són els canvis de configuració que has realitzat.
> $ mkdir /discs-mysql/tspaces  
> $ chmod 751 /discs-mysql/tspaces  
> $ chown mysql:mysql /discs-mysql/tspaces  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura10.JPG)  

En el fichero de configuración  (/etc/percona-server.conf.d/mysqld.cnf)  tendremos que añadir las siguientes líneas:  
> datadir= /discs-mysql/tspaces  
> innodb_file_per_table=1  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura11.JPG)  

### 2. Després del canvi què ha passat amb els fitxers que contenien les dades de la BD de Sakila? Fes les captures necesàries per complementar la resposta.  
Al cambiar la ruta en el fichero de configuración, los ficheros permanecerán en la antigua ubicación. No desaparecerán ni serán borrados.  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura12.JPG)   
   
Para poder borrar la bbdd sakila eliminaré los ficheros de la nueva ubicación ya que previamente copiamos todo el contenido del directorio /var/lib/mysql:  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura13.JPG)  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici2-3/Captura14.JPG)  
  
***
[Torna enrere](https://github.com/Josep88/MP10UF2-A3)
