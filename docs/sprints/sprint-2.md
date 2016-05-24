**Duración:** Jueves 26/05/16 - Martes 31/05/16

# Alcance

![Alcance](http://i.imgur.com/Fwwob3I.png)

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
5. Crear modelo y rutas de Tags, UpdateFrequency y Config
6. Crear seeds de Tags, Update Frequency y Config
7. Agregar los campos faltantes a los modelos File, Dataset y Category:
    - Owner (usuario responsable) a File y Dataset.
    - Update Frequency a File.
    - Tags a Dataset.
    - Active a Category.
8. Agregar validaciones a los campos de los modelos
9. Configurar sails-permissions
10. Correr tests de Dredd

## Admin
1. CRUD de Categories (funcional):
    - Agregando el campo fantante Active
    - Con posiblidad de activar y desactivar categorías (ver documento funcional para una descripción detallada del behavior)
2. CRUD de Organizations (funcional)
3. CRUD de Databases (funcional)
4. CRUD de Statuses (funcional)
5. CRUD de Filetypes (funcional)
5. Agregar los campos faltantes a la UI del CRUD de File y Dataset
6. UI de CRUD de UpdateFrequency
7. UI de CRUD de Tags
8. UI de Config

# Prioridades
1. Subida de archivos
2. CRUD de Categories y Organizations
3. Método OPTIONS


# Campos Faltantes

## Category

- **active:**

    Si la categoría está activa o no.

    *Tipo:* boolean

    *Requerido:* sí

    *Default:* false


## File

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


## Dataset

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


## UpdateFrequency

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


## Config

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
