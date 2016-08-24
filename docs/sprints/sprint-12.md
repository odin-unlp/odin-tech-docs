**Duración:** Martes 16/08/16 - Martes 23/08/16

# Alcance
Sprint de corrección de bugs.

## Objetivo
Continuar el desarrollo de la funcionalidad del Frontend y realizar las correcciones necesarias en la API y el Admin.

# Tareas

## API

1. Resolver diferentes autenticaciones (frontend-admin)
2. Eliminar en cascada mapas y gráficos asociados a archivo
3. Agregar relación estado en mapas y gráficos
4. Resolver bugs
5. Agregar parámetro groupBy al endpoint `:model/statistics?groupBy=:relation`, obteniendo las estadísticas ordenadas por el modelo requerido
6. Crear endpoint `:model/:id/publish` y `:model/:id/unpublish` para publicar y despublicar recursos

## Admin
1. Solucionar problema al mostrar imágen de categoría
2. Aclarar campos obligatorios en los formularios
3. Alerta al ingresar nombre de usuario y/o contraseña
4. Corregir el listado de mimetypes al crear un filetype
5. Agregar estado en crud de mapa y gráfico
6. Minificacion/concatenacion de los archivos para optimizar tiempos de carga, utilizando Gulp. Reducir el número de request al mínimo
7. Modificar mimetype crud para que sea un autocomplete
8. Agregar unidad a tooltip de gráfico
9. Implementar CSS
10. Resolver bugs

## Frontend
1. Agregar módulo **compartir**
2. Hacer funcional módulo compartir
3. Hacer descrptivas las URL (Dataset,categorias,etiquetas)
4. Disminuir el espacio en blanco entre la descripción del dataset y su borde inferior cuando no se muestra "Info adicional".
5. Disminuir el espacio en blanco entre la descripción del archivo y su borde inferior cuando no se muestra "Info adicional".
6. Minificacion/concatenacion de los archivos para optimizar tiempos de carga, utilizando Gulp. Reducir el número de request al mínimo
7. Integrar Twitter
8. Activar el ícono de previsualización
9. Implementar los tabs para seleccionar que gráfico/mapa ver
10. Implementar vista previa de archivos pdf

## Otros
1. Escribir documentación de los archivos de configuración (odin.js)

# Prioridades
1. Resolver Authorization
2. Al eliminar archivos, eliminiar mapas y gráficos asociados
3. Agregar relación estado en mapas y gráficos
4. Agregar estado en crud de mapa y gráfico

# Endpoints

## Datasets
```
PATCH    /datasets/:id/publish
PATCH    /datasets/:id/unpublish
```
## Charts
```
PATCH    /charts/:id/publish
PATCH    /charts/:id/unpublish
```
## Maps
```
PATCH    /maps/:id/publish
PATCH    /maps/:id/unpublish
```
## Files
```
PATCH    /files/:id/publish
PATCH    /files/:id/unpublish
```
