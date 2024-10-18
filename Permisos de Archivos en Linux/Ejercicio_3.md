# Ejercicio 3: Gestión de Archivos Temporales con Sticky Bit
## Escenario:
  - Se ha creado un directorio temporal compartido entre todos los usuarios del sistema. Necesitas asegurarte de que los usuarios puedan crear y modificar sus propios archivos, pero no puedan eliminar o modificar los archivos de otros
usuarios.
## Paso 1: Crear un directorio temporal
  - Crea un directorio llamado tmp_rano en /tmp:
![image](https://github.com/user-attachments/assets/d6a3d17c-931e-4272-a5f5-6e0524e7fb10)
  - Cambia los permisos para que todos los usuarios puedan leer, escribir y ejecutar en el directorio:
