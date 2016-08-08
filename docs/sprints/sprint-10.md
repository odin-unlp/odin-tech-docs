**Duración:** Lunes 01/08/16 - Viernes 05/08/16

# Alcance
Sprint de gráficos y Frontend.

## Objetivo
Desarrollar el CRUD de gráficos y continuar maquetando el Frontend.

# Tareas

## API

1. Creación de gráficos en la API

## Admin
1. CRUD de gráficos
2. Agregar botones "Editar" y "Eliminar" al listado de recursos asociados a un File
3. Crear CRUD de Configs

## Frontend
1. Maquetar el listado de datasets (marca blanca)
2. Hacer funcionales los links de Ver datasets/visualizaciones
3. Implementar la vista de gráficos
4. Implementar la vista de mapas
5. Hacer funcionales los links de descarga
6. Hacer funcionales los links al home
7. Limitar la tabla a los campos Optional (si tienen algún valor)

## Otros
1. Agregar campo "link" en mapa a documentación técnica
2. Documentar los nuevos campos en Chart : 'data', 'dataSeries, 'dataType'

# Prioridades

1. Creación de gráficos en la API
2. CRUD de gráficos
3. Maquetar el listado de datasets (marca blanca)

# Campos

## Charts

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