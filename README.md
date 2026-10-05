\# MySQL Docker - ADSO318



Configuración de un contenedor MySQL 8.0 utilizando Docker Compose.



\## Requisitos



\- Docker Desktop en Windows o Docker Engine en Linux.

\- Docker Compose.

\- Conexión a Internet para descargar la imagen MySQL.



\## Características



\- \*\*Imagen:\*\* mysql:8.0

\- \*\*Contenedor:\*\* adso318

\- \*\*Puerto del equipo:\*\* 3308

\- \*\*Puerto interno:\*\* 3306

\- \*\*Volumen:\*\* mysql\_data

\- \*\*Reinicio automático:\*\* unless-stopped



\## Configuración



Crear un archivo `.env` en la misma carpeta que `compose.yaml`, con el siguiente contenido:



```env

MYSQL\_ROOT\_PASSWORD=TU\_CONTRASEÑA\_SEGURA

```



Reemplazar `TU\_CONTRASEÑA\_SEGURA` por una contraseña propia.



> Importante: no subir el archivo `.env` a GitHub ni compartir la contraseña.



\## Despliegue



Clonar el repositorio:



```bash

git clone https://github.com/adonet77/docker-adso318.git

cd docker-adso318

```



Crear el archivo `.env` con la contraseña y ejecutar:



```bash

docker compose up -d

```



\## Verificar el contenedor



```bash

docker ps

```



Consultar los registros:



```bash

docker logs adso318

```



\## Detener y reiniciar



Detener los servicios:



```bash

docker compose down

```



Iniciarlos nuevamente:



```bash

docker compose up -d

```



Los datos se almacenan en el volumen `mysql\_data`, por lo que detener y eliminar el contenedor con Docker Compose no elimina el volumen de forma predeterminada.



\## Conexión desde phpMyAdmin



\- \*\*Servidor:\*\* 127.0.0.1

\- \*\*Puerto:\*\* 3308

\- \*\*Usuario:\*\* root

\- \*\*Contraseña:\*\* la definida al inicializar MySQL



\## Almacenamiento



Los datos de MySQL se guardan en el volumen Docker `mysql\_data`, montado en `/var/lib/mysql`.



El volumen es independiente del repositorio GitHub. Para trasladar datos existentes a otro equipo, se debe realizar una copia de seguridad y restaurarla en el destino.



\## Repositorio



https://github.com/adonet77/docker-adso318

