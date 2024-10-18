# Ejercicio 3: Gestión de Archivos Temporales con Sticky Bit
## Escenario:
  - Se ha creado un directorio temporal compartido entre todos los usuarios del sistema. Necesitas asegurarte de que los usuarios puedan crear y modificar sus propios archivos, pero no puedan eliminar o modificar los archivos de otros
usuarios.
## Paso 1: Crear un directorio temporal
  - Crea un directorio llamado tmp_rano en /tmp:
![image](https://github.com/user-attachments/assets/d6a3d17c-931e-4272-a5f5-6e0524e7fb10)
  - Cambia los permisos para que todos los usuarios puedan leer, escribir y ejecutar en el directorio:
![image](https://github.com/user-attachments/assets/67771046-1f42-4e1c-bac0-e16ae13ddda4)
## Paso 2: Aplicar el sticky bit
  - Aplica el sticky bit al directorio para evitar que los usuarios eliminen archivos de otros:
![image](https://github.com/user-attachments/assets/e5ab193c-8646-43bd-8281-e1a9d7d40b2b)
  - Verifica los permisos del directorio:
![image](https://github.com/user-attachments/assets/f0178f9e-80c6-41b6-af2a-1a0dc15923bd)
## Paso 3: Crear archivos de prueba
  - Cambia a monon1 y crea un archivo en el directorio temporal:
![image](https://github.com/user-attachments/assets/2e03ebbf-e7ee-4707-8860-3aaf7cd02591)
  - Cambia a birmingan3 y verifica si puede eliminar el archivo de monon1:
![image](https://github.com/user-attachments/assets/e25f0883-34a9-46a6-8e7c-01bb09793e32)
## Preguntas:
  - ¿Pudo birmingan3 eliminar el archivo de monon1? ¿Por qué?
      - No, birmingan3 no pudo eliminar el archivo creado por monon1 porque el sticky bit estaba aplicado en el directorio /tmp/tmp_rano. El sticky bit impide que un usuario elimine o renombre archivos creados por otros, incluso si los permisos del directorio permiten escritura.
  - ¿Cómo ayuda el sticky bit a mejorar la seguridad en directorios compartidos?
      - El sticky bit mejora la seguridad en directorios compartidos al evitar que los usuarios eliminen o modifiquen archivos de otros usuarios. Esto es útil en directorios como /tmp, donde muchos usuarios pueden tener permisos de escritura, asegurando que solo el propietario del archivo o el administrador del sistema pueda eliminar o modificar sus archivos.
