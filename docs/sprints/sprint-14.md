**Duración:** Viernes 23/09/16 - Lunes 03/10/16

# Alcance
Sprint de Web Services

## Objetivo
Permitir crear archivos desde WS Rest y Soap, ya sean real time, o con actualización con mayor periodicidad

# Tareas

## API
1. Crear el modelo `Soap`.
2. Crear el modelo `Rest`.
3. Crear la relacion entre `File` y `Soap` / `Rest`
4. Crear el archivo `WebServicesModel.js` que contenga los atributos en común entre ambos modelos.
5. Crear un servicio para obtener los datos desde un WS [Soap](https://github.com/vpulim/node-soap)
6. Crear un servicio para obtener los datos desde un WS Rest
7. Al crear un WS que no sea real time, crear un cron con la periodicidad indicada para obtener nuevos datos
 en caso de que los haya `(if-modified-since)` y persistirlos
8. Al crear un WS real time, las consultas se pasan directamente al WS,
 manteniendo una [caché](https://github.com/ptarjan/node-cache) para no sobrecargar el servidor
9. Actualizar las visualizaciones (mapas y gráficos) cuando los datos de un archivo son actualizados (62)
10. Agregar el campo `dataGuide` en el modelo `File`
11. Agregar campo slug en `Tags`,`FileType` y `Organization`

## Admin
1. Finalizar implementación de diseño
2. Agregar [captcha](https://www.google.com/recaptcha/intro/index.html) para el login
3. Generar submenúes dentro de crear archivo `A partir de un archivo` y `A partir de un servicio web`
4. Generar el módulo de WS (crear/editar)
5. Agregar un link de descarga al manual de usuario (184)
6. Seleccionar que modelos importar desde el importador (218)
7. Agregar campo `Guía de datos` en la creación / edición de un archivo (169)

## Frontend
1. Url friendly en categorías (181)
2. Agregar link a guía de datos en la vista de los datasets, en caso de no tener no mostrar link (169)
3. Tomar las visitas desde analytics (185)

## Otros
1. Implementar google analytics (146)

# Prioridades
1. Crear un servicio para obtener los datos desde un WS [Soap](https://github.com/vpulim/node-soap)
2. Crear un servicio para obtener los datos desde un WS Rest
3. Al crear un WS que no sea real time, crear un cron con la periodicidad indicada para obtener nuevos datos
 en caso de que los haya `(if-modified-since)` y persistirlos
4. Agregar campo slug en `Tags`,`FileType` y `Organization`
5. Generar el módulo de WS (crear/editar)

# Modelos

## WebServicesModel (archivo)

- **id**

    *Tipo:* string

    *Requerido:* sí

    *Único:* sí

    *Max:* 15 carácteres

---

- **url**

    *Tipo:* string

    *Requerido:* sí

    *Max:* 500 carácteres

---

- **attributesAsHeaders**

    *Tipo:* boolean

    *Max:* 500 carácteres

---

- **parameters**

    *Tipo:* json

    *Descripcion:* Parametros clave-valor.

---

## Rest < WebServicesModel

- **datapath**

    *Tipo:* string

    *Max:* 500 carácteres

    *Descripcion:* Define la ruta(xpath o json-path) a los títulos de la tabla.

---

- **titlepath**

    *Tipo:* string

    *Max:* 500 carácteres

    *Descripcion:* Define la ruta(xpath o json-path) a los datos de la tabla.

---

- **token**

    *Tipo:* string

    *Max:* 500 carácteres

    *Descripcion:* Define el token para firmar la consulta.

---

- **tokenSignature**

    *Tipo:* string

    *Max:* 500 carácteres

    *Descripcion:* Nombre del argumento que contendrá la firma.

---

- **tokenAlgorithm**

    *Tipo:* string

    *Max:* 500 carácteres

    *Descripcion:* Identifica el algoritmo a utilizar para la firma.

---

- **username**

    *Tipo:* string

    *Max:* 500 carácteres

---

- **password**

    *Tipo:* string

    *Max:* 500 carácteres


## Soap < WebServicesModel

- **method**

    *Tipo:* string

    *Max:* 500 carácteres

    *Requerido:* sí

    *Descripcion:* Define el nombre de la operación a invocar

---

- **namespace**

    *Tipo:* string

    *Max:* 500 carácteres

    *Requerido:* sí

    *Descripcion:* define el Namespace para la operación
