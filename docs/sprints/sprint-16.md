**Duración:** Martes 29/11/16 - Viernes 13/01/17

# Alcance
Sprint de mejoras y corrección de bugs ; Creación de mapas a partir de un archivo KML

## Objetivo
Continuar con las mejoras planteadas, y realizar la corrección de bugs anunciados en bugzilla

# Tareas

## API
1. Agregar campos `parent` y `subcategories` en `Category`, el cual es una relación recursiva
2. Hacer script para modificar las url de descargas de los archivos (#285)
3. Hacer endpoint para envío de mail
4. Crear Geojson desde un archivo KML (#241)
5. Crear endpoint para cada uno de los estados
6. Agregar fechas de cada estado en recursos y visualizaciones
7. Si el usuario que crea un recurso/visualización es guest; ignorar el estado por defecto y ponerlo en borrador

## Admin
1. Solucionar descarga de manual de usuario (#280)
2. Tooltips responsive (#303)
3. Mostrar rol en la lista de usuarios (#325)
4. Sacar min-height fijo en el div de los logs (#293)
5. En configuraciones, mostrar el valor del parámetro a modificar (si es posible) (#295)
6. En configuraciones, No mostrar el botón editar en los campos no configurables (#296)
7. Agregar Autor y categoría al listado de datasets
8. Agregar form para permitir crear mapa desde un archivo KML (#241)
9. Agregar popup en eliminar etiqueta para avisar las relaciones y que permita ir a detalle
10. Ordenar configs por orden alfabético
11. Indicar el tipo de archivo asociado al listar los archivos desde un dataset
12. Sacar ngf-resize en ng-fileUplad para no romper las imágenes subidas
13. Si el usuario es invitado sacar los links Creado Por y Responsables desde los detalles de recurso/visualización.
14. Añadir filtro por tipo de archivo en recursos
15. No permitir crear/borrar estados
16. Acomodar los flujos de estados; utilizando siempre los endpoints correspondientes


## Frontend
1. Previsualizar guía de datos en el front (#289)
2. Mantener la búsqueda realizada en la barra de búsqueda
3. Informar que no se encontraron registros al hacer una búsqueda que traiga 0 resultados
4. Nuevo diseño cards

## Otros
1. Adaptar diseño de website ODIN

# Prioridades
1. Agregar popup en eliminar etiqueta para avisar las relaciones y que permita ir a detalle
2. Previsualizar guía de datos en el front (#289)
