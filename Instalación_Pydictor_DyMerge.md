# SIMULACIÓN DE ATAQUES EN KALI PURPLE

## Instalar las herramientas Pydictor y DyMerge en nuestras máquinas de Linux-Purple:

### Pydictor:

![image](https://github.com/user-attachments/assets/5b264ad3-ce7e-4a9d-9583-1b82d75ddf35)

  - Nos descargaremos los repositorios de Pydictor manualmente desde Github desde el siguiente comando: wget https://github.com/landgrey/pydictor/archive/refs/heads/master.zip
    

![image](https://github.com/user-attachments/assets/9ffef189-c668-4449-8359-558c6546efe1)

  - Descomprimimos el archivo .zip. Esto creará un directorio llamado pydictor-master.
    

![image](https://github.com/user-attachments/assets/218c806a-e73b-4967-8066-0c17b641a438)

  - Accederemos al repositorio descargado.
    

![image](https://github.com/user-attachments/assets/9fc4d27b-6e2b-441d-910f-b0433fb18853)
  
  - Ejecutaremos Pydictor directamente usando Python, para ello usaremos este comando a modo de comprobación: python3 pydictor.py -h.


### DyMerge:

![image](https://github.com/user-attachments/assets/175e8c41-0fbe-45a1-901c-09c22acc7360)

  - Introduciremos el comando “sudo apt install python2” para tener la versión de python que nos permitirá instalar DyMerge al tener compatibilidad entre ambos.

![image](https://github.com/user-attachments/assets/b3e0e47d-c289-47c8-9604-567fc9bf6a2d)

  - Introduciremos el comando “git clone https://github.com/k4m4/dymerge.git ” para instalarnos la versión de DyMerge compatible.

## Crear un Diccionario de Letras y otro de Números con Pydictor:

### Diccionario de Números:

![image](https://github.com/user-attachments/assets/3c58d86c-a7f5-4938-8900-228297aca90a)

  - Para crear el diccionario de números tendremos que estar dentro de la ruta de pydictor - master e introducir el siguiente comando: python3 pydictor.py -base d -len 1 6 -o numeros_nuevo.txt. Utilizamos “-base d” dado que significa “decimal” para poder completar con números.

### Diccionario de Letras:

![image](https://github.com/user-attachments/assets/19efe876-5f48-4ffb-9370-17954e4abe29)

  - Para crear el diccionario de letras tendremos que estar dentro de la ruta de pydictor - master e introducir el siguiente comando: python3 pydictor.py -base L -len 1 6 -o letras.txt. Utilizamos “-base L” dado que significa “Letter” para poder completar con Letras.


