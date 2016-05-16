La metodología de desarrollo a emplear toma elementos de SCRUM, Incremental Build Model y Spec-Driven Development.

# SCRUM

El proceso de desarrollo estará dividido en sprints de una semana (5 días hábiles).

# Incremental Build Model

Se desarrollará la API módulo por módulo, cada uno de los cuales puede tomar uno o más sprints. 

Idealmente cada sprint abarcará el desarrollo de una pieza de funcionalidad pequeña, pero completa y autocontenida, de acuerdo a la lista de features definida para el release correspondiente.

# Spec-Driven Development

Implica empezar con la descripción y prototipado de la API siguiendo una especificación (spec) para luego proseguir con su implementación. El spec no sólo sirve como una suerte de contrato para el desarrollo de la API, sino que también puede ser usado para generar documentación, tests, SDKs, entre otras utilidades.

Bajo esta metodología se dividirá el proceso de desarrollo en tres etapas:

1. **Spec:** en esta etapa se escribirá el spec de la pieza de funcionalidad a desarrollar durante el sprint. El nivel de profundidad/completitud dependerá de las features definidas para el release correspondiente.

    El formato de spec a utlizar será [API Blueprint](https://apiblueprint.org/). Si bien anteriormente se había utilizado [Swagger](http://swagger.io/) (porque el framework iba a ser Loopback, y Loopback podía importar Swagger), para poder usar la herramienta de testeo automática [Dredd](https://github.com/apiaryio/dredd) (además de toda la suite [Apiary](https://apiary.io/)) es preciso usar este formato.

    A medida que se va describiendo la pieza de funcionalidad, se puede testear el diseño de la API haciendo uso de un servicio de mocking (como el de Apiary), corrigiendo los errores a medida que vayan surgiendo.

    Para escribir el spec se puede utilizar el editor de Apiary, o el que cada desarrollador prefiera.

    *NOTA: En caso de que el equipo de desarrollo prefiera usar Swagger, se utilizará Swagger, pero se deberá tener en cuenta que será necesario escribir los tests spec/implementación manualmente (haciendo uso de otra librería) y que no será posible hacer uso de la suite Apiary. No obstante, nótese que también es posible [convertir de un formato a otro](https://apitransformer.com/).*

    *Duración:* 1 día.

2. **Desarrollo:** se implementará lo descripto en el spec en su totalidad, tal cual se encuentra especificado. 

    *Duración:* 3 días.

3. **Testeo:** se correrá la herramienta de testeo [Dredd](https://github.com/apiaryio/dredd) contra la implementación (en relación al spec) y se corregirán los errores que surjan. 

    *Duración:* 1 día.