# Introducción a los Maps de Dart

El objeto `Map` es un simple par clave/valor. Las claves y los valores de un mapa pueden ser de cualquier tipo. Un mapa es una colección dinámica. En otras palabras, los mapas pueden crecer y reducirse en tiempo de ejecución.

**CONSEJO: Los mapas son parecidos a los objetos de Javascript**

Podemos declarar un Map de Dart de la siguiente forma:

```dart
var question = {
  'questionText': 'What\'s your favourite color?',
  'answers': ['Black', 'Red', 'Green', 'White'],
};
```

También puede crearse una lista o array de Maps así:

```dart
var questions = [
  {
    'questionText': 'What\'s your favourite color?',
    'answers': ['Black', 'Red', 'Green', 'White'],
  },
  {
    'questionText': 'What\'s your favourite animal?',
    'answers': ['Rabbit', 'Snake', 'Elephant', 'Lion'],
  },
  {
    'questionText': 'What\'s your favourite car manufacturer?',
    'answers': ['Ford', 'Opel', 'Renault', 'BMW'],
  },
];
```