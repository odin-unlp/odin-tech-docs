**Duración:** Lunes 17/10/16 - Miercoles 09/11/16

# Alcance
Sprint de subcategorías, roles, correción de bugs y mejoras

## Objetivo
Generar subcategorías dentro de categorías, y desarrollar roles planteados.
Finalizar las tareas en backlog del sprint anterior.
Continuar con la corrección de bugs, priorizando los errores bloqueantes levantados por el equipo de datos.

# Tareas

## API
1. Agregar campos `parent` y `subcategories` en `Category`, el cual es una relación recursiva
2. Instalar, configurar e integrar sails-permissions
3. Generar roles:
    - SuperAdmin
    - Admin
    - Guest
4. Implementar permisos para cada rol
5. Completar seeds de config
    - Estado revisión
    - Estado rechazado
6. Agregar seeds de subcategorías
7. Archivo .txt junto al zip de dataset (#26)
8. Límite de registros en un archivo para la creación de mapa (#159)
9. Crear Geojson desde un archivo KML (#241)
10. Cron para backup (#149)
11. Agregar seed de config para campos adicionales (#248)
12. Implemetar sails-migrations
13. FileType multiple Mimetypes
14. Despublicar en cadena (#207)
15. Agregar los campos necesarios al modelo Basemap

## Admin
1. Agregar sección "Mi Perfil"
2. Instalar y configurar angular-permission
3. Mapear permisos de la api
4. Validar permisos para cada acción en el admin
5. Agregar dropdown `role` en el formulario de `User`, incorporandole un tooltip (globo de diálogo) que muestre un link. Dicho link informará los permisos de cada rol
6. Agregar pantalla **"En revisión"**, que liste los recursos (files, maps, charts) que tengan dicho estado
7. Agregar modulo "Crear subcategoría" dentro de categoría
8. Completar filtros y búsquedas en pantallas que no lo tengan
9. Refactorizar pantalla de configuraciones
10. Agregar pantalla "Ver datasets destacados"
11. Agregar botón "rechazar" en recursos (files, maps, charts) con estado "en revisión"
12. Editar los formularios de los modelos que tengan categorías relacionadas
13. No permitir caracteres especiales en etiquetas (#227)
14. Agregar form para permitir crear mapa desde un archivo KML (#241)
15. Agregar configuración para Captcha y Analytics
16. Agregar config para campos adicionales (additionalFields) (#248)
17. Cambiar los títulos a singular (#255)
18. Agregar campos en el formulario de basemap
19. Cambiar nombre Archivos por Recurso (#261)
20. Error de mimetype desconocido, alerta al usuario (#251)
21. Fecha de relevamiento no debe poder elegirse futura (#228)
22. Ajustes de diseño
23. Previsualizar el archivo como tipo tabla en el admin (#252)
23. Previsualizar el archivo como tipo PDF en el admin (#252)
24. Permitir múltiples mimetypes en un FileType
25. Campos por defecto (organización y usuario) (#245)
26. Agregar spinner en todas las pantallas

## Frontend
1. Agregar filtros por subcategorías (si la categoría no tiene subcategorías no mostrar filtro)
2. Zoom de mapa en el frontend (#253)
3. Paginación con filtros (#274)
4. Crear pantalla de formulario de contacto
5. Crear pantalla de Términos y condiciones
6. Acotar la cantidad máxima de caracteres en el listado de datasets
7. El límite del listado del frontend lo tome desde las configs

## Otros
1. Analizar gráficos PowerBi

# Prioridades
1. Instalar, configurar e integrar sails-permissions
2. Generar roles:
    - SuperAdmin
    - Admin
    - Guest
3. Implementar permisos para cada rol
4. Instalar y configurar angular-permission
5. Validar permisos para cada acción en el admin


