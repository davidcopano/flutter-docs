# Añadir campos de texto (`TextField`)

Para poder añadir campos de texto para que el usuario pueda introducir datos, podemos usar el widget `TextField`:

```dart
// ...
Card(
  elevation: 5,
  child: Container(
    child: Column(
      children: [
        TextField(), // <-
        TextField(), // <-
      ],
    ),
  ),
),
// ...
```