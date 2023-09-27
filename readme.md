# TAREA VOLÚMENES 

## Utilizando la imagen de Apache, tag 24, usa Visual Studio Code y Docker y escribe los comandos de cada instrucción.

### 1. Descarga la imagen 'httpd' y comprueba que está en tu equipo.

```
DOCKER PULL HTTPD: Descarga la imagen httpd
DOCKER IMAGE LS: Comprueba las imágenes descargadas
```

### 2. Crea un contenedor con el nombre 'dam_web1'.
```
DOCKER RUN -D --NAME DAM_WEB1 HTTPD: crea contenedor llamada dam_web1 con la imagen httpd
```
### 3. Si quieres poder acceder desde el navegador de tu equipo, ¿que debes hacer?.

Primero eliminamos el contenedor:
```
DOCKER RM DAM_WEB1: elimina contenedor llamado dam_web1
```
Creo otra vez el contenedor mapeando el puerto de este con el del Host y así acceder desde el navegador:
```
DOCKER RUN -DIT --NAME DAM_WEB1 -P 8080:80 HTTPD:2.4
```

Lo buscamos desde el navegador escribiendo nuestra ip (ip address):

http://172.17.0.1:8080/

### 4. Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas.

Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/

La carpeta htdocs ya la habíamos creado en ejercicios previo. Volviendo a eliminar el docker para crearlo de nuevo;
```
DOCKER RUN -DIT --NAME DAM_WEBI1 -P 8080:80 -V /HOME/DAM2/SXE/APACHE/HTDOCS:USR/LOCAL/APACHE2/HTDOCS/ HTTP:2.4
```
### 5.Realiza un 'hola mundo' en html (usa Code) y comprueba que accedes desde el navegador.

Editamos el html con Visual Code y lo comprobamos con la ip en el navegador:

http://172.17.0.1:8080/




