# Crear aplicación Flutter desde 0

A continuación se muestra un ejemplo de una aplicación creada con Flutter desde 0:

```dart
// lib/main.dart
// -------------

// Importamos los widgets y clases de Flutter Material para poder usarlos.
// También podría usarse el archivo 'cupertino.dart' para tener
// una apariencia muy parecida a los componentes nativos de iOS

// NOTA: Los widgets de material.dart también funcionan si se ejecutara en iOS
import 'package:flutter/material.dart';

/*
  - `void` quiere decir que es una función que no devuelve nada. Dart es un lenguaje fuertemente tipado, por lo que a la hora de declarar funciones es necesario especificar el tipo de dato que devuelve la función que declaremos.
  - `main()` es un nombre de función especial que no puede usarse como nombre de otras funciones, ya que main() es el punto de entrada de las aplicaciones Dart (Dart/Flutter automáticamente llama a la función main() cuando la aplicación empieza a ejecutarse). 
*/
void main() {
  // La función 'runApp' la proporciona Flutter en el archivo anterior
  // que importamos. Se encarga de ejecutar la aplicación mostrando el widget u
  // objeto de clase que le pasemos en el 1er parámetro.

  // En este caso, crearemos un objeto con la clase MyCoolApp declarada.
  runApp(MyCoolApp());
}

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