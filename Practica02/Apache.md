# Apartado 1  
  ## **Preparación del sistema**<br/>
   ![Actualizamos Ubuntu y comprobamos la versión](./Imagenes/1.png)
  > Comprobación de la versión del sistema </br>
  ```lsb_release -a```

# Apartado 2
  ## **Instlación de Apache**
   ![Versión de Apache](./Imagenes/2.png)
  > Comprobación de la versión instalada

 **_Pregunta: ¿Qué paquetes se han instalado como dependencias?_** <br/>
 👉 Automáticamente se nos instalan: libfwupd2 y libgusb2
 
# Apartado 3
 ## **Comprobación del sistema**
  ### _Estado del servicio_
   ![Estado del servicio](./Imagenes/3.png)
  >``sudo systemctl status apache2``

  ## _Puertos en escucha_
  ![Puertos de escucha](./Imagenes/4.png)
 (_sudo ss -tulpn | grep apache2_)

  ## _Prueba desde el terminal y desde el navegador_
  ![Curl](./Imagenes/5.png)
 >(_curl -I http://localhost_) & Página por defecto en el navegador

  ## _Firewall_
  ![Firewall](./Imagenes/6.png)
   > (_sudo ufw status_)<br/>
   > (_sudo ufw allow 'Apache'_)

   **_Pregunta: ¿Qué diferencia hay entre los perfiles Apache, Apache Full y Apache Secure?_** <br/>
 👉 Se diferencian por los puertos 

 # Apartado 4
 | **Comando**                           | **Función**                                     |
 |---------------------------------------|-------------------------------------------------|
 | _sudo systemctl start apache2_        |  Inicia el servicio                             | 
 | _sudo systemctl stop apache2_         |  Detiene el servicio                            |
 | _sudo systemctl restart apache2_      |  Reinicia (corta conexiones)                    | 
 | _sudo systemctl reload apache2_       |  Recarga la configuración sin cortar conexiones |
 | _sudo systemctl enable apache2_       |  Arranque automático al iniciar el sistema      |
 | _sudo systemctl disable apache2_      |  Desactiva el arranque automático               |
 | _apache2ctl configtest_               |  Comprueba la sintaxis de la configuración      |
 | _apache2ctl -s_                       |  Muestra los sitios (virtual hosts) cargados    |
 | _apache2ctl -M_                       |  Lista los módulos cargados                     |
 | _a2enmod / a2dismod_                  |  Activa / Desactiva módulos                     |
 | _a2ensite / a2dissite_                |  Activa /Desactiva sitios                       |
 | _a2enconf / a2disconf_                |  Activa / Desactiva fragmentos de configuración |

   **_Pregunta: ¿Cuándo conviene usar ***reload*** en lugar de ***restart***?_** <br/>
 👉 _Reload_ conviene usarlo cuando no queremos cortar las conexiones, es decir, mantener el servidor funcionando

# Apartado 5
  ## _Exploración de la estructura de configuración_
> _ls -l /etc/apache2/

 | **Ruta*                               | **Descripción**                                 |
 |---------------------------------------|-------------------------------------------------|
 | _/etc/apache2/apache2.conf_           |  En este fichero se realizan las configuraciones de apache| 
 | _/etc/apache2/ports.conf_             |  En este fichero se hacen las configuraciones de los puertos por los que Apache va a escuchar|
 | _/etc/apache2/sites-available/_       |  Aquí se almacenan todos los sitios disponibles, activos e inactivos| 
 | _/etc/apache2/sites-enabled/_         |  En este solo se muestran los sitios activos      |
 | _/etc/apache2/mods-available/ y mods-enabled/_  |  Aquí encontramos los modulos disponibles y en el segundo encontramos los habilitados|
 | /etc/apache2/conf-available/ y conf-enabled/_      |  Aquí podemos revisar la configuración disponible y en el segundo la habilitada |
 | _/etc/apache2/envvars_                |  Aquí revisamos las variables                     |
 | _/var/www/html/_                      |  Se trata del directorio raiz|
 | _/var/log/apache2/access.log_         |  Aquí se registran los accesos |
 | _/var/log/apache2/error.log_          |  Aquí se guardan los errores|

   ## _Comprobación de los enlaces simbólicos de sites-enable_
  ![Contenido /etc/apache2/](./Imagenes/7.png)
  > _ls -l -7etc-7apache2/sites-enabled/_

   **_Pregunta: ¿Por qué Apache usa los enlaces simbólicos entre los directorios *-available y *-enabled?_** <br/>
 👉 De esta forma se evitan versiones desactualizadas  y fácilitan la la baja temporal del servicio.

# Apartado 6
  ## _Hacer copias de seguridad_
  ![Copia de seguridad](./Imagenes/8.png)
  > _sudo cp /etc/apache2/apache2.conf /etc/apache2/apache2.conf.bak_
  ## _Cambiar la página de inicio_
  > _echo "< h1 >Servidor de TU NOMBRE < /h1 >" | sudo tee /var/www/html/index.html_
