1. Importa la BD Sakila com a taules InnoDB. 
2. Quin/quins són els fitxers de dades? A on es troben i quin és la seva mida?
3. Canvia la configuració del MySQL perqurè:
Canviar la localització dels fitxers del tablespace de sistema per defecte a /discs-mysql/
Tinguem dos fitxers corresponents al tablespace de sistema.
Tots dos han de tenir la mateixa mida inicial (1MB) 
El tablespace ha de creixer de 1MB en 1MB.
Situa aquests fitxers (de manera relativa a la localització per defecte) en una nova localització simulant el següent:
/discs-mysql/disk1/primer fitxer de dades → simularà un disc dur
/discs-mysql/disk2/segon fitxer de dades → simularà un segon disc dur.
