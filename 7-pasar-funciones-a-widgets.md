# Pasar funciones a widgets personalizados

Teniendo en cuenta estos archivos...

```dart
// lib/main.dart
// -----------------

import 'package:flutter/material.dart';

import './question.dart';
import './answer.dart';

void main() => runApp(MyCoolApp());

class MyCoolApp extends StatefulWidget {
  @override
  State<StatefulWidget> createState() => _MyCoolAppState();
}

class _MyCoolAppState extends State<MyCoolApp> {
  var questions = [
    'What\'s your favourite color?',
    'What\'s your favourite animal?',
  ];
  var _questionIndex = 0;

  void _answerQuestion() {
    if (_questionIndex == (questions.length - 1)) {
      print('No more questions available!');
    } else {
      setState(() {
        _questionIndex++;
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
            // aquí usamos el widget Question que hemos
            // creado en lib/question.dart
            Question(questions[_questionIndex]),
            Answer(),
            Answer(),
            Answer(),
          ],
        ),
      ),
    );
  }
}
```

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

```dart
// lib/answer.dart
// -----------------

import 'package:flutter/material.dart';

class Answer extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container(
      width: double.infinity,
      child: RaisedButton(
        color: Colors.blue,
        child: Text('Answer 1'),
        onPressed: null,
      ),
    );
  }
}
```

# ¿Cómo podemos pasar la función `_answerQuestion` a nuestros widgets `Answer`?

Al igual que podemos pasar texto a un widget, también podemos pasar un puntero a una función a un widget. 

A este puntero se le llama también **callback**, ya que el widget que lo recibe la llamará en un futuro:

```dart
// lib/main.dart
// -----------------

// ...

// esta función es la que se le pasará al widget
void _answerQuestion() {
  if (_questionIndex == (questions.length - 1)) {
    print('No more questions available!');
  } else {
    setState(() {
      _questionIndex++;
    });
  }
}

Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('My First App'),
        ),
        body: Column(
          children: [
            Question(questions[_questionIndex]),
            Answer(_answerQuestion), // <- se le pasa sin paréntesis, porque no se va a ejecutar inmediatamente en main.dart
            Answer(_answerQuestion), // <- se le pasa sin paréntesis, porque no se va a ejecutar inmediatamente en main.dart
            Answer(_answerQuestion), // <- se le pasa sin paréntesis, porque no se va a ejecutar inmediatamente en main.dart
          ],
        ),
      ),
    );
  }
// ...
```

```dart
// lib/answer.dart
// -----------------

import 'package:flutter/material.dart';

class Answer extends StatelessWidget {
  final Function selectHandler; // <- es la función que se va a recibir y ejecutar

  Answer(this.selectHandler); // <- constructor donde se recibirá la función que se le pase

  @override
  Widget build(BuildContext context) {
    return Container(
      width: double.infinity,
      child: RaisedButton(
        color: Colors.blue,
        child: Text('Answer 1'),
        onPressed: selectHandler, // <- cuando se pulse en el botón, se ejecutará la función que se le haya pasado a este widget
      ),
    );
  }
}
```