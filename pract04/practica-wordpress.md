# Apartado 1
  ![hostname](./Imagenes/1.png)
> ``hostname -I`` </br>

  ![Comprobaciones](./Imagenes/2.png)
> ``systemctl is-active apache2 mariadb``
> ``php -v`` </br>

 **_Pregunta: ¿Qué dos "puertas" (programas y puertos) usas para trabajar con el servidor en esta práctica y para qué sirve cada una?_** <br/>
 👉

# Apartado 2
 ![Sitios activos](./Imagenes/3.png)
 > ```sudo a2dissite sitio1.conf sitio2.conf```
 >```sudo a2ensite 000-default.conf```
 > ```sudo apache2ctl configtest```
 > ```sudo systemctl reload apache2``` </br>
 
  ![ls](./Imagenes/4.png)
> ``ls /etc/apache2/sites-enabled/``
> ``grep DocumentRoot /etc/apache2/sites-enabled/000-default.conf``</br>

  ![http](./Imagenes/5.png)

 **_Pregunta: ¿Qué diferencia hay entre desactivar un sitio con a2issite y borrar sus ficheros? ¿Por qué ahora ves la página por defecto de Apache y antes veías sitio1?_** <br/>
 👉 Si borro los ficheros no podré volver a utilizarlos mientras que si los desactivo se quedan guardados para poder usarse. Respecto a la página de defecto Apache la veo porque no tiene página establecida

 
