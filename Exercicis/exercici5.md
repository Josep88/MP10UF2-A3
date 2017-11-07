### 1. Com podem comprovar (Innodb Log Checkpointing):  
Amb la comanda:  
> SHOW ENGINE INNODB STATUS\G  
>  ![501](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici5/501.PNG)  
>  ![502](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici5/502.PNG)  
>  ![503](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici5/503.PNG)  
  
### - LSN (Log Sequence Number)  
>  ![504](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici5/504.PNG) 
  
### - L'últim LSN actualitzat a disc  
>  ![505](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici5/505.PNG) 
  
### - Quin és l'últim LSN que se li ha fet Checkpoint  
>  ![506](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici5/506.PNG) 
  
### 2.  Com podem mirar el número de pàgines modificades (dirty pages)? I el número total de pàgines?  
Per saber el número de pàgines modificades:
>  ![507](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici5/507.PNG) 
I pel total de pàgines:
>  ![508](https://raw.githubusercontent.com/Josep88/MP10UF2-A3/master/img/exercici5/508.PNG) 

***
[Torna enrere](https://github.com/Josep88/MP10UF2-A3)
