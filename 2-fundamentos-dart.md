# Fundamentos de Dart

Para aprender Dart, lo mejor es usar esta web para escribir y ejecutar el código en este lenguaje: https://dartpad.dev/

## Lo más básico

Tomando como ejemplo el siguiente código:

```dart
void main() {
  for (int i = 0; i < 5; i++) {
    print('hello ${i + 1}');
  }
}
```

Se explicará a continuación qué significa cada término:

- `void` quiere decir que es una **función que no devuelve nada**. Dart es un lenguaje fuertemente tipado, por lo que a la hora de declarar funciones es necesario especificar el tipo de dato que devuelve la función que declaremos
- `main()` es un nombre de función especial que **no** puede usarse como nombre de otras funciones, ya que `main()` es el **punto de entrada de las aplicaciones Dart** (Dart/Flutter automáticamente llama a la función `main()` cuando la aplicación empieza a ejecutarse). 

Por ello, el archivo `lib/main.dart` (y dentro de él la función `void main() { }` ) es un archivo especial que Flutter buscará y ejecutará cuando se lance la aplicación. En él, es donde se tendrá que declarar los widgets/elementos visuales que aparecerán en pantalla
- `for(...)` es un bucle for, que empieza declarando un entero (`int`) llamado `i` que empieza en 0, y llega hasta 5 aumentando en 1, y muestra por consola (la función `print`) la variable `i` 5 veces (1, 2, 3, 4 y 5)