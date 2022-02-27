# El widget `ListView`

En lugar de tener nuestro `Column` con un `SingleChildScrollView`, hay otro widget incorporado en Flutter que podemos utilizar para asegurarnos de que tenemos automáticamente una columna o fila con scroll.

Este widget se llama `ListView`. Podemos usar este widget de dos formas:

![ListView](/images/listview.png?raw=true "ListView")

El más recomendado es la segunda forma, con `ListView.builder()`, ya que a diferencia de `ListView(children: [])`, sólo carga los widgets que son visibles en pantalla. 

Podemos usar `ListView.builder()` de la siguiente forma:

```dart

```