# Uso de Context Managers en Python para la Gestión de Archivos
## Vicente Arhex

### Definición del Context Manager
En este proyecto, creamos un context manager personalizado llamado gestionar_archivo. Utilizamos el decorador @contextmanager del módulo contextlib. La función que define nuestro context manager acepta dos parámetros: ruta_archivo (la ruta del archivo) y modo (el modo de apertura, como 'r' para lectura o 'w' para escritura).

## Funcionamiento del Context Manager
### Apertura del Archivo
La función gestionar_archivo abre el archivo utilizando los parámetros recibidos (ruta_archivo y modo). Intenta abrir el archivo y lo asigna a una variable llamada archivo.

### Uso del Contexto
Dentro de la función, usamos yield para devolver el objeto archivo al bloque de código que usa el context manager. Este es el punto donde el flujo del programa pasa al bloque dentro del with que utiliza gestionar_archivo.

### Cierre del Archivo
Usamos un bloque finally para asegurarnos de que el archivo se cierre correctamente después de que se hayan realizado todas las operaciones necesarias, independientemente de si ocurrieron errores o no. Verificamos si el archivo fue abierto correctamente antes de intentar cerrarlo.

### Uso del Context Manager
Implementamos dos funciones, leer_archivo y escribir_archivo, para demostrar cómo usar nuestro context manager personalizado.

### Leer un Archivo
La función leer_archivo abre un archivo en modo lectura y luego imprime cada línea del archivo. También manejamos excepciones para casos como archivo no encontrado y otros errores generales.

### Escribir en un Archivo
La función escribir_archivo abre un archivo en modo escritura y escribe varias líneas de texto en él.

### Manejo de Excepciones
El manejo de excepciones es crucial para asegurar que el programa pueda manejar situaciones inesperadas de manera controlada y proporcionar mensajes de error útiles. En la función leer_archivo, capturamos errores como FileNotFoundError para manejar el caso en que el archivo no exista y capturamos cualquier otro error que pueda ocurrir durante la lectura del archivo.