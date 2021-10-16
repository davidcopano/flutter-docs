# Primeros pasos en estilos y maquetación

Vamos a dar estilo a nuestro texto de la pregunta y para esto, aquí en el texto, en realidad podemos pasar más que el texto que debe salir. 

Ese es el argumento posicional del widget `Text` que está incorporado en Flutter y en el archivo `material.dart`, sin embargo esto también es un par de argumentos con nombre, por ejemplo el argumento `style`. 

El argumento `style`, si se pasa por encima, toma un objeto `TextStyle`. Esto no es un widget, sino un objeto normal basado en la clase TextStyle que a su vez es proporcionada por `material.dart`:

Para otros estilos como `textAlign`, etc, `Text` tiene ese argumento por nombre que se le puede pasar como el siguiente ejemplo:

**NOTA**: El widget `Container` por defecto es invisible, no tiene nada que se vea en la pantalla, si guardas eso, no cambia, es lo mismo que antes. Sin embargo, lo que podemos hacer con `Container` es que podemos establecer un ancho y puedes establecerlo en `double.infinity`. El enum `double.infinity` te da básicamente un ancho que asegura que el contenedor tome todo el tamaño, todo el ancho que pueda obtener.

```dart
// lib/question.dart
// -----------------

import 'package:flutter/material.dart';

class Question extends StatelessWidget {
  final String questionText;

  Question(this.questionText);

  @override
  Widget build(BuildContext context) {
    return Container(
      width: double.infinity,
      margin: EdgeInsets.all(10),
      child: Text(
        questionText,
        style: TextStyle(
          fontSize: 28,
        ),
        textAlign: TextAlign.center,
      ),
    );
  }
}
```