# Instalar paquetes o librerías externas

Teniendo en cuenta este código:

```dart
final now = DateTime.now();
print(now.toString()); // mostrará algo parecido a esto: 2022-02-20 12:59:20.230494
```

Vamos a formatear la fecha. No hay ninguna característica incorporada, ni en Dart ni en Flutter que nos facilite formatear esta fecha. Ahora bien, obviamente, siempre podríamos intentar hacerlo por nuestra cuenta, podríamos escribir nuestro propio código que tome esta cadena y por ejemplo sólo extraiga la parte de la fecha aquí al principio pero escribir ese código por nuestra cuenta sería bastante engorroso y por suerte, hay un paquete, un paquete de terceros que podemos utilizar. 

Si buscas `date format dart` en Google, encontrarás este paquete `intl`:

![intl pub.dev](/images/intl-pubdev.png?raw=true "intl pub.dev")

[pub.dev](https://pub.dev/) es una página importante en el universo de Dart y Flutter, es un sitio, una página web, donde encuentras un montón de paquetes que puedes instalar en tus proyectos Dart/Flutter.

## Instalación

En el apartado **Installing** del paquete en [pub.dev](https://pub.dev/), o en el **README** si lo ves en Github, encontrarás la forma de instalar el paquete.

El procedimiento habitual es el siguiente:

1) Abrir el archivo `pubspec.yaml` y añadir el nombre del paquete junto con la versión:

```yaml
# ...
dependencies:
  intl: ^0.17.0
# ...
```