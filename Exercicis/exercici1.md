### 1. Indica quins són els motors d’emmagatzematge que pots utilitzar (quins estan actius)? Mostra la comanda utilitzada i el resultat d’aquesta.  

Estan actius:  
InnoDB, MRG_MYISAM, MyISAM, BLACKHOLE, CSV, PERFORMANCE_SCHEMA, ARCHIVE i MEMORY.  
L’únic que no esta activat es el FEDERATED.  
> SHOW ENGINES;  
>  ![11]()  

### 2. Com puc saber quin és el motor d’emmagatzematge per defecte. Mostra com canviar aquest paràmetre de tal manera que les noves taules que creem a la BD per defecte utilitzin el motor MyISAM?  

Amb la comanda anterior es pot veure a la columna Support, està per defecte InnoDB.  
>  ![11]()  
  
Per canviar el motor a MyISAM utilitzem aquesta comanda:  
> SET default_storage_engine=MyISAM;  
> ![12]()  

### 3. Explica els passos per instal·lar i activar l'ENGINE MyRocks. MyRocks és un motor d'emmagatzematge per MySQL basat en RocksDB (SGBD incrustat de tipus clau-valor).  

Confirmem la versió de Linux, que tenim. Per Centos ha de ser la 6 o la 7.  
>  ![410]()  
Instalem els fitxers d'instalació i els instal·lem:  
>  ![411]()  
En acabar la instal·lació ens ha d'apareixer aquest missatge.  
>  ![412]()  
Hi ha que executar l'script com a usuari root per donar al usuari root del MySQL els credencials per habilitar el RocksDB:  
>  ![413]()  
Ara ja esta instal·lat, ho podem comprovar amb aquesta comanda:  
>  ![414]()  
Feim la prova creant una base de dades i una taula amb l'engine de ROCKSDB:  
>  ![415]()  
>  ![416b]()  


### 4. Importa la BD Sakila com a taules MyISAM. Fes els canvis necessaris per importar la BD Sakila perquè totes les taules siguin de tipus MyISAM.   
### Mira quins són els fitxers físics que ha creat, quan ocupen i quines són les seves extensions. Mostra'n una captura de pantalla i indica què conté cada fitxer.  



***
[Torna enrere](https://github.com/Josep88/MP10UF2-A3)
