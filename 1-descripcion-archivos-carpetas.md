# Descripción de los archivos y carpetas 

A continuación aparecerá una tabla indicando cada archivo/carpeta y una descripción del mismo

| Archivo/carpeta | Descripción | ¿Hay que modificar su contenido? |
|---|---|---|
| `.idea` | Carpeta con los archivos de configuración de Android Studio | ❌ |
| `.vscode` | **NOTA:** Es posible que no la tengamos. Si la tenemos, es una carpeta con solo archivos de configuración de VSCode | ❌ |
| `android` | Es una carpeta importante. Contiene el proyecto Android de la aplicación, el cual el SDK de Flutter usará para "fusionar" el código Flutter/Dart con este proyecto (cuando el código de Flutter/Dart se compila a código nativo, básicamente se inyectará en este proyecto Android) | ✔️ (la mayoría del tiempo no, pero a veces es necesario hacerlo) |
| `build` | Carpeta en la que se guarda lo que genera Flutter al ejecutarse el proyecto. Puede haber archivos compilados de Android, archivos Java | ❌ (la gestiona Flutter automáticamente) |