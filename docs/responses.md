# Estructura de las responses

## JSON

### GET

En el caso de que se devuelva un solo registro, en data no va un array, sino ese registro sólo. Y si no hay registros, en data habrá un objeto vacío.

```json
{
   "meta": {
       ...
   },
   "data": [
     {
         ...
     },
     {
         ...
     },
     {
         ...
     }
   ],
   "links": {
       ...
   }
}
```

### POST

```json
{
   "meta": {
       ...
   },
   "links": {
       ...
   }
}
```

### PATCH

```json
{
   "meta": {
       ...
   },
   "links": {
       ...
   }
}
```

### DELETE

```json
{
   "meta": {
       ...
   },
   "links": {
       ...
   }
}
```

### HEAD

```json
Una response a una request HEAD no incluye un body.
```

### OPTIONS

```json
{
   "meta": {
       ...
   },
   "methods": [
       {
           "verb": ...,
           "url": ...,
           "headers": {
               ...
           },
           "parameters": {
               ...
           }
       },
   ]
}
```