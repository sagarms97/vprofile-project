#Mysql image
FROM mysql:8.0.33
LABEL project="vprofile"
ENV MYSQL_ROOT_PASSWORD="vpropass"
ENV MYSQL_DATABASE="accounts"
ADD db_backup.sql docker_entrypoint_initdb.d/db_backup.sql
