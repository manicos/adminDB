## PROCESO 1 ##
    Paso 1: Crear archivo .sh
    Paso 2: Copiar comando de respaldo
    Paso 3: Guardar archivo .sh
    Paso 4: Dar permiso de ejecución al archivo .sh con el comando chmod +x nombrearchivo
    Paso 5: Ejecutar crontab -e
    Paso 6: Establecer la periocidad con * * * * * y escribir la ruta del archivo .sh creado en el paso 1 al 3.
    Paso 7: Guarda cambios
    Paso 8: Nuestros respaldos ya están automatizados

### CONTENIDO ARCHIVO .sh
    find /home/backups/ -type f -mtime +30 -name '*.gz' -print0 | xargs -r0 rm --

    /usr/bin/docker exec db_basedatosclase_1 mysqldump --user root --password=myrootpassword clase | gzip > /home/backups/backup-$(date +%Y-%m-%d-%H.%M.%S).sql.gz

### COMANDOS A USAR
    - controb -e
    - vi
    - nano
    - chmod +x



## PROCESO 2 ##
    Paso 1: Generar un repositorio Git en la nube privado
    Paso 2: Generar SSH Key en instancia
    Paso 3: Copiar contenido de llave pública
    Paso 4: Agregar llave en repositorio GIT en la nube
    Paso 5: Clonar repositorio en instancia de la nube
    Paso 6: Modificar ruta de respaldos en instancia de la nube
    Paso 7: Crear archivo uploadgit.sh
    Paso 8: Otorgar permisos de ejecución al archivo uploadgit.sh
    Paso 9: Ejecutar el archivo uploadgit.sh para verificar su correcto funcionamiento.
    Paso 10: Adicionar tarea al crontab -e
    Paso 11: Revisar que se encuentren los respaldos en el repositorio Git en la nube

### CONTENIDO ARCHIVO uploadgit.sh
    cd /home/dbbackup
    git add .
    git commit -m 'Dialy backup'
    git push origin master

    Donde:
    Accedemos a la carpeta del repositorio local
    Hacemos un Stage o Add para indicar que todos los nuevos archivos serán cargados en el repositorio de la nube
    Hacemos un commit 
    Se cargan los nuevos respaldos en la nube

## Comandos a usar
    - ssh-keygen -t rsa
    - chmod +x
    - vi

### 