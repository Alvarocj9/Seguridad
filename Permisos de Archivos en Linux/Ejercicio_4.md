Ejercicio 4: Configuración de umask y Creación de
Archivos Nuevos
Escenario:
Quieres configurar el entorno de trabajo para que todos los archivos nuevos creados por los usuarios tengan permisos predeterminados restrictivos (sólo lectura y escritura para el propietario, sin acceso para el grupo y otros).
.
Paso 1: Configurar umask
Verifica el valor actual de umask:
Cambia el valor de umaska 077 para que los archivos creados sean accesibles solo por el propietario:
Paso 2: Crear archivos de prueba
Crea un archivo nuevo llamado gomaesp_umask y verifica sus permisos:
Paso 3: Restablecer umask
Si deseas restaurar el valor predeterminado de umask, puedes hacerlo:
Preguntas:
¿Cómo afectó el valor de umask a los permisos de los nuevos archivos?
¿Cómo podrías usar umask para mejorar la seguridad de los archivos en un sistema multiusuario?
