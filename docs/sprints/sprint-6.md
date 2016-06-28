**Duración:** Miercoles 29/06/16 - Martes 05/07/16

# Alcance
Sprint de vistas.

## Objetivo
Hacer el CRUD de las vistas.


# Tareas

## API

1. Hacer el spec, modelo, seeds, routes y controller de las vistas (views)
2. Añadir el campo `geojson` a Maps, y `embedCode` a Charts y Maps
3. Desarrollar la generación de geojson
4. Loguear a un archivo las actividades CRUD de la API

    Se usará el logger Winston. El archivo tendrá el nombre del environment actual (ej. `development.log`) y se creará automáticamente si no existe, al igual que el directorio donde estará (logs). Se creará también una configuración extra en `config/odin.js` para determinar el nivel de logging a utilizar, de entre los definidos en npm: `silly`, `verbose`, `info`, `http`, `warn`, `error`, `silent`. Los eventos que se loguearán son:

    - Cuando la aplicación se ha terminado de levantar y está completamente operativa. Nivel: `info`
    - Creación de cada recurso (Categories, Datasets, Organization, etc). Nivel: `info`
    - Edición de cada recurso. Nivel: `info`
    - Borrado de cada recurso. Nivel: `info`
    - Errores en cada uno de los anteriores. Nivel: `error`
    - La descarga de un archivo. Nivel: `verbose`
    - El code y message de cada response generada. Nivel: `verbose`
    - Las headers, parámetros (si corresponde) y body de cada request recibida. Nivel: `silly`
    - Las headers y body de cada response generada. Nivel: `silly`

    El log debe incluir: evento, IP (si corresponde), fecha y hora.
5. Desarrollar conversión a JSON y guardado en la BBDD no relacional de los archivos XLS y XLSX
6. Escribir los tests unitarios faltantes

    Para los siguientes casos:

    - Subida de un archivo
    - Codificación correcta de los archivos de texto
    - Accesibilidad vía API del contenido de los archivos CSV, XLS y XLSX
    - Ciclo completo de un mismo recurso: creación, edición y borrado
    - Generación de feed RSS
    - Descarga de archivos
    - Paginado
    - Populate y filtrado
    - Búsqueda

# Prioridades

1. Modelos y seeds
2. GeoJSON
3. Tests unitarios


# Endpoints

## Views
```
GET      /views
POST     /views
OPTIONS  /views

GET      /views/first
OPTIONS  /views/first

GET      /views/last
OPTIONS  /views/last

GET      /views/count
OPTIONS  /views/count

GET      /views/:id
PATCH    /views/:id
DELETE   /views/:id
HEAD     /views/:id
OPTIONS  /views/:id
```

# Modelos

## Views

- **id**

    *Tipo:* string

    *Requerido:* sí

    *Único:* sí

    *Max:* 15 carácteres

---

- **name**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 150 carácteres

---

- **description**

    *Tipo:* string

    *Max:* 350 carácteres

---

- **notes**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **tags**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales


### Claves Foráneas

- **tags**

    Referencia a la relación muchos a muchos tags-views.

---

- **createdBy**

    El ID del usuario que creó el gráfico.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres


# Campos

## Maps

- **geojson**

    *Tipo:* json

    *Max:* 5000 carácteres


## Maps y Charts

- **embedCode**

    *Tipo:* text

    *Max:* 500 carácteres