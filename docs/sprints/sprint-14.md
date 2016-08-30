**Duración:** Miércoles 31/08/16 - Martes 07/09/16

# Alcance
Sprint de subcategorías y roles

## Objetivo
Generar subcategorías dentro de categorías, y desarrollar roles planteados.
Continuar con la corrección de bugs, priorizando los errores bloqueantes levantados por el equipo de datos.

# Tareas

## API
1. Agregar campo `parent` en `Category`, el cual es una relación recursiva
1. Agregar campo `subcategories` en `Category`, el cual es una relación recursiva
2. Instalar, configurar e integrar sails-permissions en **odin**
3. Generar roles:
    - SuperAdmin
    - Admin
    - Guest
5. Implementar permisos para cada rol
6. Agregar seeds de subcategorías
7. Completar seeds de config
    - Estado revisión
    - Estado rechazado

## Admin
1. Agregar sección "Mi Perfil"
2. Instalar y configurar angular-permission
3. Generar roles en el admin:
    - SuperAdmin
    - Admin
    - Guest
4. Implementar permisos para cada rol en el admin
5. Agregar dropdown `role` en el formulario de `User`, incorporandole un tooltip (globo de diálogo) que muestre un link. Dicho link informará los permisos de cada rol
6. Agregar pantalla **"En revisión"**, que liste los recursos (files, maps, charts) que tengan dicho estado
7. Agregar botón "Crear subcategoría" dentro de categoría
8. Agregar pantalla con formulario nueva subcategoría dentro
9. Completar filtros y búsquedas en pantallas que no lo tengan
10. Refactorizar pantalla de configuraciones

## Frontend

# Prioridades
1. Instalar, configurar e integrar sails-permissions en **odin**
2. Generar roles:
    - SuperAdmin
    - Admin
    - Guest
3. Implementar permisos para cada rol
4. Instalar y configurar angular-permission
5. Generar roles en el admin:
    - SuperAdmin
    - Admin
    - Guest
6. Implementar permisos para cada rol en el admin


