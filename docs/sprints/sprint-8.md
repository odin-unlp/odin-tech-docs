**Duración:** Lunes 18/07/16 - Viernes 22/07/16

# Alcance
Sprint de Admin y statistics.

## Objetivo
Continuar desarrollando y corregir errores del Admin, desarrollar el módulo de stats de la API y agregar color e image a las categorías.


# Tareas

## API

1. Desarrollar la pertenencia a más de una categoría
2. Desarrollar el módulo de analytics
3. Desarrollar la subida de imágenes para las categorías
4. Agregar los campos color e image a Category
5. Agregar seeds de color e image a Category
6. Agregar un job para desocupar la tabla de Stats 1 vez al mes
7. Solucionar las issues de Codacy
8. Agregar tests de Organization
9. Agregar tests de Statistic

## Admin
1. Solucionar los tickets de errores (del Trello de Testing)
2. Completar las tareas pendientes de sprints anteriores
3. Incluir la pertenencia a más de una categoría en el CRUD de Datasets
4. Agregar color e image al CRUD de Category

## Otros
1. Instalar y configurar Kong en el entorno de integración y en el de testeo
2. Escribir el README
3. Escribir el CHANGELOG
4. Consolidar la documentación técnica

# Prioridades

1. Solucionar los tickets de errores (del Trello de Testing)
2. Completar las tareas pendientes de sprints anteriores
3. Desarrollar la pertenencia a más de una categoría
4. Desarrollar el módulo de analytics
5. Desarrollar la subida de imágenes para las categorías
6. Agregar los campos color e image a Category

# Endpoints

## Statistics
```
GET      /statistics
POST     /statistics
OPTIONS  /statistics

GET      /statistics/first
OPTIONS  /statistics/first

GET      /statistics/last
OPTIONS  /statistics/last

GET      /statistics/count
OPTIONS  /statistics/count

GET      /statistics/:id
PATCH    /statistics/:id
DELETE   /statistics/:id
HEAD     /statistics/:id
OPTIONS  /statistics/:id
```

# Campos

## Statistics

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

## Categories

- **color**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 6 carácteres

---

- **image**

    *Tipo:* string

    *Max:* 500 carácteres