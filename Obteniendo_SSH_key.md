# Generando una nueva clave SSH

Después de checkear la existencia de alguna clave SSH, puedes generar una nueva clave y agregarla al agente de claves SSH. Si es que no tienes una clave SSH, debes generar una. Estaremos siguiendo los pasos indicados en el tutorial oficial de Github en inglés, puedes revisarlo mediante el siguiente [enlace](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/).

## 1.1 Abrir una terminal y cambiar al directorio home
Puedes buscarla o simplemente presionar `Ctrl + ALt + T` en tu teclado. Una abierta la terminal, debes asegurarte que estás en el directorio *home* de Ubuntu, para acceder a él basta con escribir el comando `cd` y luego clickear `ENTER` en tu terminal. Esto te llevará directamente al directorio si es que no estabas en él.

## 1.2 Genera una clave SSH 
Copia el siguiente texto, substituyendo el e-mail de ejemplo por tu e-mail de Github.

    ssh-keygen -t rsa -b 4096 -C "tu_email@ejemplo.com"
    
Esto debiera crear una nueva clave ssh, utilizando el e-mail que hallas escrito, obtendrás el siguiente mensaje:

    Generating public/private rsa key pair.
    
## 1.3 Completar la información solicitada
Una vez realizado el paso anterior, se te solicitará ingresar un archivo donde guardar la clave, luego se te solicitará agregar una frase como contraseña, recomendamos clickear enter en las tres solicitudes.

    Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Presionar ENTER]
    Enter passphrase (empty for no passphrase): [Presionar ENTER]
    Enter same passphrase again: [Presionar ENTER]
    
# Agregando tu clave SSH al agente-SSH

## 2.1 Iniciar el agente-SSH
Primero debes asegurarte que el agente-SSH esta corriendo, lo iniciamos manualmente mediante el siguiente coando:

    eval $(ssh-agent -s)
    
Obtendremos un mensaje de la siguiente forma

     Agent pid XXXXX

## 2.2 Agregar la clave SSH al agente
Luego debemos agregar la clave SSH al agente, basta con ejecutar el siguiente comando:

    ssh-add ~/.ssh/id_rsa

# Agregando la clave SSH a la cuenta de Github

Para configurar la cuenta de Github usando la clave SSH, debemos agregarla a la cuenta.

## 3.1 Copiar la clave SSH al portapapeles
Para copiar la clave SSH, primero debemos ejecutar un par de lineas de código en el directorio *home*, basta con copiar y pegar:

    sudo apt-get install xclip
    xclip -sel clip < ~/.ssh/id_rsa.pub
    
Donde la primera linea instala xclip, mientras que la segunda utiliza xclip para guardar en nuestro portapapeles el string que contiene nuestra clave SSH.

## 3.2 Abrir las configuraciones de la cuenta y agregar la clave.
En la esquina superior derecha de Github, haz click en tu foto de perfil, y clickea **Settings**, luego aparecerá una lista al lado izquierdo del navegador, haz click en **SSH and GPG key**. Luego pincha sobre el botón verde que dice **New SSH key**.

En el campo del Título agrega una descripción para la nueva llave, por ejemplo si estás usando tu notebook personal, puedes escribir "Notebook Personal Samsung" (puse Samsung porque el mio lo es, pero puedes poner cualquier cosa).

Ahora basta con pegar en el campo "Key" lo que tienes guardado en el portapapeles, basta hacerlo con `CTRL+V` o simplemente click derecho y pegar. Una vez hallas pegado esto, haz click en **Add SSH Key**. Felicidades!, ya terminaste con este tutorial.
