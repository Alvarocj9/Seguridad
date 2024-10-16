# Ejercicio 2: Control de Acceso con el Bit SGID en Directorios
## Escenario:
El equipo de desarrollo necesita colaborar en un subdirectorio dentro de di_recto. Queremos asegurarnos de que cualquier archivo creado en ese subdirectorio tenga automaticamente el mismo grupo propietario (devEria2), para facilitar la colaboración.
## Paso 1: Crear un subdirectorio para colaboración
  - Crea un subdirectorio llamado di_afano dentro de /di_recto:
![image](https://github.com/user-attachments/assets/4e74a9e9-c1a0-4103-8c4e-35f40399fb78)
  - Cambia el grupo propietario del subdirectorio a devEria2:
![image](https://github.com/user-attachments/assets/572b9b0e-b39c-4183-a035-290e8a790b47)
## Paso 2: Aplicar el bit SGID
  - Aplica el bit SGID al subdirectorio di_afano, para que todos los archivos creados en hereden el grupo propietario:
![image](https://github.com/user-attachments/assets/9dd10697-6ecf-4dea-b565-6ee3fa78eccf)
  - Verifica y muestra los permisos del subdirectorio:
![image](https://github.com/user-attachments/assets/3f616161-4e97-4387-928f-ed52694673b0)
## Paso 3: Crear archivos de prueba
  - Cambia a tronko2 y crea un archivo llamado archivo_tronko2.txt dentro del subdirectorio di_afano:
![image](https://github.com/user-attachments/assets/3d02a4f0-a6e4-480d-88d7-7f2fa154f0cd)
![image](https://github.com/user-attachments/assets/3179ddaa-dddb-4f07-8266-a4d32ba75fdc)
  - Verifica y muestra los permisos y el grupo propietario del archivo:
![image](https://github.com/user-attachments/assets/50a1e949-8a28-4a10-bc68-fce1d5a3a22a)
Preguntas:
• ¿Cuál es el grupo propietario del archivo creado por tronko2?
• ¿Qué ventaja aporte elbil SGID en un entomo de colaboración?
Ejercicio 3: Gestión de Archivos Temporales con Sticky
Bit Escenario:
Se ha creado un directorio temporal compartido entre todos los usuarios del sistema. Necesitas asegurarte de que los usuarios puedan creary modificar sus propios archivos, pero no pueden eliminar o modificar los archivos de otros
Usuarios.
Paso 1: Crear un directorio temporal
Crea un directorio famedo tmp_nen/tap
Cambia los permisos para que todos los usuarios puedan leer, escribir y ejecutar en el directorie
