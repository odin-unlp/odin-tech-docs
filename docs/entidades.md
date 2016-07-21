# 1. Organization
## Endpoints
```
GET      /organizations
POST     /organizations
OPTIONS  /organizations

GET      /organizations/first
OPTIONS  /organizations/first

GET      /organizations/last
OPTIONS  /organizations/last

GET      /organizations/count
OPTIONS  /organizations/count

GET      /organizations/:id
PATCH    /organizations/:id
DELETE   /organizations/:id
HEAD     /organizations/:id
OPTIONS  /organizations/:id
```

## Campos
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

- **address**

    *Tipo:* string

    *Max:* 150 carácteres

---

- **active**

    *Tipo:* boolean

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales


### Claves Foráneas

- **parent**

    El ID de la organización a que pertenece. En caso de una organización que no depende de alguna otra existente en la base de datos, va NULL.

    *Tipo:* string

    *Max:* 15 carácteres

---

- **createdBy**

    El ID del usuario que creó la organización.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

# 2. User
## Endpoints
```
GET      /users
POST     /users
OPTIONS  /users

GET      /users/first
OPTIONS  /users/first

GET      /users/last
OPTIONS  /users/last

GET      /users/count
OPTIONS  /users/count

GET      /users/:id
PATCH    /users/:id
DELETE   /users/:id
HEAD     /users/:id
OPTIONS  /users/:id

GET      /users/refreshToken/:id
OPTIONS  /users/refreshToken/:id

POST     /users/login
OPTIONS  /users/login
```

## Campos
- **id**

    *Tipo:* string

    *Requerido:* sí

    *Único:* sí

    *Max:* 15 carácteres

---

- **username**

    *Tipo:* string

    *Requerido:* sí

    *Único:* sí

    *Max:* 25 carácteres

---

- **password**

    *Tipo:* string

    *Requerido:* sí

---

- **email**

    *Tipo:* email

    *Requerido:* sí

    *Único:* sí

    *Max:* 250 carácteres

---

- **firstName**

    *Tipo:* string

    *Max:* 50 carácteres

    *Default:* '' (empty string)

---

- **lastName**

    *Tipo:* string

    *Max:* 100 carácteres

    *Default:* '' (empty string)

---

- **avatar**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **active**

    *Tipo:* boolean

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

### Claves Foráneas

- **organization**

    El ID de la organización a que pertenece. En el caso del Admin (usuario 1) por el momento será la primera organización generada por el seedeo de la base de datos (ej. "Organización 1").

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **createdBy**

    El ID del admin que creó el usuario. En el caso del Admin (usuario 1), es sí mismo (1).

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres


### Calculados

- **fullName**

    Es el resultado de concatenar firstName y lastName, separados por un espacio en blanco.

    *Tipo:* string

    *Ejemplo:* Juan Pérez

# 3. Category
## Endpoints
```
GET      /categories
POST     /categories
OPTIONS  /categories

GET      /categories/first
OPTIONS  /categories/first

GET      /categories/last
OPTIONS  /categories/last

GET      /categories/count
OPTIONS  /categories/count

GET      /categories/:id
PATCH    /categories/:id
DELETE   /categories/:id
HEAD     /categories/:id
OPTIONS  /categories/:id

GET      /categories/:id/image
```

## Campos
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

- **color**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 6 carácteres

---

- **image**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **active:**

    Si la categoría está activa o no.

    *Tipo:* boolean

    *Requerido:* sí

    *Default:* false

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales


### Claves Foráneas

- **createdBy**

    El ID del usuario que creó la categoría.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

# 4. Status
## Endpoints
```
GET      /statuses
POST     /statuses
OPTIONS  /statuses

GET      /statuses/first
OPTIONS  /statuses/first

GET      /statuses/last
OPTIONS  /statuses/last

GET      /statuses/count
OPTIONS  /statuses/count

GET      /statuses/:id
PATCH    /statuses/:id
DELETE   /statuses/:id
HEAD     /statuses/:id
OPTIONS  /statuses/:id
```

## Campos
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

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

**Nota:** a los fines del seedeo, los estados por recurso son:

- Draft
- Under Review
- Rejected
- Published
- Unpublished

