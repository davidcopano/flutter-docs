# Descripción de los archivos y carpetas 

A continuación aparecerá una tabla indicando cada archivo/carpeta y una descripción del mismo.

**NOTA**: Archivos o carpetas como `.gitignore` no se mencionarán al no ser específicos de Flutter:

| Archivo/carpeta | Descripción | ¿Hay que modificar su contenido? |
|---|---|---|
| 📁 `.idea` | Carpeta con los archivos de configuración de Android Studio | ❌ |
| 📁 `.vscode` | **NOTA:** Es posible que no la tengamos. Si la tenemos, es una carpeta con solo archivos de configuración de VSCode | ❌ |
| 📁 `android` | Es una carpeta importante. Contiene el proyecto Android de la aplicación, el cual el SDK de Flutter usará para "fusionar" el código Flutter/Dart con este proyecto (cuando el código de Flutter/Dart se compila a código nativo, básicamente se inyectará en este proyecto Android) | ⏱️ (la mayoría del tiempo no, pero a veces es necesario hacerlo) |
| 📁 `build` | Carpeta en la que se guarda lo que genera Flutter al ejecutarse el proyecto. Puede haber archivos compilados de Android, archivos Java | ❌ (la gestiona Flutter automáticamente) |
| 📁 `ios` | Es una carpeta importante. Contiene el proyecto iOS de la aplicación, el cual el SDK de Flutter usará para "fusionar" el código Flutter/Dart con este proyecto (cuando el código de Flutter/Dart se compila a código nativo, básicamente se inyectará en este proyecto iOS) | ⏱️ (la mayoría del tiempo no, pero a veces es necesario hacerlo) |
| 📁 `lib` | **Es la carpeta más importante**, es en la que trabajaremos el 99% del proyecto. Es aquí donde añadiremos y escribiremos el código de nuestros archivos Dart (el lenguaje de programación que usamos en los proyectos con Flutter) | ✔️ |
| 📁 `test` | Carpeta en la que se escribe el código de los test de nuestra aplicación (test automatizados) | ⏱️ (será más importante cuando se tenga más experiencia durante el desarrollo con Dart y Flutter, por ahora para empezar la ignoraremos) |
| 📄 `.metadata` | Este archivo registra las propiedades de los proyectos Flutter. Utilizado por la herramienta Flutter para evaluar las capacidades y realizar actualizaciones, etc | ❌ (lo gestiona Flutter automáticamente) |
| 📄 `.packages` | Administra las dependencias internas de Flutter | ❌ (lo gestiona Flutter automáticamente, no hay que borrarlo) |
| 📄 `NOMBRE_PROYECTO.iml` | Administra otras dependencias internas y ajustes de Flutter  | ❌ (lo gestiona Flutter automáticamente, no hay que borrarlo) |
| 📄 `pubspec.lock` |  |  |
| 📄 `pubspec.yaml` | Permite gestionar las dependencias de terceros que tiene el proyecto, fuentes e imágenes que se usan... | ✔️ |