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

Hay dos formas de acceder al valor de un `TextField`. Depende de ti cuál elegir. También depende de la complejidad del formulario que estés construyendo:

### 1) Guardar el valor introducido cada vez que el usuario escriba

```dart
class MyHomePage extends StatelessWidget {
  // ...
  String titleInput;
  String amountInput;
  // ...

  @override
  Widget build(BuildContext context) {
    // ...
    Column(
      crossAxisAlignment: CrossAxisAlignment.end,
      children: [
        TextField(
          decoration: InputDecoration(labelText: 'Title'),
          onChanged: (value) {
            titleInput = value; // <-- cada vez que cambie el valor, lo guardamos en una variable
          },
        ),
        TextField(
          decoration: InputDecoration(labelText: 'Amount'),
          onChanged: (value) => amountInput = value, // <-- también puede usarse una función flecha
        ),
        TextButton(
          onPressed: () {
            print(titleInput);
            print(amountInput);
          },
          child: const Text('Add Transaction'),
          style: TextButton.styleFrom(
            primary: Colors.purple,
          ),
        )
      ],
    ),
    // ...
  }
}
```

**NOTA**: Usando esta esta forma, Flutter se quejará o nos dará una advertencia en la clase `MyHomePage`, ya que está marcada como inmutable: quiere decir que tiene un campo, una propiedad que cambia o que no es `final`. Eso es cierto, `titleInput` y `amountInput` no son finales, ya que pueden cambiar.

### 2) Usar `TextEditingController`

`TextEditingController` es una clase proporcionada por Flutter con la que puedes asignar dicho controlador a tus campos de texto con la ayuda del argumento `controller`:

```dart
class MyHomePage extends StatelessWidget {
  // ...
  final titleController = TextEditingController();
  final amountController = TextEditingController();
  // ...

  @override
  Widget build(BuildContext context) {
    // ...
    Column(
      crossAxisAlignment: CrossAxisAlignment.end,
      children: [
        TextField(
          decoration: InputDecoration(labelText: 'Title'),
          controller: titleController,
        ),
        TextField(
          decoration: InputDecoration(labelText: 'Amount'),
          controller: amountController
        ),
        TextButton(
          onPressed: () {
            print(titleController.text);
            print(amountController.text);
          },
          child: const Text('Add Transaction'),
          style: TextButton.styleFrom(
            primary: Colors.purple,
          ),
        )
      ],
    ),
    // ...
  }
}
```

**Esta segunda forma es la más cómoda**, ya que Flutter se encargará por detrás de controlar y obtener los valores introducidos por el usuario en los campos de texto. Además, a diferencia de la primera forma, Flutter ya no se quejará o nos dará una advertencia en la clase `MyHomePage` que está como inmutable, ya que todos los campos son finales o `final`.