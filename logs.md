### ANALISIS DE LOGS ###

1. Log de Errores
2. Log Generales
3. Log de querys lentos
4. Log's binarios

### COMANDO PARA Logs binarios ###
docker exec nombre_base_datos mysqlbinlog /var/log/mysql/mysql-bin.000001 > mysq.sql

### Enlaces de interés ###
https://mariadb.com/kb/en/overview-of-mariadb-logs/
https://mariadb.com/kb/en/using-mysqlbinlog/