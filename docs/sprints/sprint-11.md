**Duración:** Lunes 08/08/16 - Viernes 12/08/16

# Alcance
Sprint de frontend y corrección de errores.

## Objetivo
Desarrollar la funcionalidad del Frontend y realizar las correcciones necesarias en la API y el Admin.

# Tareas

## API

1. Desarrollar la descarga de archivos en más de un formato
2. Comprobar los archivos permitidos para subir desde el modelo filetypes
3. Verificar que latitud y longitud no estén vacías
4. Normalizar basemaps
5. Actualizar archivos, reemplazando el archivo
6. Usar el slug del nombre del archivo para guardarlo en disco
7. Actualizar archivos, con borrrado físico del archivo antiguo
8. Carpeta de dataset guardada con nombre en vez de id
9. Crear endpoint para refrescar token
10. Agregar endpoint `/:resource/statistics`, con los hits a cada endpoint del recurso y sus ítems

## Admin
1. Agregar el campo `mimetype` al CRUD de file types
2. Tomar los tipos de archivos permitidos desde la API
3. Agregar al CRUD de File los campos `gatheringDate` y `updated`
4. Actualizar archivos, reemplazando el archivo
5. Avisar al usuario los errores en la creación de mapa
6. Agregar el campo Estado a la edición de datasets

## Frontend
1. Hacer funcionales las categorías
2. Agregar cantidad de datasets al filtrar
3. Quitar la cantidad de vistas de cada dataset en el listado de datasets
4. Colocar las categorías en 3 filas de 3 ítems
5. Hacer funcionales los breadcrumbs
6. Alinear correctamente el separador `|` entre los ítems del breadcrumb
7. Linkear **Especificaciones**, **Términos y condiciones** y **Contacto** al Home
8. Linkear **Ver conjunto de visualizaciones** al Home
9. Cambiar **Más Visitados** por **Más Descargados**
10. Eliminar el link del label de formato
11. Hacer funcionales los filtros por etiquetas al clickearlas
12. Hacer el dropdown de previsualización de archivo
13. Linkear el botón de Twitter del footer a la cuenta **@LABgcba**
14. Implementar la vista de tabla
15. Hacer funcionales los filtros
16. Limitar a 100 carácteres la descripción de los datasets en el Home
17. Hacer el dropdown de descarga de archivo
18. Hacer funcional la búsqueda
19. Maquetar los comentarios
20. Integrar Disqus
21. Tomar las imágenes de las categorías desde la API
22. Implementar el CSS de **Marca BA**
23. Agregar filtro de **Publicado** en datasets y archivos

## Otros
1. Escribir el CHANGELOG

# Prioridades
1. Hacer funcionales las categorías
2. Resolver Authorization frontend
3. Implementar la vista de tabla
4. Colocar las categorías en 3 filas de 3 ítems
5. Hacer funcionales los filtros
6. Implementar el CSS de **Marca BA**
7. Hacer funcional la búsqueda
8. Desarrollar la descarga de archivos en más de un formato
9. Actualizar archivos, reemplazando el archivo
10. Agregar endpoint `/:resource/statistics`, con los hits a cada endpoint del recurso y sus ítems
