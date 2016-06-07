**Duración:** Miercoles 8/06/16 - Martes 14/06/16

# Alcance
Sprint de refactoring + cleanup + polishing.

## Objetivo
Hacer el log de acciones, refactorear el código y arreglar los errores y detalles de la UI.

# Tareas

## API

1. Hacer el modelo, seeds y controller del log de acciones.
2. Hacer async la creación del zip de descarga de dataset.
3. Hacer los borrados lógicos.
4. Desarrollar includes granulares (ej. include=tags.name).
5. Refactorear `.negotiate` para dar soporte a todos los tipos de error definidos en `config/errors.js`, y cambiarlo a `.error`.
6. Implementar la recepción de múltiples valores para un parámetro, separados por coma:
    siempre y cuando se el modelo lo admita (es decir, haya una relacion de uno a muchos o de muchos a muchos).
7. Extractar a un servicio y comentar la lógica de la subida de archivos.
8. Separar la lógica del constructor de `ResponseGET` en métodos y comentarlos.
9. Refactorear la búsqueda para que no busque en todos los campos por defecto, sino sólo los que estén en una whitelist.
10. Poner el campo fullName en la response de `GET /users` y `GET /users/:id`.
11. En las responses GET de un ítem en particular, agregar en `links` las relaciones de primer grado:
    por ejemplo, `/datasets/ag56fdf/tags`.
12. Separar las responses correctas (2xx) definidas en `config/errors.js` a otro archivo.
13. Refactorear `appUrl`.
14. Implementar `206 Partial Content` para el contenido paginado.
15. Implementar `204 No Content` para las responses sin contenido.
16. Implementar un chequeo más robusto de objetos vacíos.

## Admin

1. Solucionar los ítems marcados como "Crítico" en el Trello de testing.
2. Solucionar los ítems marcados como "Error" en el Trello de testing.
3. Solucionar los ítems marcados como "Mejora" en el Trello de testing.
4. Adecuar la interfaz del CRUD de Archivos a lo especificado por los documentos funcionales.
5. Agregar al dashboard el contenido del log de acciones, las más recientes primero (funcional):
    mostrar las últimas 500 acciones, paginadas de a 20.
6. Quitar el CRUD de databases del Admin (no es necesario que esté expuesto en el Admin).


# Prioridades

1. Async zips
2. Borrados lógicos
3. Includes parciales
4. Resolución de problemas de UI
5. Adecuar CRUD de Archivos


# Endpoints

## Logs
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

# Modelos

## Logs

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