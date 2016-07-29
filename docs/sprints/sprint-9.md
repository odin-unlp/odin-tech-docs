**Duración:** Lunes 25/07/16 - Viernes 29/07/16

# Alcance
Sprint de Admin y Frontend.

## Objetivo
Continuar desarrollando y corregir errores del Admin y maquetar el home del Frontend.

# Tareas

## API

1. Resolver la cuestión de las carpetas que deben existir para poder levantar la aplicación
2. Solucionar las stats con IP 127.0.0.1
3. Poner los seeds de UpdateFrequency en español
4. Agregar el campo 'active' (boolean) a Category
5. Actualizar los seeds de Category incorporando el campo 'active'
6. Agregar los campos 'gatheringDate' (date), 'updateDate' (timestamp) y 'updated' (booleano) a File
7. Implementar la lógica de links / geojson en Maps
8. Fix upload files en Category y Files
9. Resolver creación de zip de dataset

## Admin
1. Implementar el CSS del Admin
2. Agregar al CRUD de File los campos 'gatheringDate' y 'updated'
3. Agregar al CRUD de Category el campo 'active'
4. Agregar el botón-dropdown 'Crear recurso asociado' con las opciones 'Gráfico' y 'Mapa' (si aplica) en la vista individual de un File y cuando se ha terminado de subirlo

## Frontend
1. Maquetar el home (marca blanca)

# Prioridades

1. Maquetar el home (marca blanca)
2. Resolver la cuestión de las carpetas que deben existir para poder levantar la aplicación
3. Fix upload files en Category y Files
4. Resolver creación de zip de dataset
5. Implementar el CSS del Admin

# Campos

## Categories

- **active**

    *Tipo:* boolean

    *Requerido:* sí


## File

- **gatheringDate**

    *Tipo:* date

---

- **updateDate**

    *Tipo:* timestamp

---

- **update**

    *Tipo:* boolean

    *Requerido:* sí