# 5. FileType
## Endpoints
```
GET      /filetypes
POST     /filetypes
OPTIONS  /filetypes

GET      /filetypes/first
OPTIONS  /filetypes/first

GET      /filetypes/last
OPTIONS  /filetypes/last

GET      /filetypes/count
OPTIONS  /filetypes/count

GET      /filetypes/:id
PATCH    /filetypes/:id
DELETE   /filetypes/:id
HEAD     /filetypes/:id
OPTIONS  /filetypes/:id
```

## Campos
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

- **mimetype**

    *Tipo:* string

    *Max:* 200 carácteres

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

**Nota:** a los fines del seedeo, los tipos de archivo son:

- csv
- html
- ics
- pdf
- rar
- shp
- xls
- xml
- xlsx
- zip

# 6. UpdateFrequency
## Endpoints
```
GET      /updatefrequencies
POST     /updatefrequencies
OPTIONS  /updatefrequencies

GET      /updatefrequencies/first
OPTIONS  /updatefrequencies/first

GET      /updatefrequencies/last
OPTIONS  /updatefrequencies/last

GET      /updatefrequencies/count
OPTIONS  /updatefrequencies/count

GET      /updatefrequencies/:id
PATCH    /updatefrequencies/:id
DELETE   /updatefrequencies/:id
HEAD     /updatefrequencies/:id
OPTIONS  /updatefrequencies/:id
```

## Campos
- **id**

    *Tipo:* string

    *Requerido:* sí

    *Único:* sí

    *Max:* 15 carácteres

---

- **name**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 100 carácteres

# 7. Tag
## Endpoints
```
GET      /tags
POST     /tags
OPTIONS  /tags

GET      /tags/first
OPTIONS  /tags/first

GET      /tags/last
OPTIONS  /tags/last

GET      /tags/count
OPTIONS  /tags/count

GET      /tags/:id
PATCH    /tags/:id
DELETE   /tags/:id
HEAD     /tags/:id
OPTIONS  /tags/:id
```

## Campos
- **id**

    *Tipo:* string

    *Requerido:* sí

    *Único:* sí

    *Max:* 15 carácteres

---

- **name**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 100 carácteres


### Claves Foráneas

- **createdBy**

    El ID del usuario que creó la etiqueta.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

# 8. Dataset
## Endpoints
```
GET      /datasets
POST     /datasets
OPTIONS  /datasets

GET      /datasets/first
OPTIONS  /datasets/first

GET      /datasets/last
OPTIONS  /datasets/last

GET      /datasets/count
OPTIONS  /datasets/count

GET      /datasets/:id
PATCH    /datasets/:id
DELETE   /datasets/:id
HEAD     /datasets/:id
OPTIONS  /datasets/:id

GET  /datasets/:id/download
```

## Campos
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

- **visible**

    *Tipo:* boolean

---

- **starred**

    *Tipo:* boolean

---

- **optional1**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **optional2**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **optional3**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **optional4**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **optional5**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **optional6**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **optional7**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **optional8**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **optional9**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **optional10**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **publishedAt**

    *Tipo:* datetime

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales


### Claves Foráneas

- **category**

    El ID de la categoría del dataset.

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **status**

    El ID del status que posee el dataset.

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **owner:**

    Es el usuario responsable del archivo. Es una clave foránea.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **createdBy**

    El ID del usuario que creó el dataset.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

# 9. File
## Endpoints
```
GET      /files
POST     /files
OPTIONS  /files

GET      /files/first
OPTIONS  /files/first

GET      /files/last
OPTIONS  /files/last

GET      /files/count
OPTIONS  /files/count

GET      /files/:id
PATCH    /files/:id
DELETE   /files/:id
HEAD     /files/:id
OPTIONS  /files/:id

GET      /files/:id/resources
```

## Campos
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

- **url**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **visibility**

    *Tipo:* boolean

---

- **publishedAt**

    *Tipo:* datetime

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales


### Claves Foráneas

- **type**

    El ID del tipo de archivo.

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **status**

    El ID del status que posee el archivo.

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **organization**

    El ID de la organización que provee los datos.

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **dataset**

    El ID del dataset al que pertenece.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **owner:**

    Es el usuario responsable del archivo. Es una clave foránea.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **updateFrequency:**

    La frecuencia en que se debe actualizar el archivo. Es una clave foránea.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **createdBy**

    El ID del usuario que creó el archivo.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

# 10. Chart
## Endpoints
```
GET      /charts
POST     /charts
OPTIONS  /charts

GET      /charts/first
OPTIONS  /charts/first

GET      /charts/last
OPTIONS  /charts/last

GET      /charts/count
OPTIONS  /charts/count

GET      /charts/:id
PATCH    /charts/:id
DELETE   /charts/:id
HEAD     /charts/:id
OPTIONS  /charts/:id
```

