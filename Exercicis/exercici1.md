### 1. Indica quins són els motors d’emmagatzematge que pots utilitzar (quins estan actius)? Mostra la comanda utilitzada i el resultat d’aquesta.  

Estan actius:  
InnoDB, MRG_MYISAM, MyISAM, BLACKHOLE, CSV, PERFORMANCE_SCHEMA, ARCHIVE i MEMORY.  
L’únic que no esta activat es el FEDERATED.  
> SHOW ENGINES;  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/11.PNG)  

### 2. Com puc saber quin és el motor d’emmagatzematge per defecte. Mostra com canviar aquest paràmetre de tal manera que les noves taules que creem a la BD per defecte utilitzin el motor MyISAM?  

Amb la comanda anterior es pot veure a la columna Support, està per defecte InnoDB.  
>  ![11](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/11.PNG)  
  
Per canviar el motor a MyISAM utilitzem aquesta comanda:  
> SET default_storage_engine=MyISAM;  
> ![12](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/12.PNG)  

### 3. Explica els passos per instal·lar i activar l'ENGINE MyRocks. MyRocks és un motor d'emmagatzematge per MySQL basat en RocksDB (SGBD incrustat de tipus clau-valor).  

Confirmem la versió de Linux, que tenim. Per Centos ha de ser la 6 o la 7.  
>  ![410](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/410.PNG)  

Instalem els fitxers d'instalació i els instal·lem:  
>  ![411](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/411.PNG)  

En acabar la instal·lació ens ha d'apareixer aquest missatge.  
>  ![412](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/412.PNG)  

Hi ha que executar l'script com a usuari root per donar al usuari root del MySQL els credencials per habilitar el RocksDB:  
>  ![413](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/413.PNG)  

Ara ja esta instal·lat, ho podem comprovar amb aquesta comanda:  
>  ![414](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/414.PNG)  

Feim la prova creant una base de dades i una taula amb l'engine de ROCKSDB:  
>  ![415](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/415.PNG)  
>  ![416b](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/416b.PNG)  


### 4. Importa la BD Sakila com a taules MyISAM. Fes els canvis necessaris per importar la BD Sakila perquè totes les taules siguin de tipus MyISAM.  

Al crear les taules, hi ha que modificar l'ENGINE:  
>  ![510](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/510.PNG)  
  
I ara la carreguem al MySQL:  
>  ![511](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/511.PNG)  

### Mira quins són els fitxers físics que ha creat, quan ocupen i quines són les seves extensions. Mostra'n una captura de pantalla i indica què conté cada fitxer.  

Comprovem a la carpeta /var/lib/mysql que ha creat la carpeta sakila:   
>  ![512](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/512.PNG)  
  
I el contingut de la carpeta sakila:  
>  ![513](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/513.PNG)  
  
Podem comprovar que hi ha fitxers amb les extensions:  
> - frm – Guarda la definició de la estructura de la taula  
> - MYD – Guarda el contingut de les taules, es a dir, files i dades  
> - MYI – Guarda els índexs de la taula  
> - opt – Tan sols hi ha el fitxer db.opt. Guarda les opcions de la base de dades.  
>  ![514](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/514.PNG)  
> - TRG – Indica la taula que conté triggers.  
> - TRN – Un fitxer per cada trigger.  
>  ![515](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici1/515.PNG)  

***
|[Inici](https://github.com/Josep88/MP10UF2-A3)|[Següent](https://github.com/Josep88/MP10UF2-A3/blob/master/Exercicis/exercici2.md)|
|:-:|:-:|
