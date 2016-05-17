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

- **username**

    *Tipo:* string 
    
    *Requerido:* sí
    
    *Único:* sí
    
    *Max:* 25 carácteres


- **password**

    *Tipo:* string
    
    *Requerido:* sí 


- **email**

    *Tipo:* email
    
    *Requerido:* sí
    
    *Único:* sí
    
    *Max:* 250 carácteres


- **firstName**

    *Tipo:* string
    
    *Max:* 50 carácteres
    
    *Default:* '' (empty string)


- **lastName**

    *Tipo:* string
    
    *Max:* 100 carácteres
    
    *Default:* '' (empty string)


- **avatar**

    *Tipo:* string
    
    *Max:* 500 carácteres
    
    *Default:* '' (empty string)


- **createdAt**

    *Tipo:* datetime
    
    *Default:* fecha y hora actuales


- **updatedAt**

    *Tipo:* datetime
    
    *Default:* fecha y hora actuales


### Claves Foráneas

    
- **organization**
    
    El ID de la organización a que pertenece. En el caso del Admin (usuario 1) por el momento será la primera organización generada por el seedeo de la base de datos (ej. "Organización 1").

    *Tipo:* string 
    
    *Requerido:* sí
    
    *Max:* 15 carácteres


- **createdBy**
    
    El ID del admin que creó al usuario. En el caso del Admin (usuario 1), es sí mismo (1).

    *Tipo:* string 
    
    *Requerido:* sí
    
    *Max:* 15 carácteres 


### Calculados

- **fullName**

    Es el resultado de concatenar firstName y lastName, separados por un espacio en blanco.
    
    *Tipo:* string
    
    *Ejemplo:* Juan Pérez


## Datasets


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