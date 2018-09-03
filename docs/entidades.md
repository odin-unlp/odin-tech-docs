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
PUT    /organizations/:id
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

    *Único:* sí

    *Max:* 150 carácteres

    *Min:* 1 carácteres

---

- **slug**

    *Tipo:* string

    *Único:* sí

    *Max:* 150 carácteres

    *Min:* 1 carácteres

---

- **description**

    *Tipo:* string

    *Max:* 350 carácteres

---

- **address**

    *Tipo:* string

    *Max:* 150 carácteres

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

    *Model:*  user

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
PUT    /users/:id
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

    *url:* true

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

    *Model:* user


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
PUT    /categories/:id
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

    *Único:* sí

    *Max:* 150 carácteres

    *Min:* 1 carácteres

    *Único:* sí

---

- **slug**

    *Tipo:* string

    *Único:* sí

    *Max:* 150 carácteres

---

- **fileName**

    *Tipo:* string

    *Max:* 150 carácteres

---

- **description**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 350 carácteres

---

- **color**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 6 carácteres


- **active:**

    Si la categoría está activa o no.

    *Tipo:* boolean

    *Requerido:* sí

    *Default:* true

---

- **datasets**

    *Collection:* dataset

    *Via:* categories
---

- **datasetsSubcategories**

    *Collection:* dataset

    *Via:* subcategories

---

- **parent**

    *model:* category

---    

- **subcategories**

    *Collection:* category

    *Via:* parent

---

- **requests**
  
  *Collection:* datasetreques

    *Via:* categories

- **deletedAt**

    *type:* datetime

--

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

### Claves Foráneas

- **createdBy**

    El ID del usuario que creó la categoría.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:*  user

---

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
PUT    /statuses/:id
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

    *Único:* sí

    *Max:* 150 carácteres

    *Min:* 1 carácteres
---

- **files**

    *collection:* file

    *via:* status

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **createdBy**

    *model:* user

---

- **datasets**

    *collection:* dataset

    *via:* status

--- 

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

**Nota:** a los fines del seedeo, los estados por recurso son:

- Borrador
- En revision
- Rechazado
- Publicado
- Despublicado

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
PUT    /filetypes/:id
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

    *Único:* sí

    *Max:* 150 carácteres

---

- **slug**

    *Tipo:* string

    *Requerido:* sí

---

- **api**

    Indica si el tipo de archivo es parseable en la api

    *Tipo:* boolean

---

- **mimetype**

    *Tipo:* array

---

- **editable**

    *Tipo:* boolean

    *defaultsTo:* true

---

- **createdBy**

    *model:* user

---

- **deletedAt**

    *type:* datetime

---    

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **files** 
 
    *collection:* file
    *via:* type

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
PUT    /updatefrequencies/:id
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

    *Único:* sí

    *Max:* 100 carácteres

---

- **timePattern**

    Indica la frequencia en la que se correrá el cron

    *Tipo:* string
---

- **createdBy**

    *model:* user

---

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
PUT    /tags/:id
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

    *Único:* sí

    *Max:* 100 carácteres

---

- **slug**

    *Tipo:* string

    *Único:* sí

    *Max:* 150 carácteres

---

- **files**

    *collection:* file

    *via:* tags

---

- **datasets** 
 
    *collection:* dataset
    *via:* tags

---    

### Claves Foráneas

- **createdBy**

    El ID del usuario que creó la etiqueta.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:* user

---    

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
PUT    /datasets/:id
DELETE   /datasets/:id
HEAD     /datasets/:id
OPTIONS  /datasets/:id

PATCH /datasets/:id/unpublish
PATCH /datasets/:id/publish

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

    *Único:* sí

    *Max:* 150 carácteres

    *Min:* 1 carácteres

---

- **slug**

    *Tipo:* string

    *Único:* sí

    *Max:* 150 carácteres

---

- **description**

    *Tipo:* string

    *Requerido:* sí

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

- **optionals**

    *Tipo:* json

---

- **publishedAt**

    *Tipo:* datetime

---

