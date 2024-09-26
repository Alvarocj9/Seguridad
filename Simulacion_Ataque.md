# Herramienta Hindra para simular 2 ataques por fuerza bruta con diccionarion

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

