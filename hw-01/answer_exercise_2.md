------------------------------------------------------------------------
  ## Indica la diferencia entre el uso de la instrucción ADD y COPY ##
------------------------------------------------------------------------

COPY y ADD son instrucciones que tienen propósitos similares. Permiten copiar archivos/directorios desde una ubicación específica a una imagen de Docker.

ADD <src> <dest>    o    COPY <src> <dest>

Donde <src> es la URL donde se encuentra lo que queremos copiar y <dest> es el path de destino donde queremos copiarlo.

ADD /source/file/path  /destination/path    o    COPY /source/file/path  /destination/path

--------------------

En el caso de ADD, una de sus caracteristicas es que puede copiar ficheros de una URL externa, descargando el fichero y copiandolo en la imagen.

ADD http://source.file/url  /destination/path

Además, también puede copiar archivos comprimidos (solo los que se encuentran en local): extrae automaticamente el contenido y lo copia. 

ADD source.file.tar.gz /destination/path

--------------------
  
En el caso de COPY, solo se puede utilizar para archivos almacenados localmente, no se puede usar con URLs para copiar archivos externos.
Además, solo permite copiar los archivos en su forma existente, por lo que no descomprime archivos comprimidos, aunque sí los copia sin extraer su contenido.
 
COPY /source/file/path  /destination/path 
  


El hecho de que ADD tenga tantas funcionalidades puede ser problematico porque se puede comportar de manera impredecible, y copiar en vez de extraer o extraer en lugar de copiar. 



