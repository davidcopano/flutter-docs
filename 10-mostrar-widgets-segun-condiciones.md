# Mostrar widgets según condiciones

Para mostrar widgets según alguna o algunas condiciones, podemos usar una expresión ternaria como la siguiente:

```dart
// ...
void _answerQuestion() {
  setState(() {
    _questionIndex++;
  });
}

@override
Widget build(BuildContext context) {
  return MaterialApp(
    home: Scaffold(
      appBar: AppBar(
        title: Text('My First App'),
      ),
      body: _questionIndex < questions.length // se mostrará el contenido cuando el indice de la pregunta sea menor que la cantidad total de preguntas
          ? Column(
              children: [
                Question(questions[_questionIndex]['questionText']),
                ...(questions[_questionIndex]['answers'] as List<String>)
                    .map((answer) {
                  return Answer(_answerQuestion, answer);
                }).toList()
              ],
            )
          : Center( // cuando no haya ninguna pregunta que mostrar, mostramos este texto
              child: Text('You did it!'),
            ),
    ),
  );
}
// ...
```