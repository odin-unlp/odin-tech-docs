**Duración:** Miércoles 18/05/16 - Martes 24/05/16

# Alcance

![Entidad - Relación](http://i.imgur.com/u7CUz6v.png)

## Entra

## No Entra



# Tareas

## API

## Admin

## Frontend


# Endpoints

## Users
```
GET     /users
POST    /users
HEAD    /users
OPTION  /users

GET     /users/first
HEAD    /users/first
OPTION  /users/first

GET     /users/last
HEAD    /users/last
OPTION  /users/last

GET     /users/count
HEAD    /users/count
OPTION  /users/count

GET     /users/:id
PATCH   /users/:id
DELETE  /users/:id
HEAD    /users/:id
OPTION  /users/:id

GET     /users/login
POST    /users/login
HEAD    /users/login
OPTION  /users/login
```

## Organizations
```
GET     /organizations
POST    /organizations
HEAD    /organizations
OPTION  /organizations

GET     /organizations/first
HEAD    /organizations/first
OPTION  /organizations/first

GET     /organizations/last
HEAD    /organizations/last
OPTION  /organizations/last

GET     /organizations/count
HEAD    /organizations/count
OPTION  /organizations/count

GET     /organizations/:id
PATCH   /organizations/:id
DELETE  /organizations/:id
HEAD    /organizations/:id
OPTION  /organizations/:id
```

## Categories
```
GET     /categories
POST    /categories
HEAD    /categories
OPTION  /categories

GET     /categories/first
HEAD    /categories/first
OPTION  /categories/first

GET     /categories/last
HEAD    /categories/last
OPTION  /categories/last

GET     /categories/count
HEAD    /categories/count
OPTION  /categories/count

GET     /categories/:id
PATCH   /categories/:id
DELETE  /categories/:id
HEAD    /categories/:id
OPTION  /categories/:id
```

## Statuses
```
GET     /statuses
POST    /statuses
HEAD    /statuses
OPTION  /statuses

GET     /statuses/first
HEAD    /statuses/first
OPTION  /statuses/first

GET     /statuses/last
HEAD    /statuses/last
OPTION  /statuses/last

GET     /statuses/count
HEAD    /statuses/count
OPTION  /statuses/count

GET     /statuses/:id
PATCH   /statuses/:id
DELETE  /statuses/:id
HEAD    /statuses/:id
OPTION  /statuses/:id
```

## Files
```
GET     /files
POST    /files
HEAD    /files
OPTION  /files

GET     /files/first
HEAD    /files/first
OPTION  /files/first

GET     /files/last
HEAD    /files/last
OPTION  /files/last

GET     /files/count
HEAD    /files/count
OPTION  /files/count

GET     /files/:id
PATCH   /files/:id
DELETE  /files/:id
HEAD    /files/:id
OPTION  /files/:id
```

## Datasets
```
GET     /datasets
POST    /datasets
HEAD    /datasets
OPTION  /datasets

GET     /datasets/first
HEAD    /datasets/first
OPTION  /datasets/first

GET     /datasets/last
HEAD    /datasets/last
OPTION  /datasets/last

GET     /datasets/count
HEAD    /datasets/count
OPTION  /datasets/count

GET     /datasets/:id
PATCH   /datasets/:id
DELETE  /datasets/:id
HEAD    /datasets/:id
OPTION  /datasets/:id
```

# Base de datos
image

## Users

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


## Organizations

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

- **parent**
    
    El ID de la organización a que pertenece. En caso de una organización que no depende de alguna otra existente en la base de datos, va NULL.

    *Tipo:* string 
    
    *Max:* 15 carácteres

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
    
    El ID del usuario que creó la organización.

    *Tipo:* string 
    
    *Requerido:* sí
    
    *Max:* 15 carácteres 


## Categories

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


## Statuses

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
- Under review
- Rejected
- Published
- Unpublished


## Files

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

- **createdBy**
    
    El ID del usuario que creó el archivo.

    *Tipo:* string 
    
    *Requerido:* sí
    
    *Max:* 15 carácteres 


## Datasets

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

- **visibility**

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
    
    El ID del status que posee el archivo.
    
    *Requerido:* sí
    
    *Max:* 15 carácteres

---

- **organization**
    
    El ID de la organización que provee los datos.
    
    *Requerido:* sí
    
    *Max:* 15 carácteres

---

- **createdBy**
    
    El ID del usuario que creó el dataset.

    *Tipo:* string 
    
    *Requerido:* sí
    
    *Max:* 15 carácteres 


# Repositorios

## API

## Admin

## Frontend

## Yeoman

```
Application questions:
? Application name odin

Configuration questions:
? Database name odin
? Enable CORS? Yes

Logger questions:
? Choose which logger you want to configure Winston

Blueprint questions:
? Use overridden blueprints? Yes

Controller questions:
? Choose which predefined controllers you want to copy (Press <space> to select)PingController, SearchController

Hook questions:
? Choose which predefined hooks you want to copy (Press <space> to select)CountHook, PluralizeHook

Cron questions:
? Do you need cron? Yes

Swagger questions:
? Do you need Swagger UI Explorer? No

Authentication questions:
? Do you need authentication layer? Yes

Service questions:
? Select which services you want to use CipherService, HashService, MailerService, StorageService
? Mailer provider direct
? Storage provider Local
```
Guardar la secret key generada en Google Drive