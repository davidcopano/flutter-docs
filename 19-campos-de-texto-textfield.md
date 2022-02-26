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

## Modificar estilos del widget `TextField`

Usando el argumento `decoration` de este widget, podemos modificar sus estilos con `InputDecoration`, así como añadir un label o texto explicativo de lo que pide el campo de texto:

```dart
// ...
Column(
  crossAxisAlignment: CrossAxisAlignment.end,
  children: [
    const TextField(
      decoration: InputDecoration(labelText: 'Title'),
    ),
    const TextField(
      decoration: InputDecoration(labelText: 'Amount'),
    ),
    TextButton(
      onPressed: () {},
      child: const Text('Add Transaction'),
    )
  ],
),
// ...
```

## Recoger valor introducido por el usuario