- **unPublishedAt**

    *Tipo:* datetime

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **deletedAt**

    *Tipo:* datetime

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales


### Claves Foráneas

- **categories**

    Los ID de las categorías del dataset.

    *Requerido:* sí

    *Collection:* category

    *Via:* datasets

    *Dominant:* true

---

- **subcategories**

    Los ID de las subcategorías del dataset.

    *Requerido:* sí

    *Collection:* category

    *Via:* datasetsSubcategories
    
    *Dominant:* true

---

- **status**

    El ID del status que posee el dataset.

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:* status

---

- **owner:**

    Es el usuario responsable del archivo. Es una clave foránea.

    *Tipo:* string

    *Requerido:* sí
    
    *Model:* user

    *Max:* 15 carácteres

---

- **tags**

    *Collection:* tag

    *Via:* datasets
           
    *Dominant:* true

---

- **createdBy**

    El ID del usuario que creó el dataset.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:* user

---

- **organization**

    *Model:* organization

---    

- **hasMap**

    *Type:* boolean

    *DefaultsTo:* false

---

- **hasChart**

    *Type:* boolean

    *DefaultsTo:* false

---

- **hasTable**

    *Type:* boolean

    *DefaultsTo:* false

---

- **newestGatheringDate**

    *type:* date

---

          
           
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
PUT    /files/:id
DELETE   /files/:id
HEAD     /files/:id
OPTIONS  /files/:id

GET   /files/:id/contents
GET   /files/(:slug|:id)/download
GET   /files/(:slug|:id)/download/:format

PATCH   /files/:id/publish
PATCH   /files/:id/unpublish
PATCH   /files/:id/reject
PATCH   /files/:id/cancel
PATCH   /files/:id/review

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

    *Único:* sí

    *Max:* 150 carácteres

---

- **fileName**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 150 carácteres

---

- **description**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 350 carácteres

---

- **notes**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **url**

    *Tipo:* string

    *Max:* 500 carácteres

    *defaultsTo:* false

---

- **visible**

    *Tipo:* boolean

    *defaultsTo:* false

---

- **gatheringDate**

    *Tipo:* date

---

- **layout**

    Indica si el archivo es guia de datos

    *Tipo:* boolean

    *defaultsTo:* false

---

- **updated**

    Indica si el archivo debería mostrarse en el frontend

    *Tipo:* boolean

    *defaultsTo:* false

---

- **publishedAt**

    *Tipo:* datetime

---

- **optionals**

    *Tipo:* json

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

### Claves Foráneas

- **type**

    El ID del tipo de archivo.

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:* filetype

---

- **status**

    El ID del status que posee el archivo.

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:* status

---

- **organization**

    El ID de la organización que provee los datos.

    *Requerido:* sí

    *Max:* 15 carácteres
    
    *Model:* organization

---

- **dataset**

    El ID del dataset al que pertenece.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:* dataset

---

- **owner:**

    Es el usuario responsable del archivo. Es una clave foránea.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:* user

---

- **updateFrequency:**

    La frecuencia en que se debe actualizar el archivo. Es una clave foránea.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:* updatefrequency

---

- **createdBy**

    El ID del usuario que creó el archivo.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:* user

---

- **soapService:**

    Servicio soap asociado.

    *Tipo:* string

    *Max:* 15 carácteres

    *Model:* soapservice

---

- **restService:**

    Servicio rest asociado.

    *Tipo:* string

    *Max:* 15 carácteres

    *Model:* restservice

---


- **tags**

    *collection:* tag

    *via:* files

    *dominant:* true

---    

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
PUT    /charts/:id
DELETE   /charts/:id
HEAD     /charts/:id
OPTIONS  /charts/:id

PATCH   /charts/:id/publish
PATCH   /charts/:id/unpublish
PATCH   /charts/:id/reject
PATCH   /charts/:id/cancel
PATCH   /charts/:id/review
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

    *Único:* sí

    *Max:* 150 carácteres

    *Min:* 1 carácter
 
---

- **description**

    *Tipo:* string
    
    *Requerido:* sí

    *Max:* 350 carácteres

