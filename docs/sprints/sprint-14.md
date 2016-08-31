**Duración:** Miércoles 31/08/16 - Viernes 09/09/16

# Alcance
Sprint de subcategorías y roles

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
5. Implementar permisos para cada rol
6. Completar seeds de config
    - Estado revisión
    - Estado rechazado
7. Agregar seeds de subcategorías

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

## Frontend
1. Agregar filtros por subcategorías (si la categoría no tiene subcategorías no mostrar filtro)

# Prioridades
1. Instalar, configurar e integrar sails-permissions
2. Generar roles:
    - SuperAdmin
    - Admin
    - Guest
3. Implementar permisos para cada rol
4. Instalar y configurar angular-permission
5. Validar permisos para cada acción en el admin


