### 1. Crea un tablespace anomenat 'ts1' situat a /discs-mysql/disc1/ i col·loca les taules actor, address i category de la BD Sakila.  
Primero cargamos nuevamente la bbdd sakila ya que la eliminamos en el apartado anterior, para ello ejecutamos la siguiente línia desde mysql:  
> $ source /root/sakila.sql;  
> ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici4/Captura1.JPG)  

Creamos el directorio:  
> $ mkdir /discs-mysql/disc1  
> $ chmod 751 /discs-mysql/disc1  
> $ chown mysql:mysql /discs-mysql/disc1  
> ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici4/Captura2.JPG)  
  
Creamos el tablespace ‘ts1’ en la ubicación /discs-mysql/disc1 y asignamos 	las tablas actor, address y category a ‘ts1’:  
> $ CREATE TABLESPACE `ts1` ADD DATAFILE '/discs-mysql/disc1/ts1.ibd' Engine=InnoDB;   
> $ ALTER TABLE actor TABLESPACE ts1;  
> $ ALTER TABLE address TABLESPACE ts1;  
> $ ALTER TABLE category TABLESPACE ts1;  
> ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici4/Captura3.JPG)  
  
### 2. Crea un altre tablespace anomenat 'ts2' situat a /discs-mysql/disc2/ i col·loca-hi la resta de taules.  
Creamos el directorio:  
> $ mkdir /discs-mysql/disc2  
> $ chmod 751 /discs-mysql/disc2  
> $ chown mysql:mysql /discs-mysql/disc2  
> ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici4/Captura4.JPG)  
  
Creamos el tablespace ‘ts2’ en la ubicación /discs-mysql/disc2 y asignamos 	todas las tablas excepto actor, address y category a ‘ts2’:  
> $ CREATE TABLESPACE `ts2` ADD DATAFILE '/discs-mysql/disc2/ts2.ibd' Engine=InnoDB;  
> ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici4/Captura8.JPG)    
    
Para poder asignar las tablas correspondientes primero debemos saber que tablas hay en la base de datos. La comanda SHOW TABLES nos muestra todas las 	tablas però también las vistas:  
> ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici4/Captura5.JPG)    
    
Esto se aprecia más si lo comparamos con la siguiente captura:  
> ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici4/Captura6.JPG)    
  	 
Con la comanda siguiente podríamos seleccionar únicamente las tablas:  
> $ show full  tables where Table_Type != ‘VIEW’;  
> ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici4/Captura7.JPG)  
  
Ahora que ya sabemos cuales son las tablas ejecutamos las siguientes 	comandas:  
>	$ ALTER TABLE city TABLESPACE ts2;  
>	$ ALTER TABLE country TABLESPACE ts2;  
>	$ ALTER TABLE customer TABLESPACE ts2;  
>	$ ALTER TABLE film TABLESPACE ts2;  
>	$ ALTER TABLE film_actor TABLESPACE ts2;  
>	$ ALTER TABLE film_category TABLESPACE ts2;  
>	$ ALTER TABLE film_text TABLESPACE ts2;  
>	$ ALTER TABLE inventory TABLESPACE ts2;  
>	$ ALTER TABLE language TABLESPACE ts2;  
>	$ ALTER TABLE payment TABLESPACE ts2;  
>	$ ALTER TABLE rental TABLESPACE ts2;  
>	$ ALTER TABLE staff TABLESPACE ts2;  
>	$ ALTER TABLE store TABLESPACE ts2;  
> ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici4/Captura9.JPG)  
  
### 3. Comprova que pots realitzar operacions DML a les taules dels dos tablespaces.  
Insertamos 1 registro en la tabla actor(tablespace ‘ts1’):  
> ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici4/Captura10.JPG)   
   
Insertamos 3 registros en la tabla country (tablespace ‘ts2’):  
> ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici4/Captura11.JPG)  
  
### 4. Quines comandes i configuracions has realitzat per fer els dos apartats anteriors?  
  
***
[Torna enrere](https://github.com/Josep88/MP10UF2-A3)
