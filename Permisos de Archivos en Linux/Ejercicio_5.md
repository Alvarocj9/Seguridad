# Ejercicio 5: Implementación de ACLs
  - Queremos que birmingan3 pueda leer un archivo especifico dentro de un nuevo directorio que se tiene que crear llamado archivos_criticos, pero sin poder modificarlo.
Habilita ACLs en el sistema si no están habilitadas (si ya lo están, omite este paso):
![image](https://github.com/user-attachments/assets/3e019a18-76fb-4799-90c7-8e10c3f8ba11)
    - Accederemos a el archivo con el comando "sudo nano /etc/fstab"
  - Crea un archivo llamado osaka.txt dentro de archivos_criticos:
![image](https://github.com/user-attachments/assets/2ae03712-5dc1-4524-ba01-c92a0a1fd71a)
  - Añade una ACL para que birmingan3 pueda leer el archivo osaka.txt, pero no modificarlo:
![image](https://github.com/user-attachments/assets/549dfd52-b655-4e04-9b88-e668e91ff32c)
  - Verifica y muestra las ACLs del archivo:
![image](https://github.com/user-attachments/assets/b103b4bb-7a0c-45cc-ba8a-25348c897efa)
## Preguntas:
### ¿Cómo afectan las ACLS al comportamiento de permisos tradicionales?
  - Las ACLs permiten un control de acceso más granular en comparación con los permisos tradicionales de propietario, grupo y otros. Con ACLs, puedes definir permisos específicos para usuarios o grupos adicionales más allá de los tres niveles de permisos tradicionales.
  - Esto significa que puedes otorgar diferentes niveles de acceso a diferentes usuarios sin cambiar el propietario o grupo del archivo. Por ejemplo, puedes permitir que un usuario específico tenga solo permisos de lectura mientras que otros usuarios en el mismo grupo no tienen acceso en absoluto.
### ¿Qué sucede si birmingan3 intenta modificar el archivo?
  - Si birmingan3 intenta modificar osaka.txt, recibirá un mensaje de error indicando que no tiene permisos para hacerlo. Esto se debe a que la ACL configurada le otorgó solo permisos de lectura (r--), y no permisos de escritura (w-).
