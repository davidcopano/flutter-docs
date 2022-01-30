# Convertir listas/arrays a widgets

Teniendo en cuenta la siguiente variable conteniendo un array de maps:

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
    'answers': ['Ford', 'Opel', 'Renault'],
  },
];
```

**Queremos mostrar las respuestas de cada pregunta, en lugar de escribirlas a mano** (cada pregunta puede tener 3 o 4 respuestas).

Para ello castearemos la lista de `answers` a una lista de cadenas `List<String>` y usaremos la función `map`. Esta función lo que hace es iterar sobre cada elemento de la lista ejecutando como parámetro la función que le pasemos.

Luego, usaremos el **operador de propagación**, que proporcionará una forma concisa de insertar múltiples valores en una lista. 

Hacemos esto para no añadir una lista a una lista, sino los valores de una lista a otra lista, teniendo sólo una lista sin una lista anidada.

A continuación se mostrará un ejemplo sobre esto:

```dart
// lib/main.dart
// ----------------

// ...
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
          Question(questions[_questionIndex]['questionText']),
          /*
            Puedes añadir tres puntos delante. Lo que hace este operador de propagación, lo que hacen estos tres puntos aquí 
            es que toman una lista que es exactamente lo que tenemos aquí y sacan todos los valores de la lista fuera de ella 
            y los añaden a la lista circundante como valores individuales, de modo que no añadimos una lista a una lista, 
            sino los valores de una lista a una lista, teniendo sólo una lista sin una lista anidada. Así que esto es lo que 
            estamos haciendo aquí y con eso, tenemos una transformación donde transformamos cada Answer en un widget de Answer
          */
          ...(questions[_questionIndex]['answers'] as List<String>)
              .map((answer) {
            return Answer(_answerQuestion, answer);
          }).toList()
        ],
      ),
    ),
  );
}
// ...
```