# Mostrar un modal inferior

Para mostrar un modal inferior en la pantalla como el siguiente:

![Modal Bottom Sheet](/images/show-modal-bottom-sheet.gif?raw=true "Modal Bottom Sheet")

Puede añadirse el siguiente código:

```dart
import 'package:flutter/material.dart';
// ...
void startAddNewTransaction(BuildContext ctx) {
  showModalBottomSheet(
    context: ctx,
    builder: (bCtx) {
      return Container(
        padding: EdgeInsets.all(32),
        child: Text(
          'Hello!',
          textAlign: TextAlign.center,
        ),
      );
    },
  );
}
// ...
@override
Widget build(BuildContext context) {
  return Scaffold(
    appBar: AppBar(
      title: const Text('Flutter App'),
      actions: [
        IconButton(
          onPressed: () {
            startAddNewTransaction(context); // se llama aquí a la función, pasándole el contexto
          },
          icon: Icon(Icons.add),
        ),
      ],
    ),
    body: Center(
      child: Text('Modal test'),
    ),
    floatingActionButtonLocation: FloatingActionButtonLocation.centerFloat,
    floatingActionButton: FloatingActionButton(
      child: Icon(Icons.add),
      onPressed: () {
        startAddNewTransaction(context); // se llama aquí a la función, pasándole el contexto
      },
    ),
  );
}
````