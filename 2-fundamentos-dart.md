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

## Declarar nuevas funciones

Para declarar nuevas funciones y usarlas, puede tomarse el siguiente código de ejemplo:

```dart
void addNumbers(int num1, int num2) {
  return num1 + num2;
}

void main() {
  print(addNumbers(1, 2));
}
```

- El nombre de la nueva función se llama `addNumbers`, y se le pasan 2 parámetros: una variable de tipo entero (`int`) llamada `num1`, y otra variable de tipo entero (`int`) llamada `num2`. Al llamar a esta función en `void main()`, lo que hace es mostrar por pantalla la suma de los 2 parámetros.