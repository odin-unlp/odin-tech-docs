**Importante:** Para poder utilizar la api, momentaneamente se deberá solicitar una API Key al mail `datos_abiertos@produccion.gob.ar`

# 1. URLs

La API de ODIN es una API Hypermedia. Las URLs no deben ser construidas por el cliente, sino que éste debe seguir las URLs provistas por la propia API.

- **Estructura jerárquica:** de lo universal a lo particular. Se usa la barra `/` para indicar una relación jerárquica entre recursos.

    *Ejemplo:* `GET /datasets/5f86r`

- **Granularidad media:** los recursos no deben estar anidados a más de dos niveles de profundidad.

    *Mal*: `GET /datasets/5f86r/resources/f9e3b`

    *Bien*: `GET /datasets/5f86r/resources`

- **Uso de sustantivos:** para designar recursos. Sólo se deben emplear verbos para los endpoints de servicio.

    *Mal*: `GET /getAllDatasets`

    *Bien*: `GET /datasets`

- **Uso de plurales:** sólo usar la forma singular de los sustantivos cuando no haya posibilidad alguna de que los recursos tengan múltiples.

    *Mal*: `GET /dataset`

    *Bien*: `GET /datasets`

- **camelCase:** lowerCamelCase para los parámetros, tanto en la url como en el body de la request.

    *Ejemplo*: `GET /datasets?filterBy=name`


## Otras consideraciones

- No se debe incluir una barra `/` al final de las URLs. La API no debe admitir URLs que las incluyan, ni incluirlas en los links hypermedia que genere.

    *Mal:* `GET /datasets/5f86r/`

    *Bien:* `GET /datasets/5f86r`


- No se deben usar guiones bajos en las URLs. En el extremo caso de que no fuera posible o conveniente usar camelCase, usar guiones medios para separar palabras.
  ​

- Se deben usar exclusivamente letras minúsculas para las URLs, exceptuando los parámetros camelCase en las query strings.

    *Mal:* `GET /Datasets/5f86r`

    *Bien:* `GET /datasets/5f86r`


- No se deben incluir extensiones de archivo en los endpoints. El tipo de contenido a devolver al cliente estará determinado por el header `Accept` de la request.

    *Mal:* `GET /datasets/5f86r.json`

    *Bien:* `GET /datasets/5f86r`


# 2. Verbos HTTP

- **GET**
- **POST**
- **PATCH**: para las actualizaciones parciales.
- **DELETE**
- **OPTIONS:** para la navegación hypermedia.
- **HEAD:** para otorgar una forma liviana de chequear el estado de un recurso.

## Mapeo CRUD

- Create —> POST
- Read —> GET
- Update —> PATCH
- Delete —> DELETE

# 3. Queries

- **Búsqueda:** se hará por medio del endpoint *search*, con el parámetro *query*. Se admitirán dos clases de búsqueda:

    **Global:**  `GET /search?query=calidad aire`

    Busca en todos los recursos.

    **Particular:**  `GET /datasets/search?query=calidad aire`

    Busca en un recurso en particular, en este caso los datasets.

    Es posible controlar cómo se hace la búsqueda mediante los parámetros *condition* y *match*. *condition* permite que, dado más de un término de búsqueda, determinar si todos ellos deben estar presentes o cualquiera indistintamente:

    **Todos**: `GET /datasets/search?query=1,2,3 (por defecto)`

    **Indistinto**: `GET /datasets/search?query=1,2,3&condition=AND`

    Los términos deben ir separados por coma. *match* permite determinar en qué parte debe estar presente el término de búsqueda:

    **En cualquier lado**: `GET /datasets/search?query=1,2,3 (por defecto)`

    **Al comienzo**: `GET /datasets/search?query=1,2,3&match=BEGINS`

    **Al final**: `GET /datasets/search?query=1,2,3&match=ENDS`

    **Exacto**: `GET /datasets/search?query=1,2,3&match=EXACT`

    *condition* y *match* puden combinarse:

    *Ejemplo*: `GET /datasets/search?query=1,2,3&condition=AND&match=ENDS`


