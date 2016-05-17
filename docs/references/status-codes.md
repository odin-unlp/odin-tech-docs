 # Éxito
 
 Success                               |               
-------------------------------------- |--------------------------------------------------------
**200 OK**                             | Código genérico de éxito.
**201 Created**                        | Indica que el recurso fue creado exitosamente.     
**202 Accepted**                       | Se aceptó la request, pero todavía no fue procesada. Útil para requests asíncronas.
**204 No Content**                     | La request fue procesada con éxito, pero no hay nada que mostrar. Por ejemplo, después de un DELETE exitoso.
**206 Partial Content**                | El recurso devuelto está incompleto. Se lo suele usar para contenido que ha sido paginado. Por ejemplo, se devuelve la página 5 de 20.

# Error del cliente

Client Error                           |               
-------------------------------------- |--------------------------------------------------------
**400 Bad Request**                    | Error genérico para una request que no puede ser procesada por el servidor.
**401 Unauthorized**                   | El cliente es desconocido para la API y necesita autenticarse primero.    
**403 Forbidden**                      | Los permisos del cliente no son suficientes para acceder a este recurso. Es decir, el recurso es un recurso protegido (desde la perspectiva del usuario que hizo la request).
**404 Not Found**                      | No existe el recurso pedido por el cliente.
**405 Method Not Allowed**             | El usuario no tiene permiso para usar ese método HTTP en particular.
**406 Not Acceptable**                 | El contenido no está disponible en la forma específica en que lo pidió el cliente (por medio de las cabeceras "Accept-*"). Por ejemplo, el cliente pidió un recurso en XML pero sólo está disponible en JSON.
**410 Gone**                           | Indica que el recurso estaba disponible pero ya no más (de manera permanente).
**415 Unsupported Media Type**         | La request tiene un media type que no está admitido por el servidor. Por ejemplo, el cliente ha subido una imagen en SVG pero el servidor sólo recibe JPG o PNG.

# Error del servidor

Server Error                           |               
-------------------------------------- |--------------------------------------------------------
**500 Internal Server Error**          | La request parece estar bien, pero hubo un problema en el servidor. El cliente no tiene nada que ver, y tampoco puede hacer nada al respecto.
**501 Not Implemented**                | La API no ha implementado el método usado para hacer la request. Por ejemplo, el método PUT.