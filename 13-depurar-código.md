# Depurar código

Hay veces que pueden salir errores en nuestra aplicación, o no funciona como debería.

Para ello, podemos usar el depurador que trae integrado VSCode junto con la extensión de Flutter para depurar paso a paso nuestro código.

## Ejecutar en modo depuración

Para ejecutar la aplicación en este modo en VSCode, pulsa en **Ejecutar -> Iniciar depuración**, o la tecla **F5** en Windows.

La aplicación empezará a compilar y ejecutarse en este modo.

## Depurar líneas de código concretas

Para depurar líneas de código concretas, pulsa a la izquierda de la línea de código para comprobar el estado de las variables y otros en ese momento:

![Debug breakpoint](/images/debug-breakpoints.gif?raw=true "Debug breakpoint")
![Debug variable status](/images/debug-variable-status.png?raw=true "Debug variable status")

## Vigilar variables concretas

Puedes añadir variables para vigilar sus valores durante la ejecución de la aplicación.

Para ello, en VSCode, en el apartado **Ejecución y depuración -> INSPECCIÓN** del editor, pulsa el botón **+** que aparecerá a la derecha de **INSPECCIÓN** y escribe el nombre de la variable a vigilar:

![Debug watch variables](/images/debug-watch-variables.png?raw=true "Debug watch variables")