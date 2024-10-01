# Herramienta Hydra para simular 2 ataques por fuerza bruta con diccionarion

## Instalación OpenSSH y configuración del servidor

![image](https://github.com/user-attachments/assets/8372b988-fd0d-49d3-822c-ce2b372d1a2f)

  - Para poder instalar OpenSSH deberemos introducir el siguiente comando: sudo apt install openssh-server

![image](https://github.com/user-attachments/assets/28f39952-fb46-4892-8d2c-67285812279f)

  - Con el comando "sudo systemctl status ssh" podremos comprobar el estado en el que está nuestro servidor de OpenSSH

![image](https://github.com/user-attachments/assets/1e7f6324-6e5d-41a2-9389-916e2f164cbe)

  - Con el comando "sudo systemctl start ssh" iniciaremos el servicio

![image](https://github.com/user-attachments/assets/c89aed3d-74e2-429d-bc16-dd84d4940445)

  - Con el comando "sudo systemctl enable ssh" empezaremos a correr el servicio en nuestra máquina

## Crear un usuario en SSH

![image](https://github.com/user-attachments/assets/617c7c98-36ea-4216-9d20-8aea309f5250)

  - Crearemos un nuevo usuario con el siguiente comando: sudo adduser usuario_objetivo. Nos pedirá que pongamos los datos relevantes para el nuevo usuario tales como el Nombre, la contraseña y alguno más.

## Conectar al servidor SSH

![image](https://github.com/user-attachments/assets/6af85331-18a6-4bab-82d7-deace517483f)

  - Para conectarnos con el servidor SSH una vez creado el usuario deberemos introducir el siguiente comando: ssh usuario_objetivo@localhost

## Simular un ataque de fuerza bruta utilizando Hydra y tu diccionario

![image](https://github.com/user-attachments/assets/a3e66ea0-f649-4c7f-b425-928917998b45)

  - En primer lugar instalaremos Hydra para poder avanzar

![image](https://github.com/user-attachments/assets/36a621f7-94da-4e68-9ba7-9024711c9b8c)

  - Una vez instalada Hydra, procederemos a introducir el siguiente comando para ejecutar el ataque: hydra -l usuario_objetivo -P /home/alvaro/Desktop/diccionarion.txt ssh://localhost. Con este comando Hydra intentará todas las combinaciones posibles del diccionario para acceder a la cuenta SSH del usuario.

![image](https://github.com/user-attachments/assets/13419478-63bf-484f-b96c-e2200ac8dd3c)

  - Aquí vemos como Hydra ha comenzado el ataque para descifrar la contraseña

![image](https://github.com/user-attachments/assets/29d1e510-f880-4283-8fe7-8f81dc0c148a)

  - Aquí vemos como Hydra ha conseguido descifrar la contraseña ya que nos muestra un mensaje con éxito.

## Revisar los logs del sistema para analizar los intentos de conexión

![image](https://github.com/user-attachments/assets/da5401f5-5bfd-4a5b-b10e-5bbd60a43dbf)

  - Una vez ejecutado el ataque, revisa los logs para ver los intentos de acceso fallidos: sudo tail -f /var/log/auth.log

# Utilizar diccionarion con Hydra para simular un ataque de fuerza bruta con HTTP (formulario web)

## Instalar y configurar DVWA(https://github.com/digininja/DVWA)

![image](https://github.com/user-attachments/assets/1babc0c8-914a-4add-ba15-98981a678d06)

  - Utilizaremos el siguiente comando para clonar el repositorio de DVWA: git clone https://github.com/digininja/DVWA.git

![image](https://github.com/user-attachments/assets/80d9fa37-a061-4400-918f-20e451702dfc)

  - Utilizaremos el siguiente comando para mover DVWA al directorio de tu servidor web: sudo mv DVWA /var/www/html/

![image](https://github.com/user-attachments/assets/c5060166-0dda-4be2-bf96-883b785a686b)

  - Utilizaremos los siguientes comandos para configurar los permisos de los archivos:
      - sudo chown -R www-data:www-data /var/www/html/DVWA
      - sudo chmod -R 755 /var/www/html/DVWA

![image](https://github.com/user-attachments/assets/09afd09b-786d-45e1-be07-5605c9f618d0)

  - Deberemos crear una Base de Datos para DVWA y un usuario con permisos. Para ello introduciremos los siguientes comandos:
      - CREATE DATABASE dvwa;
      - CREATE USER 'dvwauser'@'localhost' IDENTIFIED BY 'password';
      - GRANT ALL PRIVILEGES ON dvwa.* TO 'dvwauser'@'localhost';
      - FLUSH PRIVILEGES;
      - exit;

![image](https://github.com/user-attachments/assets/f29c1cc1-b68c-4c2a-a086-ada2c230da31)

  - Si queremos comprobar que los datos registrados en la Base de Datos están guardados ejecuraremos los siguientes comandos:
      - SHOW DATABASES;
      - SELECT User, Host FROM mysql.user;
      - SHOW GRANTS FOR 'dvwauser'@'localhost';

![image](https://github.com/user-attachments/assets/3669494d-2005-48b2-9188-f54023d42d6c)

  - Crearemos una copia del archivo config.inc.php.dist llamado config.inc.php para poder realizar unas modificaciones lo cual nos perimitirá después abrir la web de la página DVWA y poder editarla para facilitar la respuesta del ataque.

![image](https://github.com/user-attachments/assets/d3d171e7-b9b5-4986-8dd2-0daaf9435767)

  - Una vez esté creada la Base de Datos con los datos que nos piden a cerca de DVWA podremos acceder a la misma introduciendo la contraseña.

![image](https://github.com/user-attachments/assets/b0f77d05-491e-443f-84bc-8f046eccec6e)

  - Nos iremos al buscador de Internet y colocaremos la siguiente dirección: http://localhost/DVWA/setup.php para acceder al configurador de la páquina web de DVWA.

![image](https://github.com/user-attachments/assets/9a6388f5-c133-4b60-897d-bb3be334fba2)

  - Ya tendremos acceso a la Página web de DVWA sobre la que realizar el ataque.

![image](https://github.com/user-attachments/assets/5e12b53e-6956-44dc-bf30-a04d9c64efd2)

  - Nos meteremos en el archivo de configuración de php.ini ubicado en /etc/php/8.2/apache2 para cambiar un parámetro necesario para continuar con el ataque.

![image](https://github.com/user-attachments/assets/6dc36eea-0b10-4259-b206-cb554e1cc90b)

  - Deberemos configurar el parámetro "allow_url_include" y cambiarlo de OFF a ON.

![image](https://github.com/user-attachments/assets/a6bc9e97-8583-4bf6-9821-ea6077f21717)

  - Deberemos ejecutar el siguiente comando para dar permisos de www como usuario de datos de tal forma que pueda funcionar todo correctamente: sudo chown www-data: /var/www/html/DVWA/hackable/uploads

![image](https://github.com/user-attachments/assets/6bbf5f61-fc53-46ad-bf66-9b28a507dd59)

  - De la misma forma introduciremos el siguiente comando para dar permisos al archivo de configuración de DVWA: sudo chown www-data: /var/www/html/DVWA/config

![image](https://github.com/user-attachments/assets/2e9f3362-7549-429f-be6d-8da481de5335)

  - Nos tenemos que ir a la web de DVWA y acceder con el usuario y la contraseña. Después nos iremos a la pestaña de "CSRF" y cambiaremos la contraseña a 123

![image](https://github.com/user-attachments/assets/4ea94a3d-fbbb-4cc4-aa68-4558b4e02c78)

  - Crearemos un nuevo diccionario en el que la última opción sea la contraseña real de DVWA (123 en nuestro caso)

![image](https://github.com/user-attachments/assets/d8046a63-37a9-4870-a92d-979c90da1f0f)

  - Ejecutaremos el ataque mediante el siguiente comando: hydra -l admin -P /home/alvaro/Desktop/diccionario_numeros.txt http-get://127.0.0.1/DVWA/login.php
