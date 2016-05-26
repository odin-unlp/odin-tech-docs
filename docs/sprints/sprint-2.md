**Duración:** Jueves 26/05/16 - Martes 31/05/16

# Alcance

![Alcance](http://i.imgur.com/X2qos0b.png)

## Objetivo
Hacer la lógica de la subida de archivos, avanzar con los modelos faltantes y la UI del Admin, y hacer funcional gran parte de lo ya prototipado.

*Nota:* Este sprint contará con un día menos a causa del feriado del 25 de mayo.

## No Entra
- UI de subida de archivos


# Tareas

## API
1. Escribir spec de Categories
2. Corregir spec de Users y Datasets
3. Desarrollar subida de archivos
4. Desarrollar método OPTIONS
5. Crear modelo y rutas de Tags, UpdateFrequencies y Configs
6. Crear seeds de Tags, UpdateFrequencies y Configs
7. Agregar los campos faltantes a los modelos Files, Datasets y Categories:
    - Owner (usuario responsable) a Files y Datasets.
    - UpdateFrequencies a Files.
    - Tags a Datasets.
    - Active a Categories.
8. Agregar validaciones a los campos de los modelos
9. Configurar sails-permissions
10. Correr tests de Dredd

## Admin
1. CRUD de Categories (funcional):
    - Agregando el campo faltante Active
    - Con posiblidad de activar y desactivar categorías (ver documento funcional para una descripción detallada del behavior)
2. CRUD de Organizations (funcional)
3. CRUD de Databases (funcional)
4. CRUD de Statuses (funcional)
5. CRUD de Filetypes (funcional)
5. Agregar los campos faltantes a la UI del CRUD de Files y Datasets
6. UI de CRUD de UpdateFrequencies
7. UI de CRUD de Tags
8. UI de Configs

# Prioridades
1. Subida de archivos
2. CRUD de Categories y Organizations
3. Método OPTIONS


# Endpoints

## Tags
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

## UpdateFrequencies
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

## Configs
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

# Campos Faltantes

## Categories

- **active:**

    Si la categoría está activa o no.

    *Tipo:* boolean

    *Requerido:* sí

    *Default:* false


## Files

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


## Datasets

- **owner:**

    Es el usuario responsable del archivo. Es una clave foránea.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres


### Tags

Es una relación muchos a muchos, por lo que se necesitará una tabla intermedia (creada automáticamente por Waterline).


# Modelos

## Tags

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


## UpdateFrequencies

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


## Configs

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

    El ID del usuario que actualizó la configuración.

    *Tipo:* string

    *Max:* 15 carácteres