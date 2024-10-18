# Ejercicio 1: Gestión de Permisos en un Entorno de Trabajo Multiusuario
## Escenario:
Imagina que eres el administrador de un equipo de desarrollo con varios usuarios, y necesitas configurar los permisos de un proyecto compartido entre tres usuarios: monon1, tronko2 y birmingan3. Cada uno debe tener permisos especificos para un directorio de proyecto, de acuerdo con su rol
## Paso 1: Crear un entorno simulado de usuarios y grupos
  - Crea los tres usuarios y un grupo común llamado devEria2:
![image](https://github.com/user-attachments/assets/670f270c-4070-4b98-8bb0-88368b23588a)
  - Crea un directorio llamado di_recto para el proyecto y cambia el grupo propietario devEria2:
![image](https://github.com/user-attachments/assets/aaf4239a-dcef-447d-bfb3-94e4c056845c)
## Paso 2: Configuración de permisos básicos
  - Configura los permisos para que solo los usuarios del grupo devEria2 puedan escribir en el directorio:
![image](https://github.com/user-attachments/assets/13ee233e-7db0-4c9c-a05b-084e701f3b71)
  - Verifica mostrando los permisos del directorio:
![image](https://github.com/user-attachments/assets/9416467f-67c9-4a5e-a5cc-e67deb35ab1e)
## Paso 3: Configuración de permisos avanzados
  - monon1 debe tener permisos completos (lectura, escritura, ejecución) en todo el proyecto. Cambia el propietario del directorio a monon1:
![image](https://github.com/user-attachments/assets/685865d5-49e5-45f5-88bf-b2d91262139b)
  - Los otros dos usuarios del grupo solo deben poder leer y ejecutar archivos, pero no modificarlos. Cambia los permisos de modo que el grupo devEria2 solo tenga permisos de lectura y ejecución:
![image](https://github.com/user-attachments/assets/295c988d-0309-4f38-b3fd-cc8deb84aa2d)
## Preguntas:
### ¿Qué sucede si un usuario fuera del grupo devEria2 intenta acceder al directorio?
  - Si un usuario fuera del grupo devEria2 intenta acceder al directorio /di_recto, no podrá hacerlo. Con los permisos actuales (750), los usuarios que no sean el propietario (monon1) o miembros del grupo devEria2 no tienen permiso para leer, escribir ni acceder al directorio.
### ¿Qué sucede si tronko2 intenta modificar un archivo dentro del directorio?
  - Si el usuario sitronko2 intenta modificar un archivo dentro del directorio /di_recto, no podrá hacerlo. Con los permisos actuales, ni siquiera podrá entrar al directorio, ya que no tiene permisos de lectura, escritura ni ejecución en ese directorio.
