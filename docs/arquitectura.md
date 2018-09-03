# Arquitectura

- En la **base de datos No SQL** se deben almacenar los datos de los archivos, que son datos no relacionales.
- En la **base de datos SQL** se deben almacenar los datos relacionales del sistema, como ser: usuarios, permisos, roles, organizaciones, metadatos, etc.
- El **almacenamiento de estáticos** es para almacenar los recursos asociados a los datasets: archivos csv, pdf, shp, etc.
- El **API Gateway** es una aplicación third party que oficia de proxy entre los clientes y la API, añadiendo una capa de administración extensible con plugins.
- El **Admin** es una aplicación web (cliente de la API) desde la cual es posible administrar las diferentes entidades que componen ODIN.


# Stack

## API

- **Sistema operativo:** Ubuntu 16.04 Xenial Xerus
- **Servidor:** NodeJS 8.11.3
- **ECMAScript:** ECMAScript 6
- **Framework:** Sails 0.12.3
- **BBDD no relacional:** MongoDB
- **BDD relacional:** PostgreSQL
- **Almacenamiento de archivos:** FileSystem

## API Gateway

- **Sistema operativo:** Ubuntu 16.04 Xenial Xerus
- **Aplicación:** Kong 0.8.3
- **Servidor:** NGINX 1.10.0

## Frontends

- **Admin:** aplicación AngularJS 1.5.
- **datos.produccion.gob.ar:** aplicación AngularJS 1.5.

# Lógica

## API

Se utilizará el patrón MVC para organizar el código.

## Admin

Se utilizará el patrón MVC para organizar el código.

## Frontend

Se utilizará el patrón MVC para organizar el código.
