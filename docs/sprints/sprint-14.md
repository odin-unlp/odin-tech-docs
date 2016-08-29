**Duración:** Miércoles 31/08/16 - Martes 07/09/16

# Alcance
Sprint de subcategorías y roles

## Objetivo
Generar subcategorías dentro de categorías, y desarrollar roles planteados.
Continuar con la corrección de bugs, priorizando los errores bloqueantes levantados por el equipo de datos.

# Tareas

## API
1. Agregar campo `subcategory` en `Category`
2. Agregar relación recursiva en `Category`
3. Agregar campo `role` en `User`
4. Generar roles:
    - SuperAdmin
    - Admin
    - Guest
5. Implementar permisos para cada rol

## Admin
1. Implementar authorization via roles
2. Agregar dropdown `role` en el formulario de `User`, incorporandole un tooltip (globo de diálogo) que muestre un link. Dicho link informará los permisos de cada rol
3. Agregar sección "Mi Perfil"
3. Completar filtros y búsquedas en pantallas que no lo tengan

## Frontend

## Otros
1. Actualizar tests de unidad (mocha)

# Prioridades
1. Implementar authorization via roles
2. Generar roles:
    - SuperAdmin
    - Admin
    - Guest
3. Implementar permisos para cada rol

