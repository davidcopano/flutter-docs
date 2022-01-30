# Palabras clave `final` vs `const`

## `final`

La palabra clave `final` se utiliza para establecer el valor de una variable y no puede ser alterada en el futuro, ni ningún tipo de operación realizada sobre estas variables puede alterar su valor.

```dart
// sin tipo de dato
final myNumber1;
final myNumber2 = 2;

// con tipo de dato
final String myString1;
final String myString2 = 'hello 2';
```

Si intentamos reasignar las mismas variables, se mostrará un error.

## `const`

La palabra clave `const` en Dart se comporta exactamente como la palabra clave `final`. **La diferencia entre `final` y `const` es que `const` hace que la variable sea constante en tiempo de compilación**. Usar `const` en un objeto, hace que todo el estado del objeto se fije estrictamente en tiempo de compilación y que el objeto con este estado se considere congelado y completamente inmutable:

```dart
// esto DARÁ error
const date = new DateTime.now();

// esto NO DARÁ error
final date = new DateTime.now();
```