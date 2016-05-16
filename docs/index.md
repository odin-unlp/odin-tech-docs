# Principios

## 1.  Mostly RESTful

Para diseñar la API de ODIN se ha tomado como referencia la definición de REST especificada en el [capítulo nº 5](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm) de la tesis doctoral de Roy Fielding. No obstante, se podrá adoptar otro enfoque si en aspectos particulares éste resulta más apropiado según las necesidades del caso.

## 2. Simplicidad

- Sólo puede haber una URL para cada recurso.
- Deben emplearse nombres concretos y autodescriptivos.
- No se admitirán abreviaturas, excepto aquellas muy ampliamente utilizadas y conocidas (por ejemplo: min, max).
- Si bien se prevee dar soporte a muchos tipos de formato para las responses, en la primera versión sólo se proveerán respuestas JSON.

## 3. Consistencia

Las normas aquí descriptas deben aplicarse de manera uniforme y exhaustiva al desarrollar la API.

## 4. Abstracción

No necesariamente debe haber un endpoint por cada tabla de la base de datos, ni cada parámetro debe equivaler a un campo de una tabla, ni mucho menos el resultado de una query a la base de datos ser serializado y despachado sin más. 

Por un lado es preciso limitar los datos que se envían en la response, y por otro hay que tener en cuenta los casos de uso y las necesidades de datos de los clientes, por ejemplo proveyendo campos calculados o construidos a partir de otros. Todo ello contribuye a mantener bajo control el tamaño de las responses, a reforzar la seguridad de la API y a minimizar el número de requests.

La API debe ser una capa de abstracción sobre los detalles de implementación de ODIN, limitando y estandarizando lo que se expone a través de ella. En otras palabras, la API debe implementar el patrón Façade.

## 5. Autodescriptividad

La API debe poder navegarse sin necesidad de acudir a la documentación, y a la vez documentarse a sí misma. Esto es posible a través de la implementación de Hypermedia con el método OPTION, que además tiene la ventaja de que ya no es necesario tener que versionar la API. Implementar OPTION posibilita incluso la generación automática de la UI de los clientes.

## 6. Modularidad

El núcleo de funcionalidad más elemental de la API debe implementarse en una serie de módulos funcional y lógicamente distintos, que sea posible desarrollar por separado. Estos módulos no necesariamente serán desacoplables. La funcionalidad restante se desarrollará como plugins, que sí deben ser desacoplables.

Una de las ventajas de la modularidad y el empleo de la estructura core/plugins es que la aplicación es fácilmente actualizable, y en el caso de ODIN esta cualidad es muy deseable.

## 7. Extensibilidad

Debe ser posible extender y/o modificar la API mediante plugins. El sistema de plugins debe implementar el patrón Inversion of Control, y los plugins no deben poder alterar el código fuente de la API.

# Convenciones

TBD

# Licencia

La API de ODIN será un proyecto de código abierto y se ofrecerá bajo la licencia MIT.
