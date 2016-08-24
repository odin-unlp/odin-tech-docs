**Duración:** Miércoles 24/08/16 - Martes 30/08/16

# Alcance
Sprint de importador de CKAN

## Objetivo
Crear el importador de datos de CKAN, vinculando las tablas existentes con las tablas de ODIN, mediante el uso de la api de CKAN.
Corregir los bugs, priorizando los errores bloqueantes levantados por el equipo de datos.

# Tareas

## API
1. Cambiar de obligatorio a opcional los campos `description` y `address` de Organization
2. Crear filtro para los campos que se devuelven al frontend, y cualquier aplicación que no sea el admin. Filtrar segun corresponda:
    - owner
    - createdBy
    - modelos con estado despublicado
    - modelos borrados lógicamente

## Admin
1. Agregar tab **importar** al sidebar
2. Crear pantalla principal del importador, donde se seleccionen los campos por defecto (dropdowns)
    - Usuario responsable
    - Estado
    - Frequencia de actualización
3. Generar la importación de datos
    1. **Categorías**: [http://data.buenosaires.gob.ar/api/3/action/group_list?q=](http://data.buenosaires.gob.ar/api/3/action/group_list?q=)
    2. **Etiquetas**: [http://data.buenosaires.gob.ar/api/3/action/tag_list?q=](http://data.buenosaires.gob.ar/api/3/action/tag_list?q=)
    3. **Datasets**:
        - Todos: [http://data.buenosaires.gob.ar/api/3/action/package_list?q=](http://data.buenosaires.gob.ar/api/3/action/package_list?q=)
        - Individuales: [http://data.buenosaires.gob.ar/api/3/action/package_show?id=nombredeldataset](http://data.buenosaires.gob.ar/api/3/action/package_show?id=nombredeldataset)
    4. **Recursos**: [http://data.buenosaires.gob.ar/api/3/action/resource_search?query=nombredeldataset](http://data.buenosaires.gob.ar/api/3/action/resource_search?query=nombredeldataset)
        - Dentro de cada recurso hay un campo llamado `url`, desde donde se puede descargar el archivo relacionado
4. Notificar cantidad de datos importados
    - Categorías
    - Etiquetas
    - Organizaciones
    - Datasets
    - Recursos
5. Agregar unidad de tooltip en los gráficos
6. Unificar respuestas Bad Request de la api + i18n
7. Permitir borrado físico en modelos que no tengan relaciones populadas

## Frontend
1. Agregar skip y limit para paginación a la vista de tabla (bugzilla)

## Otros
1. Completar la documentación de instalación
2. Actualizar tests de unidad (mocha)

# Prioridades
1. Cambiar de obligatorio a opcional los campos `description` y `address` de Organization
2. Generar la importación de datos

