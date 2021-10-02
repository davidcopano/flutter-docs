# Crear aplicación Flutter desde 0

A continuación se muestra un ejemplo de una aplicación creada con Flutter desde 0:

```dart
// lib/main.dart
// -------------

// Importamos los widgets de Flutter Material para poder mostrarlos.
// También podría usarse el archivo 'cupertino.dart' para tener
// una apariencia muy parecida a los componentes nativos de iOS

// NOTA: Los widgets de material.dart también funcionan si se ejecutara en iOS
import 'package:flutter/material.dart';

void main() {}

// Usamos 'extends' para decirle a Dart que la clase
// que creemos se basará en otra ya creada previamente.
// Solo se puede extender una clase
class MyCoolApp extends StatelessWidget {
  // Para extender la clase StatelessWidget, es necesario que nuestra clase
  // tenga el método 'build', al que se le pasa automáticamente
  // un parámetro BuildContext (contiene metadatos de nuestra aplicación).
  // Flutter llamará automáticamente a este método para mostrar por pantalla
  // el widget que devolvamos.

  // Ya que en Flutter trabajamos con widgets, el método
  // 'build' debe devolver un widget
  Widget build(BuildContext context) {
    // 'MaterialApp' es un widget que proporciona Flutter que hace como una configuración
    // base para convertir la combinación de widgets en una aplicación que
    // puede verse y ejecutarse.

    // 'MaterialApp' acepta lo que se llaman argumentos por nombre (hasta ahora
    // hemos visto argumentos posicionales -1er parámetro, 2do parámetro, etc-)
    // le pasaremos un parámetro llamado 'home', el cual Flutter usará para
    // mostrar por pantalla lo que queramos.

    // A su vez, 'home' aceptará otro widget para así mostrarlo en la aplicación.
    return MaterialApp(
      home: Text('Hello!'),
    );
  }
}
```