# Pruebas Same Origin Policy
El presente repo es una serie de ejemplos para revisar los conceptos asociados al Same Origin Policy desde un punto de vista 100% práctico.

Se ha privilegiado la funcionalidad sobre la estética para no agregar capas de complejidad con tags html, estilos y código javascript más complejo que nos desvíen del objetivo principal.

Este proyecto de ejemplo acompaña la entrada de blog que está en [azuax.com](http://www.azuax.com) y corresponde a la temática de **web security** que estoy revisando.

## Configuración de prueba
Para seguir el ejemplo, te recomiendo utilizar apache y configurar 2 *virtualhosts* que funcionarán como distintos dominios (orígenes). Clona el repositorio en tu equipo (En Linux/apache ```/var/www/html/```) y en el navegador ingresa a [http://localhost/pruebas-sop/](http://localhost/pruebas-sop/)

### uno.local
```
<VirtualHost *:80>
        ServerName uno.local
        ServerAdmin webmaster@uno.local
        DocumentRoot /var/www/html/pruebas-sop/uno.local

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
### dos.local
```
<VirtualHost *:80>
        ServerName dos.local
        ServerAdmin webmaster@dos.local
        DocumentRoot /var/www/html/pruebas-sop/dos.local

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
### Tabla hosts
En tu tabla de hosts, tienes que configurar las referencias a tus dominios recién configurados. Por ejemplo en Linux/Apache:

```
# /etc/hosts
127.0.0.1   uno.local
127.0.0.1   dos.local
```

## Contribuciones
* __azuax__
  * Ejemplo 1. Iframe con mismo origen.
  * Ejemplo 2. Iframe con distinto origen.
  * Ejemplo 3. window.location, mismo origen.
  * Ejemplo 4. window.location, distinto origen.

¿Quieres aportar con ejemplos?
Envíame tu pull request y podemos agregarlo al repo. Tu nombre aparecerá en la lista de contribuciones.
