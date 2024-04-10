## Descarga la imagen 'httpd' y comprueba que está en tu equipo.

![Alt text](imagenes/Screenshot_20240410_182824.png)

    El comando "docker pull httpd" descarga la imagen de Docker denominada "httpd" desde Docker Hub o el registro de imágenes configurado y la guarda localmente en el sistema.

## Crea un contenedor con el nombre 'asir_httpd'.

![Alt text](imagenes/Screenshot_20240410_183316.png)

    El comando ejecuta un contenedor de Docker en modo desatachado (-d) con una sesión interactiva (-i) y un terminal (-t), asignándole el nombre "asir_httpd", utilizando la imagen "httpd:latest" y ejecutando el shell "bash" dentro del contenedor.

## Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.

![Alt text](imagenes/Screenshot_20240410_184447.png)

    simplemente al comando anterior añadimos el parametro -p que hace referencia a los puertos y mapeamos el puerto 8000 para mi maquina local y el 80 de el contenedor.

## Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas.

![Alt text](imagenes/Screenshot_20240410_190517.png)

    Este comando ejecuta un contenedor Docker en modo desatachado (-d), mapeando el puerto 8000 del host al puerto 80 del contenedor (-p 8000:80), asignándole el nombre "asir_httpd", realizando un bind mount del directorio htdocs del directorio actual ($PWD) al directorio /usr/local/apache2/htdocs/ dentro del contenedor, utilizando la imagen "httpd:latest". 

## Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.

![Alt text](imagenes/Screenshot_20240410_190200.png)

    creamos un documento .html y lo formateamos.

![Alt text](imagenes/Screenshot_20240410_191216.png)

    accedemos desde nuestro navegador a http://localhost:8000/

![Alt text](imagenes/Screenshot_20240410_191307.png)

    hacemos click en el nombre de nuestra pagina y la muestra.

## Crea un contenedor 'asir_web1' que use este mismo directorio para 'htdocs' y el puerto 8000

![Alt text](imagenes/Screenshot_20240410_192232.png)

    (para crear este contenedor dado que esta usando el mismo puerto que el anterior tuve que parar el anterior contenedor)


    El comando ejecuta un contenedor Docker en modo desatachado (-d), mapeando el puerto 8000 del host al puerto 80 del contenedor (-p 8000:80), asignándole el nombre "asir_web1", realizando un bind mount del directorio htdocs del directorio actual ($PWD) al directorio /usr/local/apache2/htdocs/ dentro del contenedor, utilizando la imagen "httpd:latest".

## Utiliza Code para hacer un hola mundo en html

![Alt text](imagenes/Screenshot_20240410_192821.png)

## Crea otro contenedor 'asir_web2' con el mismo directorio y a otro puerto, por ejemplo 9080.

![Alt text](imagenes/Screenshot_20240410_193123.png)

    El comando ejecuta un contenedor Docker en modo desatachado (-d), mapeando el puerto 9080 del host al puerto 80 del contenedor (-p 9080:80), asignándole el nombre "asir_web2", realizando un bind mount del directorio htdocs del directorio actual ($PWD) al directorio /usr/local/apache2/htdocs/ dentro del contenedor, utilizando la imagen "httpd:latest".

## Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador:

![Alt text](imagenes/Screenshot_20240410_193248.png)

![Alt text](imagenes/Screenshot_20240410_193313.png)

![Alt text](imagenes/Screenshot_20240410_193555.png)

![Alt text](imagenes/Screenshot_20240410_193612.png)

    comprobamos que muestran las dos pagina accediendo desde nuestro navegador tanto a http://localhost:8000/ como a http://localhost:9080/