- **Fitrado:** a través de parámetros.

    *Ejemplo*: `GET /datasets?name=Dataset 1`

    Devuelve el dataset llamado Dataset 1.

    *Ejemplo*: `GET /datasets?status.name=Public`

    Devuelve los datasets públicos.

    Es posible controlar cómo se hace el filtrado mediante los parámetros *condition* y *match*. *condition* permite que, dado más de un valor de filtrado, determinar si todos ellos deben estar presentes o cualquiera indistintamente:

    **Todos**: `GET /datasets?name=1,2,3 (por defecto)`

    **Indistinto**: `GET /datasets?name=1,2,3&condition=AND`

    Los valores deben ir separados por coma. *match* permite determinar en qué parte debe estar presente el valor de filtrado:

    **En cualquier lado**: `GET /datasets?name=1,2,3 (por defecto)`

    **Al comienzo**: `GET /datasets?name=1,2,3&match=BEGINS`

    **Al final**: `GET /datasets?name=1,2,3&match=ENDS`

    *condition* y *match* pueden combinarse:

    *Ejemplo*: `GET /datasets?name=1,2,3&condition=AND&match=ENDS`


- **Ordenado:** a través de los parámetros *orderBy* y *sort*. Este último admite ASC o DESC como valores, para ordenar en forma ascendiente o descendiente respectivamente.

    *Ejemplo*: `GET /datasets?orderBy=name&sort=DESC`

    Devuelve los datasets ordenados por nombre en forma descendiente.


- **Limitado:** a través del parámetro *limit*.

    *Ejemplo*: `GET /datasets?limit=10`

    Devuelve 10 resultados.


- **Paginado:** por rango, a través del parámetro *skip* combinado con el parámetro *limit*. El *skip* es el número de elementos a partir de los cuales se comienza a contar la cantidad de ítems especificada por *limit.* El valor por defecto de *limit* es 20.

    El paginado debe usar el timestamp de la request como una suerte de versionado a los fines de no incluir duplicados (incluso aunque los objetos involucrados cambien).

    *Ejemplo*: `GET /datasets?skip=5&limit=30`

    Devuelve los 10 resultados que siguen a los primeros 5 ítems.


- **Respuestas parciales:** permite a los clientes elegir qué información necesitan en lugar de obtener la respuesta completa, lo que es especialmente útil para las aplicaciones móviles (por el ancho de banda limitado). Los datos requeridos van en el campo *fields*, separados por coma para campos completos, y por puntos para atributos en particular.

    *Ejemplo*: `GET /datasets?fields=name`

    *Ejemplo*: `GET /datasets?fields=name,description`

    *Ejemplo*: `GET /datasets?fields=name,description,category.name`


- **Palabras reservadas:** *first*, *last* y *count*. Pueden reservarse otras, según el tipo de dato (por ejemplo: *average*, *max*, *min*).

    **First:**  `GET /datasets/first`

    Devuelve el primer dataset.

    **Last:**  `GET /datasets/last`

    Devuelve el último dataset.

    **Count:**  `GET /datasets/count`

    Devuelve la cantidad de datasets.

- **Recursos relacionados:** posibilita incluir en la response otros recursos que estén relacionados con el recurso que fue requerido. Debe ser posible incluir más de uno separándolos con comas, y también acceder a un atributo en particular (después de un punto).

    *Ejemplo*: `GET /datasets?include=tags`

    *Ejemplo*: `GET /datasets?include=tags.name`

    *Ejemplo*: `GET /datasets?include=tags.name,tags.id`

# 4. Plugins

TBD

# 5. Seguridad

## Autenticación

La API de ODIN será una API privada, es decir que no será posible usarla sin estar autenticado.

Se delegará la autenticación de los usuarios externos en [Kong](https://getkong.org/), que admite varios tipos de autenticación por medio de plugins. La instalación por defecto de ODIN utilizará el plugin de autenticación por JWT.
La autenticación de los usuarios internos se hará por un sistema convencional de user/password con la librería [Passport](http://passportjs.org/).

## Listas de control de acceso

Delegado en [Kong](https://getkong.org/).

## Control de tráfico

Delegado en [Kong](https://getkong.org/).

## CORS

También delegado en Kong. El soporte de la cabecera CORS debe estar habilitado por defecto para todos los clientes.

# 5. I18N y L10N

El soporte de internacionalización y localización se hará a nivel del cliente. El lenguaje por defecto en ODIN será el inglés, tanto para los identificadores en el código fuente como para los comentarios.

# 6. Testeo

Se escribirán suites de tests usando [Mocha](https://mochajs.org/) para cubrir los casos CRUD de cada modelo a través de la API.
