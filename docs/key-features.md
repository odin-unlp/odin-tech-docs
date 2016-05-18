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
    

- No se deben incluir extensiones de archivo en los endpoints. El tipo de contenido a devolver al cliente estará determinado por el header `Accepts` de la request.

    *Mal:* `GET /datasets/5f86r.json`
  

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

- **Búsqueda:** se hará por medio del parámetro *search*, con los términos de búsqueda separados por `+`. Se admitirán dos clases de búsqueda:

    *Global:*  `GET /search?query=calidad+aire` 

    Busca en todos los recursos.

    *Particular:*  `GET /datasets/search?query=calidad+aire` 

    Busca en los datasets.


- **Fitrado:** a través de parámetros.

    *Ejemplo*: `GET /datasets?state=public`

    Devuelve los datasets públicos.


- **Ordenado:** a través de los parámetros *orderBy* y *sort*. Este último admite ASC o DESC como valores, para ordenar en forma ascendiente o descendiente respectivamente. 

    *Ejemplo*: `GET /datasets?orderBy=name&sort=DESC`

    Devuelve los datasets ordenados por nombre en forma descendiente.
    

- **Limitado:** a través del parámetro *limit*.

    *Ejemplo*: `GET /datasets?limit=10`

    Devuelve 10 resultados.


- **Paginado:** por rango, a través del parámetro *offset* combinado con el parámetro *limit*. El *offset* es el ID del elemento a partir del cual se comienza a contar la cantidad de ítems especificada por limit. Si no se pasara *limit*, se obtendrían todos los recursos a partir del *offset*. 

    De allí la necesidad de **definir un límite** para la cantidad de registros que una query puede devolver, especialmente cuando se trata de muchos registros, como un dataset extenso. Igualmente para el caso de en que se piden todos los registros de un recurso, como por ejemplo `GET /datasets`.

    El paginado debe ser consistente, es decir usar el timestamp de la request como una suerte de versionado a los fines de no incluir duplicados (incluso aunque los objetos involucrados cambien).

    *Ejemplo*: `GET /datasets?offset=5f86r&limit=30`

    Devuelve los 10 resultados que siguen al ítem número 20.
    

- **Respuestas parciales:** permite a los clientes elegir qué información necesitan en lugar de obtener la respuesta completa, lo que es especialmente útil para las aplicaciones móviles (por el ancho de banda limitado). Los datos requeridos van en el campo *fields*, separados por coma.

    *Ejemplo*: `GET /datasets?fields=name,description`


- **Palabras reservadas:** *first*, *last* y *count*. Pueden reservarse otras, según el tipo de dato (por ejemplo: *average*, *max*, *min*).

    *First:*  `GET /datasets/first`

    Devuelve el primer dataset. 

    *Last:*  `GET /datasets/last`

    Devuelve el último dataset. 

    *Count:*  `GET /datasets/count`

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

Se delegará la autenticación en [Kong](https://getkong.org/), que admite varios tipos de autenticación por medio de plugins. La instalación por defecto de ODIN utilizará OAuth2 para la autenticación, que a su vez requiere el uso de SSL.

## Listas de control de acceso

Delegado en [Kong](https://getkong.org/).

## Control de tráfico

Delegado en [Kong](https://getkong.org/).

## CORS

También delegado en Kong. El soporte de la cabecera CORS debe estar habilitado por defecto para todos los clientes.

# 5. I18N y L10N

El soporte de internacionalización y localización se hará a nivel de frontend. El lenguaje por defecto en ODIN será el inglés, tanto para los identificadores en el código fuente como para los comentarios.

# 6. Testeo

TBD