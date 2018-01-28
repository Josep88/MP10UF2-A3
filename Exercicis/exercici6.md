### 1. Prepara un Servidor Percona Server amb la BD de Sakila  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/601.png)  

### 2. Prepara un segon servidor Percona Server a on hi hauran un conjunt de taules FEDERADES al primer servdor.  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/602.png)  

### 3. Per realitzar aquest link entre les dues BD podem fer-ho de dues maneres:  
### 3.1. Opció1: especificar TOTA la cadena de connexió a CONNECTION 
La línia de connexió s’han de posar el usuari creat anteriorment, la seva contrasenya, l’altre servidor (amb el hostname o la IP), el port, la base de dades i la taula federada: en el nostre cas: ‘  
> mysql://joel:patata@192.168.127.144:3306/sakila/prueba  

### 3.2. Opció2: especificar una connexió a un server a CONNECTION que prèviament s'ha creat mitjançant CREATE SERVER  
Com amb la línia de connection, a l’hora de crear el servidor haurem de donar-li: l’usuari creat anteriorment, la contrasenya, host (hostname o ip), port, base de dades.
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/603.png)  

### 3.3. Posa un exemple de 2 taules de cada opció. Tingues en compte els permisos a nivell de BD i de SO així com temes de seguretat com firewalls, etc...  
Línia de connexió:  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/604.png)  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/605.png)  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/606.png)  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/607.png)  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/608.png)  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/609.png)  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/610.png)  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/611.png)  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/612.png)  

Amb servidor creat:  
Sense les taules prueba i prueba2  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/613.png)  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/614.png)  

### 4. Detalla quines són els passos i comandes que has hagut de realitzar en cada màquina.  
Per poder fer aquest apartat he hagut de:  
1. Abans de configurar el mysql, he hagut de deshabilitar el Selinux i el firewall en els dos servidors:  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/615.png)  

Per el selinux, modificar l’arxiu /etc/sysconfig/selinux i substituir enforcing per disabled  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/616.png)  

2. Per defecte el engine FEDERATED està deshabilitat, per habilitar-lo haurem d’escriure federated a l’apartat MYSQLD de l’arxiu /etc/my.cnf  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/617.png)  

3. Ja dintre el MySQL crearem l’usuari que utilitzarem per connectar-nos i li donarem permisos:
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/618.png)  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/619.png)  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/620.png)  

4. Ja ho tenim tot preparat. ara hem de crear una taula, i crear la mateixa taula a l’altre servidor IDENTICA, però amb la línia de connexió o amb el servidor creat.  

Línia de connexió:  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/621.png)  

Amb el servidor:  
>  ![601](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici6/622.png)  


***
|[Anterior](https://github.com/Josep88/MP10UF2-A3/blob/master/Exercicis/exercici5.md)|[Inici](https://github.com/Josep88/MP10UF2-A3)|[Següent](https://github.com/Josep88/MP10UF2-A3/blob/master/Exercicis/exercici7.md)|
|:-:|:-:|:-:|
