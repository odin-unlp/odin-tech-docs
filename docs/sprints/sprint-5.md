**Duración:** Miercoles 21/06/16 - Martes 28/06/16

# Alcance
Sprint de visualizaciones.

## Objetivo
Hacer el CRUD de gráficos y mapas.


# Tareas

## API

1. Hacer el spec, modelo, seeds, routes y controller de gráficos (charts).
2. Hacer el spec, modelo, seeds, routes y controller de mapas (maps).
3. Exponer el contenido de los archivos subidos (CSVs) mediante la API
4. Implementar filtrados condicionales
5. Implementar respuestas parciales granulares
6. Crear servicio de feeds RSS

# Prioridades

1. Modelos y seeds
2. Exponer el contenido de los archivos subidos (CSVs) mediante la API


# Endpoints

## Charts
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

## Maps
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

# Modelos

## Charts

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

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales


### Claves Foráneas

- **createdBy**

    El ID del usuario que creó el gráfico.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres


## Maps

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

- **createdAt**

    *Tipo:* datetime

    *Default:* fecha y hora actuales


### Claves Foráneas

- **createdBy**

    El ID del usuario que creó el map.

    *Tipo:* string

    *Requerido:* sí

    *Max:* 15 carácteres