# SIMULACIÓN DE ATAQUES EN KALI PURPLE

## Instalar las herramientas Pydictor y DyMerge en nuestras máquinas de Linux-Purple:

### Pydictor:



Nos descargaremos los repositorios de Pydictor manualmente desde Github desde el siguiente comando: wget https://github.com/landgrey/pydictor/archive/refs/heads/master.zip



Descomprimimos el archivo .zip. Esto creará un directorio llamado pydictor-master.



Accederemos al repositorio descargado.



Ejecutaremos Pydictor directamente usando Python, para ello usaremos este comando a modo de comprobación: python3 pydictor.py -h.

### DyMerge:



Introduciremos el comando “sudo apt install python2” para tener la versión de python que nos permitirá instalar DyMerge al tener compatibilidad entre ambos.


Introduciremos el comando “git clone https://github.com/k4m4/dymerge.git ” para instalarnos la versión de DyMerge compatible.



Crear un Diccionario de Letras y otro de Números con Pydictor:

Diccionario de Números:




Para crear el diccionario de números tendremos que estar dentro de la ruta de pydictor - master e introducir el siguiente comando: python3 pydictor.py -base d -len 1 6 -o numeros_nuevo.txt. Utilizamos “-base d” dado que significa “decimal” para poder completar con números.

Diccionario de Letras:



Para crear el diccionario de letras tendremos que estar dentro de la ruta de pydictor - master e introducir el siguiente comando: python3 pydictor.py -base L -len 1 6 -o letras.txt. Utilizamos “-base L” dado que significa “Letter” para poder completar con Letras.


