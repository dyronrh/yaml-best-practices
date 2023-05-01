# YAML DOCUMENTATIONS
<img src="https://upload.wikimedia.org/wikipedia/commons/f/f8/YAML_Logo.svg" alt="yaml" title="yaml" />


Un fichero YAML es un archivo de texto que se utiliza para almacenar datos estructurados en un formato legible por humanos. El nombre YAML es un acrónimo recursivo que significa "YAML Ain't Markup Language" (YAML no es un lenguaje de marcado), lo que refleja su enfoque en la simplicidad y la facilidad de uso.

Los archivos YAML se componen de una serie de pares de clave-valor, donde cada par de clave-valor está separado por dos puntos (:), y los valores se definen mediante una indentación. Esto hace que los archivos YAML sean fáciles de leer y entender.

Los archivos YAML se utilizan comúnmente en la configuración de aplicaciones, la creación de archivos de configuración, la definición de plantillas de recursos en la nube y la definición de pipelines de integración continua y entrega continua. YAML es también un formato común para el intercambio de datos entre diferentes aplicaciones o lenguajes de programación.

En resumen, un fichero YAML es un archivo de texto que se utiliza para almacenar datos estructurados de forma legible y fácil de entender.


## YAML best practices

10 Buenas practicas con yaml.


¡Por supuesto! Aquí te comparto algunas buenas prácticas para trabajar con YAML:

### 1 Formato consistente: 
Utiliza un formato consistente en todas tus definiciones YAML. Utiliza el mismo número de espacios para las indentaciones y para separar claves de valores.
```yaml
version: '3'
services:
  web1: 
    image: nginx:latest
    volumes:
      - ./src:/usr/share/nginx/html
    restart: always
    ports:
      - 80:80
  web2:
    image: nginx:latest
    volumes:
      - ./src:/usr/share/nginx/html
    restart: always
    ports:
      - 81:80
  web3:
    image: nginx:latest
    volumes:
      - ./src:/usr/share/nginx/html
    restart: always
    ports:
      - 82:80
```
### 2 Comentarios: 
Utiliza comentarios para explicar el propósito y el contenido de tus archivos YAML. Esto ayuda a otros a entender tus definiciones y a ti mismo en el futuro cuando revisas tu propio código.
```yaml
version: '3' #version de docker
services:
  web1: 
    image: nginx:latest #imagen del servicio
    volumes:
      - ./src:/usr/share/nginx/html
    restart: always
    ports:
      - 80:80
  web2:
    image: nginx:latest
    volumes:
      - ./src:/usr/share/nginx/html
    restart: always
    ports:
      - 81:80 #exposicion de puerto externo:puerto interno
    networks:
      - web_net    
  web3:
    image: nginx:latest
    volumes:
      - ./src:/usr/share/nginx/html
    restart: always
    ports:
      - 82:80
networks:
    web_net:
        driver: bridge
```
### 3  Uso de listas: 
Utiliza listas siempre que sea posible en lugar de duplicar las mismas claves. Esto hace que sea más fácil de leer y reducir errores.

### 4 Uso de anclas y referencias: 
Utiliza anclas y referencias para evitar duplicar definiciones. Esto reduce el tamaño del archivo y hace que sea más fácil de mantener.

### 5 Validación: 
Valida tus archivos YAML para asegurarte de que se adhieren a la sintaxis correcta y que son válidos.

### 6 Usa constantes en lugar de valores literales: 
  Al definir constantes, podemos asignar un valor a una variable y luego usar esa variable en todo el archivo YAML. Esto hace que sea más fácil actualizar el valor en una sola ubicación y actualizar automáticamente todas las instancias de ese valor en todo el archivo YAML.
  
```yaml
# Ejemplo 1: Definición de constante
constants:
  MAX_USERS: 100

# Ejemplo 2: Uso de constante
database:
  name: my_database
  max_users: ${constants.MAX_USERS}

# Ejemplo 3: Uso de constante en una lista
servers:
  - name: server1
    max_users: ${constants.MAX_USERS}
  - name: server2
    max_users: ${constants.MAX_USERS}
  
# Ejemplo 4: Uso de constante en un objeto anidado
service:
  name: my_service
  settings:
    max_users: ${constants.MAX_USERS}
    timeout: 60
```
### 7 Documentación: 
Documenta tus archivos YAML para que los demás puedan entenderlos fácilmente y utilizarlos correctamente.

### 8 Control de versiones: 
Utiliza un sistema de control de versiones para tus archivos YAML, lo que te permite realizar un seguimiento de los cambios y volver a versiones anteriores en caso de errores.

### 9 Seguridad: 
No incluyas información confidencial, como contraseñas o claves de API, en tus archivos YAML. En su lugar, utiliza variables de entorno o archivos de configuración separados.

### 10 Pruebas: 
Realiza pruebas exhaustivas en tus archivos YAML para asegurarte de que funcionan correctamente antes de utilizarlos en producción.


## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.