---

- **type**

    *Tipo:* string

    *Valores posibles:* 'bar', 'pie', 'line', 'stackedbar','heatmap'

---

- **notes**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **data**

    *Tipo:* json

    *Max:* 5000 carácteres

---

- **dataType**

    *Tipo:* enum

    *Valores posibles:* 'qualitative', 'cuantitative'

---

- **dataSeries**

    *Tipo:* array

---

- **url**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **link**

    Grafico embebido

    *Tipo:* string

    *Max:* 500 carácteres

---

- **publishedAt**

    *Tipo:* datetime

---

- **unPublishedAt**

    *Tipo:* datetime

---

- **rejectedAt**

    *Tipo:* datetime

---

- **cancelledAt**

    *Tipo:* datetime

---

- **reviewedAt**

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

- **createdBy**

    El ID del usuario que creó el gráfico.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:* user

---

- **status**

    El ID del status que posee el grafico.

    *Requerido:* sí

    *Model:* status

    *Max:* 15 carácteres

---

- **file**

    El ID del del archivo relacionado archivo.

    *Requerido:* sí

    *Max:* 15 carácteres

    *Model:* file


# 11. Basemap
## Endpoints
```
GET      /basemaps
OPTIONS  /basemaps

GET      /basemaps/first
OPTIONS  /basemaps/first

GET      /basemaps/last
OPTIONS  /basemaps/last

GET      /basemaps/count
OPTIONS  /basemaps/count

GET      /basemaps/:id
HEAD     /basemaps/:id
OPTIONS  /basemaps/:id
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
    
    *Único:* sí

    *Max:* 100 carácteres

---


- **attribution**

    *Tipo:* string

---

- **tms**

    *Tipo:* boolean

    *defaultsTo:* false

---

- **maxZoom**

    *Tipo:* integer

    *defaultsTo:* 18

---

- **minZoom**

    *Tipo:* integer

    *defaultsTo:* 0

---

- **optionals**

    *Tipo:* json

---

- **url**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 500 carácteres

---

- **unPublishedAt**

    *Tipo:* datetime

---

- **publishedAt**

    *Tipo:* datetime

---

- **rejectedAt**

    *Tipo:* datetime

---

- **cancelledAt**

    *Tipo:* datetime

---

- **reviewedAt**

    *Tipo:* datetime

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---    

# 12. Map
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
PUT    /maps/:id
DELETE   /maps/:id
HEAD     /maps/:id
OPTIONS  /maps/:id

PATCH   /maps/:id/publish
PATCH   /maps/:id/unpublish
PATCH   /maps/:id/reject
PATCH   /maps/:id/cancel
PATCH   /maps/:id/review
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

    *Único:* sí

    *Max:* 150 carácteres

    *Min:* 1 carácter

---

- **description**

    *Tipo:* string

    *Requerido:* sí

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

- **link**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **embedCode**

    *Tipo:* text

    *Max:* 500 carácteres

---

- **properties**

    *Tipo:* array

---

- **latitudeKey**

    *Tipo:* string

    *Max:* 100 carácteres

---

- **longitudeKey**

    *Tipo:* string

    *Max:* 100carácteres

---


- **geojson**

    *Tipo:* json

    *Max:* 5000 carácteres

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

---    

### Claves Foráneas

- **basemap**

    El ID del basemap.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **createdBy**

    El ID del usuario que creó el map.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **status**

    El ID del status que posee el mapa.

    *Requerido:* sí

    *Max:* 15 carácteres

---

- **kml**

    *Type:* boolean


    *DefaultsTo:* false

---   

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
PUT    /configs/:id
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

    *Único:* sí

    *Max:* 250 carácteres

---

- **type**

    *Tipo:* enum

    *Requerido:* sí

    *Valores posibles:* 'bool', 'string', 'int', 'float', 'model', 'group'

---

- **category**

    *Tipo:* enum

    *Requerido:* sí

    *Valores posibles:* 'site', 'visualizations', 'integrations'

---

- **key**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 100 carácteres

---

- **value**

    *Tipo:* string

    *Max:* 250 carácteres

---

- **multiple**

    *Tipo:* boolean
    
    *Boolean:* true

---

- **editable**

    *Tipo:* boolean

    *Boolean:* true

---

- **required**

    *Tipo:* boolean

    *Boolean:* true

---

- **model**

    *Tipo:* string

    *Max:* 50

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---


- **tooltip**

    *type:* string

---    

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---
### Claves Foráneas

- **updatedBy**

    El ID del usuario que actualizó por última vez el `value` de la configuración.

    *Tipo:* string

    *Max:* 15 carácteres

---

- **parent**

    El ID de la configuración padre en caso de que corresponda.

    *Tipo:* string

    *Max:* 15 carácteres

    *Model:* config

---    

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
PUT    /logs/:id
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

    *Tipo:* string

    *Requerido:* sí

---

- **resource**

    *Tipo:* string

    *Requerido:* sí
    
    *Max:* 15
---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---    

### Claves Foráneas

- **user**

    El ID del usuario que actualizó realizó la acción.

    *Tipo:* string

    *Max:* 15 carácteres

    *Model:* user

---    

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
HEAD     /statistics/:id
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

    *Valores posibles:* 'GET', 'POST', 'PUT', 'DELETE', 'HEAD', 'OPTIONS'

---

- **client**

    *Tipo:* string


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

# 16. SoapService
## Endpoints
```
GET      /soapservices
POST     /soapservices
OPTIONS  /soapservices

