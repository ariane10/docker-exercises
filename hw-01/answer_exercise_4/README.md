
(Para este ejercicio usamos de base el dockerfile del ejercicio3)


Desde el directorio donde se encuentra el dokerfile del ejercicio4 construimos la imagen
Con la opción -t le damos un nombre personalizado a la imagen

docker build -t imagen4 . 



Montas el contenedor con la imagen que has creado antes
- Con la opción -d queremos que el contenedor se ejecute en segundo plano
- Con la opción --name le damos un nombre personalizado al contenedor
- Con la opción -p le indicamos que queremos que se ejecute en el puerto 8080 de nuestro localhost y el puerto 80 del contenedor

docker run -d --name contenedor4 -p 8080:80 imagen4

