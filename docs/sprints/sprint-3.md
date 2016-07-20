**Duración:** Miercoles 01/06/16 - Martes 07/06/16

# Alcance

![Alcance](http://i.imgur.com/6jhR8my.png)

## Objetivo
Hacer la lógica del parseo y guardado de datos y terminar los CRUD que entran en la release Alpha.


# Tareas

## API

1. Escribir spec de Datasets
2. Desarrollar el ordenamiento de los archivos subidos en carpetas (por dataset)
2. Desarrollar la validación de los archivos subidos
3. Desarrollar la codificación por defecto de los archivos de texto
4. Desarrollar el parseo y guardado de datos en la BBDD no relacional
5. Desarrollar el listado de response codes y sus messages
6. Desarrollar el empaquetado y endpoint para la descarga de datasets:
    debe incluirse la URL de descarga dentro de la sección `links` de la response a `GET /datasets`, y dentro de la response a `OPTIONS /datasets`.


## Admin

1. UI de subida de archivos (funcional):
    debe chequear el mimetype (no la extensión) del archivo que se sube, y sólo permitir la subida de los siguientes tipos de archivos:
    - csv
    - html
    - ics
    - pdf
    - rar
    - shp
    - xls
    - xlsx
    - xml
    - zip
2. CRUD de UpdateFrequencies (funcional)
3. CRUD de Tags (funcional)
4. CRUD de Filetypes (funcional)


## Frontend

1. Landing page (funcional)
2. Listado datasets (funcional)
3. Ver dataset (funcional)
4. Ver recursos asociados (UI + funcional)


# Prioridades
1. Parseo y guardado de datos
2. UI de subida de archivos (funcional)
3. Validación de archivos subidos
4. Listado de response codes y messages


# Endpoints

## Datasets
```
GET  /datasets/:id/download
```