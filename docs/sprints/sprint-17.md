**Duración:** Martes 29/11/16 -

# Alcance
Sprint de mejoras y corrección de bugs

## Objetivo
Continuar con las mejoras planteadas, y realizar la corrección de bugs anunciados en bugzilla

# Tareas

## API
1. Crear migración con nuevas configuraciones
2. Agregar campo tooltip en configuraciónes
3. Hacer partials includes
4. Agregar fecha de despublicación en datasets
5. Agregar campo "Parent" en configs
6. Agregar campo "Category" (site,visualizations, integrations) en configs
7. Crear policy para editar configs (basado en el campo "editable")
8. Agregar type "group" en configs
9. Permitir dejar la categoría sin imágen
10. Agregar fecha de despublicación en datasets

## Admin
1. Generar tabs en las configuraciones y listarlas dependiendo su categoría
2. No mostrar botón editar en caso de ser administrador y la confugración no tenga el campo "editable" en true
3. En caso de que la configuración sea tipo "group", listar todas las configuraciones asociadas
4. Separar el versionado de la url de la api, para que no salte un conflicto cada vez que se hace un pull con una versión nueva en un entorno distinto
5. Mostrar tooltip en las configuraciones que correspondan
6. Revisar el css del administrado
7. Resolver borrado automatico de categoria
8. Permitir desactivar subcategorías
9. Filtro en Organizaciones
10. Agregar tooltip en la creación de gráficos en el campo URL
11. Eliminar el campo "autor" en el listado de Estados
12. Ordenar alfabeticamente la lista de estados
13. Eliminar filtros en el listado de Estados
14. Permitir dejar la categoría sin imágen
15. Submenú en Recursos, gráficos y mapas con estado "En revisión"
16. Cambiar fecha de publicación y actualización en dataset
17. Modificar nombres de roles de usuario
18. Crear subcategorías desde un menú aparte
19. Botón borrar en el detalle de entidades
20. Solucionar error al borrar gráfico/mapa
21. Sacar filtro "Autor" para usuario Invitado
22. Ordenar alfabeticamente los Recursos asociados desde la vista del dataset
23. Inhabilitar URL si se selecciona Tipo de gráfico y vicebersa; en la creación de gráficos

## Frontend
1. Mover filtros seleccionados arriba de todo para que se vean
2. Cuando entras a un dataset desde “Ultimos..” o “Destacados” queda vacío el “historial” ya que no tiene categoria
3. En la vista de dataset, cuando clickeas un tag esto genera una consulta en /datasets?tag=X y no limpia currentCategory, habria que hacer lo mismo que hace el boton del Home “Ver catalogo”
4. Al paginar los datasets, el contenedor de arriba se limpie y el spinner ocupe ese lugar hasta que cargue la info
5. En la vista de dataset, el paginador de recursos deberia cumplir la misma funcionalidad que se pide arriba en categorias (spinner)
6. En la vista de dataset, el paginador de la vista tipo tabla de un recurso, deberia levantar un spinner cuando se cambia de pagina
7. Si se ingresa a “Ver catalogo completo de datasets” y despues entras a una categoria, no se deberia mostrar en la navegacion el nombre de la categoria a la que pertenece el DS
8. Agregar autocomplete en los filtros de organización y etiquetas
9. Ordenar formatos por cantidad de archivos asociados
10. No mostrar formatos con (0)
11. Filtros se desplieguen haciendo click en cualquier parte del rectángulo
12. Al entrar a listados de dataset (ya se por categorías o por otro lado), mantener el spinner hasta que esté todo completo ( al menos el color en las cajitas de filtros y la cantidad de datasets)
13. Filtro por subcategorías
14. Separar el versionado de la url de la api, para que no salte un conflicto cada vez que se hace un pull con una versión nueva en un entorno distinto

## Otros
1. Adaptar diseño de website ODIN

# Prioridades
1. Agregar popup en eliminar etiqueta para avisar las relaciones y que permita ir a detalle
2. Previsualizar guía de datos en el front (#289)