## Campos
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

- **url**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **embedCode**

    *Tipo:* text

    *Max:* 500 carácteres

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales


### Claves Foráneas

- **createdBy**

    El ID del usuario que creó el gráfico.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

# 11. Map
## Endpoints
```
GET      /maps
POST     /maps
OPTIONS  /maps

GET      /maps/first
OPTIONS  /maps/first

GET      /maps/last
OPTIONS  /maps/last

GET      /maps/count
OPTIONS  /maps/count

GET      /maps/:id
PATCH    /maps/:id
DELETE   /maps/:id
HEAD     /maps/:id
OPTIONS  /maps/:id
```

## Campos
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

- **basemap**

    *Tipo:* enum

    *Requerido:* sí

    *Valores posibles:* 'roadmap', 'satellite', 'hybrid', 'terrain'

---

- **url**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **embedCode**

    *Tipo:* text

    *Max:* 500 carácteres

---

- **geojson**

    *Tipo:* json

    *Max:* 5000 carácteres

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

### Claves Foráneas

- **createdBy**

    El ID del usuario que creó el map.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

# 12. View
## Endpoints
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

## Campos
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

# 13. Config
## Endpoints
```
GET      /configs
POST     /configs
OPTIONS  /configs

GET      /configs/first
OPTIONS  /configs/first

GET      /configs/last
OPTIONS  /configs/last

GET      /configs/count
OPTIONS  /configs/count

GET      /configs/:id
PATCH    /configs/:id
DELETE   /configs/:id
HEAD     /configs/:id
OPTIONS  /configs/:id
```

## Campos
- **id**

    *Tipo:* string

    *Requerido:* sí

    *Único:* sí

    *Max:* 15 carácteres

---

- **description**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 250 carácteres

---

- **type**

    *Tipo:* enum

    *Requerido:* sí

    *Valores posibles:* 'bool', 'string', 'int', 'float'

---

- **key**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 100 carácteres

---

- **value**

    *Tipo:* string

    *Max:* 250 carácteres


### Claves Foráneas

- **updatedBy**

    El ID del usuario que actualizó por última vez el `value` de la configuración.

    *Tipo:* string

    *Max:* 15 carácteres

# 14. Log
## Endpoints
```
GET      /logs
POST     /logs
OPTIONS  /logs

GET      /logs/first
OPTIONS  /logs/first

GET      /logs/last
OPTIONS  /logs/last

GET      /logs/count
OPTIONS  /logs/count

GET      /logs/:id
PATCH    /logs/:id
DELETE   /logs/:id
HEAD     /logs/:id
OPTIONS  /logs/:id
```

## Campos
- **id**

    *Tipo:* string

    *Requerido:* sí

    *Único:* sí

    *Max:* 15 carácteres

---

- **action**

    *Tipo:* enum

    *Requerido:* sí

    *Valores posibles:* 'create', 'update', 'delete'

---

- **target**

    *Tipo:* enum

    *Requerido:* sí

    *Valores posibles:* 'category', 'dataset', 'fileType', 'file', 'organization', 'status', 'tag', 'updateFrequency', 'user'

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales


### Claves Foráneas

- **user**

    El ID del usuario que actualizó realizó la acción.

    *Tipo:* string

    *Max:* 15 carácteres

# 15. Statistic
## Endpoints
```
GET      /statistics
OPTIONS  /statistics

GET      /statistics/first
OPTIONS  /statistics/first

GET      /statistics/last
OPTIONS  /statistics/last

GET      /statistics/count
OPTIONS  /statistics/count

GET      /statistics/:id
OPTIONS  /statistics/:id
```

# Campos
- **id**

    *Tipo:* string

    *Requerido:* sí

    *Único:* sí

    *Max:* 15 carácteres

---

- **resource**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 50 carácteres

---

- **endpoint**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 300 carácteres

---

- **querystring**

    *Tipo:* string

    *Max:* 1000 carácteres

---

- **method**

    *Tipo:* enum

    *Requerido:* sí

    *Valores posibles:* 'GET', 'POST', 'PATCH', 'DELETE', 'HEAD', 'OPTIONS'

---

- **client**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 100 carácteres

---

- **useragent**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 1000 carácteres

---

- **ip**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 46 carácteres