# Descarga código de Duckietown

Existen dos formas de descargar el código de Duckietown desde Github. La primera y más simple es vía HTTPS mientras que la segunda es vía SSH, método levemente más complejo pero por suerte algunos pasos se deben hacer una sola vez. Los siguientes pasos serán comunes para ambos métodos.

## 1.1 Ingresar a la página que contiene el software
Aquí basta solo ingresar mediante el siguiente [enlace] (https://github.com/Duckietown-Chile/Software). Mientras, dejaremos la página abierta en el navegador.

## 1.2 Abrir una terminal y cambiar al directorio home
Puedes buscarla o simplemente presionar `Ctrl + ALt + T` en tu teclado. Una abierta la terminal, debes asegurarte que estás en el directorio *home* de Ubuntu, para acceder a él basta con escribir el comando `cd` y luego clickear `ENTER` en tu terminal. Esto te llevará directamente al directorio si es que no estabas en él.

## 1.3 Clone or download
Ahora debemos volver a la pagina que habíamos abierto inicialmente en el navegador, donde en el extremo superior derecho de la lista de carpetas podemos hallar un botón verde que dice *Clone or download*, lo clickeamos y se desplegará una pequeña pestaña la que dirá *Clone with SSH* o bien *Clone with HTTPS* (el valor por defecto depende de si la habías abierto previamente). En esta pestaña, para ambas opciones aparece una casilla con un texto el cual deberemos copiar.

## 1.4 Clonar carpeta
El siguiente paso es común para clonar via SSH o vía HTTPS, si nunca haz clonado vía SSH debes completar primero los pasos descritos [aquí](google.com), si lo vas a hacer vía HTTPS o ya completaste los pasos descritos en el link alguna vez en tu computador puedes seguir con lo que viene a continuación. Una vez copiado el enlace de la casilla nos dirigimos nuevamente a la terminal donde asegurándonos de que estamos en la carpeta *home* escribimos:
    
    git clone "TEXTOCOPIADO" duckietown
 
Donde `git clone` corresponde a un comando de git que le indíca al mismo git que debe clonar en el directorio actual algun repositorio en específico. En este caso el repositorio lo obtendrá del link que hemos copiado el cual debemos reemplazar en el comando descrito más arriba en donde dice `"TEXTOCOPIADO"` (incluyendo las comillas). Finalmente se escribe `duckietown` para asignar un nombre a la carpeta a crear (en el caso de no escribir un nombre para la carpeta, git, por defecto asigna el nombre del repositorio). Habiendo completado este paso podemos clickear `ENTER`, lo que dará inicio a la descarga del repositorio

## 1.5 Finalizar
Si realizaste el proceso vía HTTPS y no obtuviste ningún error durante la descarga, felicitaciones!, ya estás listo para utilizar el software de duckietown, pero si obtuviste alguna especie de error, deberás completar los pasos descritos en el link del punto 1.4 para luego repetir el proceso del mismo punto, pero con la diferencia de que ahora debes clickear la esquina superior derecha de la pestaña en *Use SSH* y copiar el texto de esa sección.
    
## Utilizando el código de Duckietown



