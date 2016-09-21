**Duración:** Viernes 23/09/16 - Lunes 03/10/16

# Alcance
Sprint de Web Services

## Objetivo
Permitir crear archivos desde WS Rest y Soap, ya sean real time, o con actualización con mayor periodicidad

# Tareas

## API
1. Hacer el modelo, routes y controller de `Soap`.
2. Hacer el modelo, routes y controller de `Rest`.
3. Crear la relacion entre `File` y `Soap` / `Rest`
4. Crear el archivo `WebServicesModel.js` que contenga los atributos en común entre ambos modelos.
5. Crear tarea para obtener los datos desde un WS [Soap](https://github.com/vpulim/node-soap)
6. Crear tarea para obtener los datos desde un WS Rest
7. Al crear un WS que no sea real time, crear un cron con la periocidad indicada para obtener nuevos datos
 en caso de que los haya `(if-modified-since)` y persistirlos
8. Al crear un WS real time, las consultas se pasan directamente al WS,
 manteniendo una [caché](https://github.com/ptarjan/node-cache) para no cargar demasiado al servidor
9. Actualizar las visualizaciones (mapas y gráficos) cuando los datos de un archivo son actualizados (62)

## Admin
1. Finalizar de implemetar el css propuesto
2. Agregar caché para el login
3. Generar submenúes dentro de crear archivo `A partir de un archivo` y `A partir de un servicio web`
4. Generar el módulo de WS (crear/editar)
5. Agregar un link de descarga al manual de usuario (184)
6. Seleccionar que modelos importar desde el importador

## Frontend
1. Agregar filtros por subcategorías (si la categoría no tiene subcategorías no mostrar filtro)
2. Url friendly en categorías (181)

# Prioridades
1. Instalar, configurar e integrar sails-permissions
2. Generar roles:
    - SuperAdmin
    - Admin
    - Guest
3. Implementar permisos para cada rol
4. Instalar y configurar angular-permission
5. Validar permisos para cada acción en el admin


