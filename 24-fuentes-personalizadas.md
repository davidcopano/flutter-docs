# Añadir fuentes de letra personalizadas

Para añadir fuentes de letra personalizadas a una aplicación Flutter, podemos seguir los siguientes pasos:

1) En el directorio raíz del proyecto, crear una carpeta (puede tener cualquier nombre, aunque `assets` y luego una subcarpeta ahí llamada `fonts` sería lo correcto)

2) Descargar en un sitio web como Google Fonts o parecido la fuente o fuentes que vaya a usar el proyecto
 
3) Copia o mueve estos archivos de fuentes (normalmente archivos `.ttf`) a la carpeta/subcarpeta que creaste antes (`assets/fonts` en nuestro caso)

4) Abrir el archivo `pubspec.yaml` y añadir los archivos de las fuentes como en el siguiente ejemplo:

```yaml
# ...
fonts:
    - family: OpenSans
      fonts:
        - asset: assets/fonts/OpenSans-Regular.ttf
        - asset: assets/fonts/OpenSans-Bold.ttf
          weight: 700
  fonts:
    - family: Quicksand
      fonts:
        - asset: assets/fonts/Quicksand-Regular.ttf
        - asset: assets/fonts/Quicksand-Bold.ttf
          weight: 700
# ...
```

5) En el widget `MaterialApp`, dentro del `ThemeData`, añadimos la fuente de la siguiente forma:

```dart
// ...
return MaterialApp(
  title: 'Personal Expenses',
  theme: ThemeData(
    primarySwatch: Colors.purple,
    accentColor: Colors.amber,
    fontFamily: 'Quicksand', // importante: el nombre de la fuente DEBE tener el nombre EXACTO del archivo pubspec.yaml
  ),
  home: MyHomePage(),
);
// ...
```

Si quitas y vuelves a poner el livereload de la aplicación, se mostrará la nueva fuente en todos los textos de la aplicación.

## Usar fuentes personalizadas distintas en algunos textos

Si por ejemplo has declarado que la aplicación tiene 2 fuentes personalizadas de texto y quieres usar una en concreto solo para algún texto concreto, puedes hacerlo de la siguiente forma:

```dart
// ...
Text(
  transactions[index].title,
  style: const TextStyle(
    fontSize: 16,
    fontWeight: FontWeight.bold,
    fontFamily: 'OpenSans', // aquí declaramos la fuente personalizada
  ),
),
// ...
```