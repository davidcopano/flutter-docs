# Configurar y usar temas

Para compartir colores y estilos de letra en toda la aplicación, utilizaremos los llamados **temas**. Puedes definir temas para toda la aplicación o utilizar widgets de temas que definan los colores y estilos de letra para una parte concreta de la aplicación. 

De hecho, los temas para toda la aplicación no son más que widgets de `Theme` creados en la raíz de una aplicación por el widget `MaterialApp`.

```dart
// ...
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Personal Expenses',
      theme: ThemeData(
        primarySwatch: Colors.purple,
      ),
      home: MyHomePage(),
    );
  }
}
// ...
```

Si guardamos los cambios y recargamos la aplicación, los widgets propios de Flutter como la barra de navegación superior o el botón redondo flotante tendrán el color púrpura:

![Flutter Color Theme](/images/flutter-themes-1.jpeg?raw=true "Flutter Color Theme")