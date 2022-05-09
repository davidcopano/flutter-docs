# Añadir imágenes

## Imágenes en local

Para mostrar imágenes almacenadas localmente dentro de la aplicación, podemos seguir los siguientes pasos:

1) En el directorio raíz del proyecto, crear una carpeta (puede tener cualquier nombre, aunque `assets` y luego una subcarpeta ahí llamada `images` sería lo correcto)

2) Descargar una imagen de internet o de otros medios, y copiarla o moverla a la carpeta creada anteriormente (`assets/images` en este caso)

3) Abrir el archivo `pubspec.yaml` y añadir los archivos de las imágenes como en el siguiente ejemplo:

```yaml
# ...
  assets:
      - assets/images/waiting.png
# ...
```

4) En el código de la aplicación, usar el método `Image.asset` como el siguiente ejemplo:

```dart
// ...
Column(
  children: [
    Text(
      'No transactions added yet!',
      style: Theme.of(context).textTheme.headline6,
    ),
    const SizedBox(
      height: 20,
    ),
    SizedBox(
      height: 200,
      child: Image.asset('assets/images/waiting.png'), // usamos el constructor `asset` para mostrar la imagen guardada
    ),
  ],
)
// ...
```

## Imágenes de internet

Para mostrar imágenes guardadas en un servidor de internet, usamos el método `Widget.network`:

```dart
Image.network('https://picsum.photos/250?image=9'),
```