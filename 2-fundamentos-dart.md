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
int addNumbers(int num1, int num2) {
  return num1 + num2;
}

void main() {
  int result = addNumbers(1, 2);
  print(result); // mostrará 3
  result = addNumbers(2, 4);
  print(result); // mostrará 6
}
```

- El nombre de la nueva función se llama `addNumbers` (devolverá un valor de tipo entero `int`), y se le pasan 2 parámetros: una variable de tipo entero (`int`) llamada `num1`, y otra variable de tipo entero (`int`) llamada `num2`. Al llamar a esta función en `void main()`, lo que hace es mostrar por pantalla la suma de los 2 parámetros.

## Funciones flecha (=>)

En lugar de que la función 'main' se vea así:

```dart
void main() {
  runApp(MyApp());
}
```

También puedes ver algo que se parece a esto:

```dart
void main() => runApp(MyApp());
```

Tienes `void main()`, luego tienes tus paréntesis, así que es lo mismo que tenemos arriba, pero luego en lugar de llaves, tienes un signo igual y un signo mayor, así que una especie de flecha y luego tienes `runApp(MyApp)`. 

Esto es una sintaxis Dart válida también, **es una abreviatura para las funciones que sólo tienen una y exactamente una expresión, por lo que sólo una línea de código en la función**.

Este tipo de funciones flecha también puede usarse en funciones y métodos de clase propios. **El resultado de esta expresión aquí también será devuelto automáticamente**. Ahora aquí, `runApp` no devuelve nada y por lo tanto nuestra función general no devuelve nada, pero si `runApp` devolviera un valor, entonces este sería devuelto automáticamente por nuestra función aquí también.

Un ejemplo simple sobre esto sería algo así:

```dart
double sum(double num1, double num2) => num1 + num2;

void main() {
  double sumResult = sum(2, 3);
  print(sumResult); // mostrará 5
}
```