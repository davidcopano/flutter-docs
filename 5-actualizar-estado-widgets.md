# Actualizar el estado de widgets con StatefulWidget

## ¿Qué es el estado/state de un widget?

**En general, el estado son datos o información que tu aplicación o los widgets de tu aplicación utilizan. El estado puede ser cosas como un nombre de usuario o, en nuestro caso, el índice de la pregunta que queremos mostrar.**

Así que el estado de la aplicación sería cosas como si el usuario está autenticado o si estamos construyendo una aplicación que los usuarios pueden usar para encontrar nuevos trabajos, podríamos tener los trabajos generales que cargamos desde un servidor. El estado del widget podría ser cosas como la entrada actual del usuario entrada del usuario o si estamos cargando datos y queremos mostrar un spinner o como en nuestra aplicación, el estado del widget de la aplicación que tenemos podría ser qué pregunta está actualmente seleccionada y ese estado puede y típicamente cambiará en una aplicación.

## Diferencias entre widgets sin estado (Stateless) y con estado (Stateful)

Aunque puedes añadir (y también cambiar) propiedades en un `StatelessWidget`, no hay forma de decirle a Flutter que debe volver a ejecutar `build()` ante tales cambios.

Todos los widgets (es decir, tanto `Stateless` como `Stateful`) pueden recibir datos a través de sus constructores. Pero sólo los `StatefulWidget` pueden tener propiedades de clase donde pueden actualizar los valores y volver a ejecutar el método `build()`.

El método `setState()` de los `StatefulWidget` es un "activador" que informa a Flutter de que necesita volver a ejecutar el método `build()` del widget.

![Stateless vs Stateful](/images/flutter-stateless-stateful-widgets-slide.jpg?raw=true "Stateless vs Stateful")

### Ejemplo de widget Stateful

```dart
// lib/main.dart
// -------------

import 'package:flutter/material.dart';

void main() => runApp(MyCoolApp());

class MyCoolApp extends StatefulWidget {
  @override
  State<StatefulWidget> createState() => MyCoolAppState();
}

class MyCoolAppState extends State<MyCoolApp> {
  var questions = [
    'What\'s your favourite color?',
    'What\'s your favourite animal?',
  ];
  var questionIndex = 0;

  void answerQuestion() {
    if (questionIndex == (questions.length - 1)) {
      print('No more questions available!');
    } else {
      /*
        setState() es una función que obliga a Flutter a volver a renderizar la 
        interfaz de usuario. Sin embargo, no toda la interfaz de usuario de toda 
        la app, en cambio lo que hace setState al final es llamar a build() de 
        nuevo de este widget donde llamas a setState
      */
      setState(() {
        questionIndex++;
      });
    }
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('My First App'),
        ),
        body: Column(
          children: [
            Text(questions[questionIndex]),
            RaisedButton(
              child: Text('Answer 1'),
              onPressed: answerQuestion,
            ),
            RaisedButton(
              child: Text('Answer 2'),
              onPressed: answerQuestion,
            ),
            RaisedButton(
              child: Text('Answer 3'),
              onPressed: answerQuestion,
            ),
          ],
        ),
      ),
    );
  }
}
```