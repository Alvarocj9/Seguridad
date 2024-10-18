# Ejercicio 4: Configuración de umask y Creación de Archivos Nuevos
## Escenario:
  - Quieres configurar el entorno de trabajo para que todos los archivos nuevos creados por los usuarios tengan permisos predeterminados restrictivos (sólo lectura y escritura para el propietario, sin acceso para el grupo y otros).
## Paso 1: Configurar umask
  - Verifica el valor actual de umask:
![image](https://github.com/user-attachments/assets/16c92d97-5773-420b-901e-a45dc0c9a3d9)
  - Cambia el valor de umask a 077 para que los archivos creados sean accesibles solo por el propietario:
![image](https://github.com/user-attachments/assets/800b7b0c-24dc-4d43-9237-adfc8d9abe87)
## Paso 2: Crear archivos de prueba
  - Crea un archivo nuevo llamado gomaesp_umask y verifica sus permisos:
![image](https://github.com/user-attachments/assets/b744e8f1-beec-475b-bd03-0788d25bf491)
## Paso 3: Restablecer umask
  - Si deseas restaurar el valor predeterminado de umask, puedes hacerlo:
![image](https://github.com/user-attachments/assets/218fa82b-69d4-4bbe-9fdb-efe0df3468c9)
## Preguntas:
### ¿Cómo afectó el valor de umask a los permisos de los nuevos archivos?
  - Con un umask de 077, los archivos se crean con permisos que permiten solo al propietario leer y escribir (permisos 600), y los directorios se crean con permisos que permiten solo al propietario leer, escribir y ejecutar (permisos 700).
  - Con un umask de 022, los archivos se crean con permisos que permiten al propietario leer y escribir, mientras que el grupo y otros solo tienen permisos de lectura (permisos 644 para archivos, 755 para directorios).
### ¿Cómo podrías usar umask para mejorar la seguridad de los archivos en un sistema multiusuario?
  - Usar un umask adecuado puede ayudar a proteger los archivos de acceso no autorizado en un entorno multiusuario. Algunas formas en que se puede hacer esto incluyen:
    - Establecer un umask restrictivo: Configurar un umask como 077 para que los nuevos archivos sean accesibles solo para el propietario. Esto es útil para proteger información sensible.
    - Modificar el umask para grupos específicos: Si se desea permitir el acceso a un grupo, se podría usar un umask de 027, permitiendo que los miembros del grupo tengan acceso de lectura y escritura mientras se bloquea el acceso para otros.
    - Aplicar umask en scripts de inicio de sesión: Incluir el comando umask en archivos de configuración del shell, como ~/.bashrc o /etc/profile, para asegurarse de que los usuarios tengan configuraciones seguras desde el inicio.
