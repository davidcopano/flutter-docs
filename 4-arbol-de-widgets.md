# Mostrando un árbol de widgets

En base al ejemplo del documento anterior, para conseguir una aplicación más bonita, sería un buen comienzo tener un fondo blanco y tal vez no este texto rojizo con el doble subrayado amarillo:

![Hello Red Text](/images/hello-red-text.jpeg?raw=true "Hello Red Text")

Sólo conseguimos esto aquí porque solo estamos mostrando el widget Text en MaterialApp, y eso es suficiente para llevar algo a la pantalla, pero no tiene ningún estilo por defecto para nuestra aplicación móvil.

No tiene ningún fondo ni ninguna appBar porque para Flutter hay que configurar todo eso manualmente. Hay que tener en cuenta que **Flutter controla toda la UI, todos los píxeles de la pantalla son controlados por tu app Flutter al final**, por el framework Flutter. No toma una aplicación móvil existente y sólo mezcla algunos widgets o algunos componentes, sino que controla toda la aplicación y por lo tanto también tienes que dar instrucciones claras sobre cada detalle.

## El widget `Scaffold`

¿Cuál debería ser el color de fondo de nuestra aplicación? ¿Debería haber una barra de navegación arriba?

Para hacer eso, hay un pequeño widget de ayuda que se puede utilizar llamado `Scaffold`. Es otro widget que está incorporado en `material.dart`. 

**Este widget tiene el objetivo de crear un diseño de página base para nuestra aplicación, por lo que le dará un diseño básico y la estructura y el esquema de color o colores para darle una interfaz de usuario que se parece más a una pantalla de aplicación móvil normal.**

Lo reemplazaremos por el widget `Text` anterior. A continuación se mostrará un ejemplo usando este widget:

```dart
// lib/main.dart
// -------------

import 'package:flutter/material.dart';

void main() {
  runApp(MyCoolApp());
}

class MyCoolApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        // 'Scaffold' acepta un parámetro por nombre llamado 'appBar'. A este
        // parámetro normalmente se le pasa un widget 'AppBar'.

        // 'AppBar' acepta 'title' como parámetro por nombre. Normalmente es un
        // widget 'Text' que contiene una descripción del contenido actual
        // de la aplicación.
        appBar: AppBar(
          title: Text('My First App'),
        ),

        // 'Scaffold' acepta otro parámetro por nombre llamado 'body'. Es el
        // contenido principal, se muestra debajo de la 'appBar'.

        // El widget en el parámetro 'body' del 'Scaffold' se
        // posiciona en la parte superior izquierda del espacio disponible
        // entre la appBar y la parte inferior del 'Scaffold'. Para centrar
        // este widget en su lugar, considera ponerlo en un widget 'Center' y
        // que éste sea el 'body'.
        body: Text('This is my default text!'),
      ),
    );
  }
}
```

## Consejo

**Es recomendable añadir siempre una coma después de cerrar los paréntesis**, porque esto permitirá autoformatear el código de una manera muy legible, y esa es una característica que ofrece la extensión de Flutter para Visual Studio Code y también para Android Studio. 

Puedes formatear tu código con un determinado enlace de teclas y puedes encontrarlo si vas a los atajos de teclado y allí buscas "Formatear documento" en Visual Studio Code, entonces deberías encontrar una combinación de teclas que también puedes cambiar si no estás contento con la predeterminada y con esa tecla, si la presionas, formateas automáticamente tu código para que sea un poco más legible y con estas comas al final de cada línea, Flutter es capaz de formatear esto mejor:

![Code Formatted](/images/code-formatted.png?raw=true "Code Formatted")