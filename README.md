Examen MercadoLibre
El examen se trata de un magneto quiere reclutar la mayor cantidad de mutantes para poder luchar contra los X-Mens. 

Me ha contratado para que desarrolle un proyecto que detecte si un humano es mutante basándose en su secuencia de ADN. 
Para eso me ha pedido crear un programa con un método o función con la siguiente firma: 
             boolean isMutant(String[] dna); 
En donde recibirás como parámetro un array de Strings que representan cada fila de una tabla 
de (NxN) con la secuencia del ADN. Las letras de los Strings solo pueden ser: (A,T,C,G), las 
cuales representa cada base nitrogenada del ADN.


Sabrás si un humano es mutante, si encuentras más de una secuencia de cuatro letras iguales, de forma oblicua, horizontal o vertical. Ejemplo (Caso mutante):
 String[] dna = {"ATGCGA","CAGTGC","TTATGT","AGAAGG","CCCCTA","TCACTG"}; 
En este caso el llamado a la función isMutant(dna) devuelve “true”. 
Desarrolla el algoritmo de la manera más eficiente posible.


Creamos un API REST con postman creando el servicio “/mutant/” en donde se pueda detectar si un humano es mutante enviando la secuencia de ADN mediante un HTTP POST con un Json el cual tenga el siguiente formato:

 POST → /mutant/ 
"dna"={"ATGCGA","CAGTGC","TTATGT","AGAAGG","CCCCTA","TCACTG"}  Devuelve true

 POST → /mutant/ 
"dna"={"AAAATG","TGCAGT","GCTTCC","CCCCTG","GTAGTC","AGTCAC"}  Devuelve true

 POST → /mutant/ 
"dna"={"AGAATG","TGCAGT","GCTTCC","GTCCTC","GTAGTC","GGTCAC"}  Devuelve true

POST → /mutant/ 
"dna"={"AGTCAA","GTCACG","CTGGTA","ACTGCC","CCTAGT","AAGCAA"}  Devuelve false

POST → /mutant/ 
"dna"={"AGAATG","TACAGT","GCAGCC","TTGATG","GTAGTC","AGTCAA"}  Devuelve true

POST → /mutant/ 
"dna"={"AGTCAG","AAGTCC","CCTGGG","ATTCAA","CTTAGA","GTACCC"}  Devuelve false

POST → /mutant/ 
"dna"={"ATAATG","GTTAGT","GGCTCG","TTGATG","GTAGTC","AGTCAA"}  Devuelve true

POST → /mutant/ 
"dna"={"ATAATG","GTATGA","GCTTAG","TTTAGG","GTAGTC","AGTCAA"}  Devuelve false

POST → /mutant/ 
"dna"={ "ATGATG","GTCTTA","AATTGG","ACTAGT","GGAGTC","AGGCAA"}  Devuelve false

POST → /mutant/ 
"dna"={"TTTTTA","AAAATA","GGGGTA","CCCCTA","TATATA","ACGTAC"}  Devuelve true

En caso de verificar un mutante, debería devolver un HTTP 200-OK, en caso contrario un 
403-Forbidden.


Luego anexar una base de datos, la cual guarde los ADN’s verificados con la API.  
Solo 1 registro por ADN.  
Exponer un servicio extra “/stats” que devuelva un Json con las estadísticas de las 
verificaciones de ADN: 

{“count_mutant_dna”:6, “count_human_dna”:4: “ratio”:1.5} 



Subir el archivo a GitHub y conectar con render, se obtiene los siguientes links: 
-https://parcialdesarrollo-3k09-lee-50068.onrender.com
-https://parcialdesarrollo-3k09-lee-50068.onrender.com/mutant
-https://parcialdesarrollo-3k09-lee-50068.onrender.com/stats



Luego use la aplicación jmeter para realizar pruebas de estrés ((Entre 100 y 1 
millón de peticiones por segundo). 



Por último se realiza un test-automáticos y diagrama de secuencia
