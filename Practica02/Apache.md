# Apartado 1  
  ## **Preparación del sistema**<br/>
   ![Actualizamos Ubuntu y comprobamos la versión](./Imagenes/1.png)
  > Comprobación de la versión del sistema (_lsb_release -a_)

# Apartado 2
  ## **Instlación de Apache**
   ![Versión de Apache](./Imagenes/2.png)
  > Comprobación de la versión instalada

 **_Pregunta:¿Qué paquetes se han instalado como dependencias?_** <br/>
 👉 
 
# Apartado 3
 ## **Comprobación del sistema**
  ### _Estado del servicio_
   ![Estado del servicio](./Imagenes/3.png)
  >(_sudo systemctl status apache2_)

  ## _Puertos en escucha_
 (_sudo ss -tulpn | grep apache2_)

 ## _Prueba desde el terminal y desde el navegador_
 >(_curl -I http://localhost_) & Página por defecto en el navegador

 ## _Firewall_
  ![Firewall](./Imagenes/4.png)
 > (_sudo ufw status_)<br/>
 > (_sudo ufw allow 'Apache'_)

 **_Pregunta:¿Qué diferencia hay entre los perfiles Apache, Apache Full y Apache Secure?_** <br/>
 👉 

 # Apartado 4
 
