# TAREA VOLÚMENES 

## Utilizando la imagen de Apache, tag 24, usa Visual Studio Code y Docker y escribe los comandos de cada instrucción.

### 1. Descarga la imagen 'httpd' y comprueba que está en tu equipo.

```
$ DOCKER PULL HTTPD: Descarga la imagen httpd
$ DOCKER IMAGE LS: Comprueba las imágenes descargadas
```

### 2. Crea un contenedor con el nombre 'dam_web1'.
```
$ DOCKER RUN -D --NAME DAM_WEB1 HTTPD: crea contenedor llamado dam_web1 con la imagen httpd
```
### 3. Si quieres poder acceder desde el navegador de tu equipo, ¿que debes hacer?.

Primero eliminamos el contenedor:
```
$ DOCKER RM DAM_WEB1: elimina contenedor llamado dam_web1
```
Creamos otra vez el contenedor mapeando el puerto de este con el del Host y con la direccion ip accedemos desde el navegador:
```
$ DOCKER RUN -DIT --NAME DAM_WEB1 -P 8080:80 HTTPD:2.4
$ IP ADDRESS: muestra la dirección ip del equipo -> 10.0.9.16:8080
```

### 4. Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas.

El directorio htdocs ya lo habíamos creado en ejercicios previos.
> [!IMPORTANT]
> Eliminamos el contenedor para que ejecute correctamente el siguiente comando:
```
DOCKER RUN -DIT --NAME DAM_WEBI1 -P 8080:80 -V /HOME/DAM2/SXE/APACHE/HTDOCS:USR/LOCAL/APACHE2/HTDOCS/ HTTP:2.4: 
```
Este comando ejecuta el contenedor asociando los puertos para poder acceder al servidor web del contenedor en el host
### 5.Realiza un 'hola mundo' en html (usa Code) y comprueba que accedes desde el navegador.

Editamos el archivo html con Visual Code y lo comprobamos:

http://172.17.0.1:8080/

### 6: Crea otro contenedor 'dam_web2' con el mismo volumen y a otro puerto, por ejemplo 9080.
```
DOCKER RUN -DIT --NAME DAM_WEB2 -P 9080:80 -V /HOME/DAM2/SXE/APACHE/HTDOCS:/USR/LOCAL/APACHE2/HTDOCS/ HTTP:2.4: 
```
Igual que en el ejercicio 4, ejecutamos el contenedor asociando los puertos para poder acceder al servidor web del contenedor en el host
### 7. Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador:
http://localhost:9080

http://localhost:8080

Desde el navegador verificamos que el contenido del archivo es el mismo en ambos servidores.

### 8. Realiza modificaciones de la página y comprueba que los dos servidores 'sirven' la misma página

Modificamos el archivo html y comprobamos que efectivamente se reflejan los cambios.


