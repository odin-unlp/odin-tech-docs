# Arquitectura

 ![arquitectura](http://i.imgur.com/N3qRwIW.png?1)

- En la **base de datos No SQL** se deben almacenar los datasets propiamente dichos, que son datos no relacionales.
- En la **base de datos SQL** se deben almacenar los datos relacionales del sistema, como ser: usuarios, permisos, roles, organizaciones, metadatos, etc.
- El **almacenamiento de estáticos** es para almacenar los recursos asociados a los datasets: archivos csv, pdf, shp, etc.
- El **API Gateway** es una aplicación third party que oficia de proxy entre los clientes y la API, añadiendo una capa de administración extensible con plugins.
- El **Admin** es una aplicación web conectada directamente a ambas bases de datos, en la cual es posible administrar las diferentes entidades que componen ODIN.


# Stack

## API

- **Sistema operativo:** Ubuntu 16.04 Xenial Xerus
- **Servidor:** NodeJS 5.11.1
- **Lenguaje:** JavaScript 5
- **Framework:** Sails 0.12
- **BBDD no relacional:** DocumentDB con interfaz de MongoDB (Azure Managed)
- **BDD relacional:** SQLServer (Azure Managed)
- **Almacenamiento de archivos:** Azure DataStorage

## API Gateway

- **Sistema operativo:** Ubuntu 16.04 Xenial Xerus
- **Aplicación:** Kong 0.8.2
- **Servidor:** NGINX 1.10.0

## Frontends

- **Admin:** interfaz directa sobre ambas bases de datos.
- **data.buenosaires.gob.ar:** aplicación AngularJS 2.0.