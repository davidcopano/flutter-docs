# Hacer widgets scrollables con `SingleChildScrollView`

## NOTA: Mejor usar [el widget `ListView`](21-listviews.md) para conseguir esto

-------------------------------------------------------------------------------------

Por defecto, los widgets `Column` y `Row` no permiten hacer scroll de sus widgets hijos (argumento `children`).

Para arreglar esto, envolvemos nuestro `Column` o `Row` en otro widget de Flutter llamado `SingleChildScrollView`:

```dart
class MyHomePage extends StatelessWidget {
  MyHomePage({Key key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Flutter App'),
      ),
      body: SingleChildScrollView(
        child: Column( // se podrá hacer scroll en toda la pantalla
          crossAxisAlignment: CrossAxisAlignment.center,
          children: [
            Container(
              width: double.infinity,
              child: const Card(
                color: Colors.blue,
                child: Text('CHARTS!'),
              ),
            ),
            UserTransactions(),
          ],
        ),
      ),
    );
  }
}
```

Otra opción para **hacer scrollable un widget concreto** es envolverlo en un `Container`, asignarle un `height` y ponerle como `child` nuestro `SingleChildScrollView`:

```dart
@override
Widget build(BuildContext context) {
  return Container(
    height: 300,
    child: SingleChildScrollView(
      child: Column( // se podrá hacer scroll en los widgets children
        children: [
          // ...
        ],
      ),
    ),
  );
}
```