GET      /soapservices/first
OPTIONS  /soapservices/first

GET      /soapservices/last
OPTIONS  /soapservices/last

GET      /soapservices/count
OPTIONS  /soapservices/count

GET      /soapservices/:id
PUT    /soapservices/:id
DELETE   /soapservices/:id
HEAD     /soapservices/:id
OPTIONS  /soapservices/:id
```

## Campos
- **id**

    *Tipo:* string

    *Requerido:* sí

    *Único:* sí

    *Max:* 15 carácteres

---

- **method**

    *Tipo:* sting

    *Requerido:* sí

---

- **namespace**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 500 carácteres

    *Min:* 1 carácter

---

- **url**

    *Tipo:* sting

    *Requerido:* sí

---

- **attributesAsHeaders**

    *Tipo:* boolean

    *DefaultsTo:* false

---

- **parameters**

    *Tipo:* json

    *Requerido:* sí

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---
### Claves Foráneas

- **file**

    El ID del archivo asociado al soap.

    *Tipo:* string

    *Max:* 15 carácteres

    *Model:* file

# 17. RestService
## Endpoints
```
GET      /restservices
POST     /restservices
OPTIONS  /restservices

GET      /restservices/first
OPTIONS  /restservices/first

GET      /restservices/last
OPTIONS  /restservices/last

GET      /restservices/count
OPTIONS  /restservices/count

GET      /restservices/:id
PUT    /restservices/:id
DELETE   /restservices/:id
HEAD     /restservices/:id
OPTIONS  /restservices/:id
```

## Campos
- **id**

    *Tipo:* string

    *Requerido:* sí

    *Único:* sí

    *Max:* 15 carácteres

---

- **dataPath**

    *Tipo:* sting

    *Max:* 500 carácteres
---

- **titlePath**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **token**

    *Tipo:* sting

    *Max:* 500 carácteres

---

- **tokenSignature**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **tokenAlgorithm**

    *Tipo:* sting

    *Max:* 500 carácteres

---

- **username**

    *Tipo:* string

    *Max:* 500 carácteres
---


- **password**

    *Tipo:* sting

    *Max:* 500 carácteres

---

- **url**

    *Tipo:* sting

    *Requerido:* sí

---

- **attributesAsHeaders**

    *Tipo:* boolean

    *DefaulsTo:* false

---

- **parameters**

    *Tipo:* json

    *Requerido:* sí

---

- **updatedAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales

---    

### Claves Foráneas

- **file**

    El ID del archivo asociado al soap.

    *Tipo:* string

    *Max:* 15 carácteres

    *Model* file

---    