# Bienvenido a PHP Containers

Hola !

Eres el primer empleado de la StartUp Asturiana **Elephant Containers**. Como el nombre indica, nos dedicamos a mover containers por el mundo y nuestra tecnología esta escrita en PHP.

Necesitamos empezar a ofrecer nuestros servicios lo antes posible, y por eso tu primera tarea es un cotizador de precios.


##¿Que es un cotizador de precios? 
Algo que nos diga en cada uno de nuestros proveedores (Carriers) cuanto cuesta el envio de uno o varios containers entre un puerto de origen y un puerto de destino.


### Puertos
El listado de puertos disponibles esta en un fichero json en :`config/ports.json`. No obstante, el listado inicial no incluye todos los puertos, y en cualquier momento nos pueden dar un fichero con más puertos. Esperamos que estes preparado para más puertos.

### Carriers

Para obtener precios en nuestro sistema hemos firmado acuerdos con tres carriers para utilizar sus rutas. Por desgracia, en este mundo carrier modela la información de una manera diferente y la fuente de datos es diferente:
 * Carrier XML: Este carrier nos ofrece los datos en formato XML. Una vez al mes nos los mandan por correo. Hay una copia de la última version en `config/carriers/carrier-xml.xml`
 * Carrier JSON: Este carrier nos da los datos una vez al mes, pero en JSON. La última versión esta en:`config/carriers/carrier-json.json`
 * Carrier API: Este carrier nos expone los datos en tiempo real en una API. El 93% de las veces funciona. Hemos visto que cuando usamos el parametro limit, falla siempre: En endpoint con la documentación en Swagger es:`https://carrier-api.backendlandia.tech`
 
 
 > Es importante verificar que la fecha del precio no este expirado. En caso de que este expirado, no podemos mostrar el precio al cliente.
 
 
 ## Servicio
 
 El servicio a implementar tiene que ofrecer todas las opciones disponibles para una ruta determinada y su precio.
 
 Por ejemplo
 
 ```javascript
 [
    { 
        "carrier":"JSON",
        "total_price": "500",
        "currency":"USD",
    },
    { 
        "carrier":"XML",
        "total_price": "515",
        "currency":"USD",
    }
 ]
```


Una vez implementada la primera versión. Nos dicen de preguntar que hay un backlog con funcionalidades a añadir.