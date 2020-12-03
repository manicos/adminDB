### PROCESO ###

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
