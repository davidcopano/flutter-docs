# Crear y ejecutar proyecto en Flutter

Para **crear** un proyecto en Flutter, usaremos este comando:

```bash
flutter create first_app
```

**IMPORTANTE: El nombre del proyecto (`first_app` en el ejemplo anterior) NO debe contener los siguientes caracteres:**

- Espacios
- Guiones
- Puntos

Si queremos separar por palabras el proyecto, usaremos guiones bajos.

-----------------------------

Para **ejecutar** el proyecto recién creado, abriremos un terminal e iremos al directorio donde se ha creado el proyecto (`cd first_app` si seguimos el ejemplo anterior) y usaremos este comando:

```bash
flutter run
```

**CONSEJO**: Si usamos VSCode, también podemos ejecutar el proyecto pulsando **Ejecutar > Iniciar depuración** o **Ejecutar > Ejecutar Sin depuración**. Si aparece un desplegable con varias opciones, seleccionar la opción **Dart & Flutter**.

Esto puede ser más conveniente, ya que si hacemos cambios en los archivos y los guardamos, se aplicarán los cambios automáticamente, sin necesidad de hacerlo manualmente presionando `r` o `R` en el terminal mientras se esté ejecutando `flutter run`