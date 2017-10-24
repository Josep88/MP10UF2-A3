### 1. Indica quins són els motors d’emmagatzematge que pots utilitzar (quins estan actius)? Mostra la comanda utilitzada i el resultat d’aquesta.  

Estan actius:  
InnoDB, MRG_MYISAM, MyISAM, BLACKHOLE, CSV, PERFORMANCE_SCHEMA, ARCHIVE i MEMORY.  
L’únic que no esta activat es el FEDERATED.  
> SHOW ENGIES;  
>  ![11]()  

### 2. Com puc saber quin és el motor d’emmagatzematge per defecte. Mostra com canviar aquest paràmetre de tal manera que les noves taules que creem a la BD per defecte utilitzin el motor MyISAM?  

Amb la comanda anterior es pot veure a la columna Support, està per defecte InnoDB.  
>  ![11]()  
  
Per canviar el motor a MyISAM utilitzem aquesta comanda:  
> SET default_storage_engine=MyISAM;  
> ![12]()  

### 3. Explica els passos per instal·lar i activar l'ENGINE MyRocks. MyRocks és un motor d'emmagatzematge per MySQL basat en RocksDB (SGBD incrustat de tipus clau-valor).  


### Checkpoint: Mostra al professor que està instal·lat i posa un exemple de com funciona.  


### 4. Importa la BD Sakila com a taules MyISAM. Fes els canvis necessaris per importar la BD Sakila perquè totes les taules siguin de tipus MyISAM.   
### Mira quins són els fitxers físics que ha creat, quan ocupen i quines són les seves extensions. Mostra'n una captura de pantalla i indica què conté cada fitxer.  



***
[Torna enrere](https://github.com/Josep88/MP10UF2-A3)
