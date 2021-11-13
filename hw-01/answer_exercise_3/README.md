
# 1- Creamos el volumen "statis_content"

Docker volume create static_content



# 2- Construimos la imagen del Dockerfile (desde el directorio donde se encuentra el archivo)
# Le damos el nombre "imagen3" con la opción -t

Docker build -t imagen3 .



# 3 - Ejecutamos un contenedor con la imagen3 creada anteriormente y persistimos el contenido de la carpeta html de la imagen de ngnix en el volumen "static_content"
# Con la opcion --name contenedor3, le damos un nombre personalizado al contenedor
# Con la opcion -d corremos el contenedor en segundo plano
# Con la opcion -p le indicamos que queremos que se ejecute en el puerto 8080 de nuestro localhost y apuntando al puerto 80 del contenedor
# Con la opción -v persistimos el contenido de la carpeta html de la imagen ngnix, en el volumen static_content

Docker run -d --name contenedor3 -p 8080:80 -v static_content:/usr/share/nginx/html/ imagen3

