# getters

Un getter es un tipo especial de propiedad, es básicamente una mezcla de propiedad y método.

Para crear un getter, primero hay que definir el tipo de valor que se quiere devolver, y luego la palabra clave `get`:

```dart
// ...
String get resultPhrase {
  String resultText;
  if (resultScore <= 8) {
    resultText = 'You are awesome and innocent!';
  } else if (resultScore <= 12) {
    resultText = 'Pretty likeable!';
  } else if (resultScore <= 16) {
    resultText = 'You are... strange?!';
  } else {
    resultText = 'You are so bad!';
  }
  return resultText;
}
// ...
```

## Ejemplo completo

```dart
import 'package:flutter/material.dart';

class Result extends StatelessWidget {
  final int resultScore;

  Result(this.resultScore);

  // definimos el getter 
  String get resultPhrase {
    String resultText;
    if (resultScore <= 8) {
      resultText = 'You are awesome and innocent!';
    } else if (resultScore <= 12) {
      resultText = 'Pretty likeable!';
    } else if (resultScore <= 16) {
      resultText = 'You are... strange?!';
    } else {
      resultText = 'You are so bad!';
    }
    return resultText;
  }

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Text(
        resultPhrase, // obtenemos el valor devuelto del getter anterior
        style: TextStyle(fontSize: 36, fontWeight: FontWeight.bold),
        textAlign: TextAlign.center,
      ),
    );
  }
}

```
