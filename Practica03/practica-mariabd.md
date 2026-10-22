# Apartado 1  
  ## **Preparación del sistema**<br/>
   ![Comprobación de Apache](./Imagenes/1.png)
  > Comprobación de la versión de Apache</br>
  ```system is-active apache2```

# Apartado 2
  ## **Instalación de MariaBD y su comprobación**
  ![Versión](./Imagenes/2.png)
  > Comprobación de la versión </br>
  > ``mariadb --version``

# Apartado 3
  ## **Estado del servicio**
   ![Versión](./Imagenes/3.png)
  > ``sudo systenctl status mariadb``
   ![Base de datos](./Imagenes/4.png)
  >``systemctl is-enable mariadb``
  ## **Entrar en la base de datos**
   ![Base de datos](./Imagenes/5.png)
   > ``sudo mariadb``

# Apartado 4
 | **Comando**                           | **Función**                                     |
 |---------------------------------------|-------------------------------------------------|
 | _sudo systemctl start mariadb_        |  Inicia el servicio                             | 
 | _sudo systemctl stop mariadb_         |  Detiene el servicio                            |
 | _sudo systemctl restart mariadb_      |  Reinicia                                       | 
 | _sudo systemctl status mariadb_       |  Recarga la configuración sin cortar conexiones |
 | _sudo systemctl enable apache2_       |  Arranque automático al iniciar el sistema      |

# Apartado 5
  ## **Error al parar MariaDB**
  ![Base de datos](./Imagenes/6.png)
     ![Base de datos](./Imagenes/7.png) </br>
 **_Pregunta:  Si WordPress no pudiera conectar con la base de datos, ¿qué dos comandos de este apartado usarías
para saber si el problema es que MariaDB está parado?_** <br/>
 👉 Systemctl is-active mariabd

 # Apartado 7 
 ## **Instalación de PHP y las piezas que WordPress necesita**
   ![PHP](./Imagenes/8.png)
  ## **Comprobación PHP**
   ![mpm](./Imagenes/9.png)
  ## **Comprobación conexión MariaDB**
   ![Comp maria](./Imagenes/10.png)
  ## **Comprobación de que Apache ejecuta PHP**
  ![MARIADB](./Imagenes/11.png)

   **_Pregunta:  ¿Por qué es peligroso dejar info.php en un servidor real? ¿Para qué sirve el paquete php-mysql? ?_** <br/>
 👉 Estarías dando los datos necesarios para un acceso indeseado.
