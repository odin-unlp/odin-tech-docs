**Duración:** Lunes 11/07/16 - Martes 19/07/16

# Alcance
Sprint de refactorización y testeo.

## Objetivo
Solucionar los errores de los tests y poner algunas configuraciones en la base de datos.


# Tareas

## API

1. Solucionar los errores de los tests de mocha ([Travis](https://travis-ci.org/gcba-odin/odin) debe dar **build passing**)
2. Sacar logWhiteList de `/config/odin.js` y ponerlo en la base de datos (como un seed de Config)
3. Agregar el campo **mimetype** a File y poner en los seeds de FileType su mimetype (sacarlos de `/config/odin.js`)
4. Solucionar las issues encontradas por [Codacy](https://www.codacy.com/app/ODIN/odin/issues) (las que sea posible resolver)
5. Implementar el error 522 Unprocessable Entity para los siguientes casos:

    - Se envía el parámetro **sort** con un valor que no sea `ASC` o `DESC`
    - Se envía el parámetro **condition** con un valor que no sea `AND` o `OR`
    - Se envía el parámetro **match** con un valor que no sea `BEGINS`, `CONTAINS` o `ENDS`

6. Implementar la despublicación automática de una View cuando se despublica su File
7. Implementar la despublicación automática de un Chart cuando se despublica su File
8. Implementar la despublicación automática de un Map cuando se despublica su File


# Prioridades

1. Solucionar los errores de los tests
2. Error 522
3. Despublicaciónes automáticas


# Endpoints

## Views
```
GET      /views
POST     /views
OPTIONS  /views

GET      /views/first
OPTIONS  /views/first

GET      /views/last
OPTIONS  /views/last

GET      /views/count
OPTIONS  /views/count

GET      /views/:id
PATCH    /views/:id
DELETE   /views/:id
HEAD     /views/:id
OPTIONS  /views/:id
```

# Campos

## FileType

- **mimetype**

    *Tipo:* string

    *Max:* 200 carácteres