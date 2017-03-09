#Trabajando con el robot

##1.Prender el robot
Conectar los dos cables usb a la bateria. EL negro a la izquierda, el rojo/negro a la derecha

##2.Crear una conexion ethernet compartida en tu computador
(fotos pendientes)
 1. Apretar el icono de redes y poner <kbd>editar conexiones</kbd> o <kbd>edit connections</kbd>
 2. seleccionar <kbd>añadir</kbd> o <kbd>add</kbd>
 3. Seleccionar tipo `ethernet` y presionar <kbd>crear</kbd> o <kbd>create</kbd>
 4. Elegir un nombre para la conexión
 5. Ir a ipv4 settings y seleccionar el método `compartido a otros computadores` o `shared to other computers`
 
##3.Conectar el cable ethernet al duckiebot y al pc
 
##4.Confirmar que el robot esté conectado
ejecutar en la terminal (reemplazando robot con el nombre del duckiebot):
    
    ping robot.local    
Y debiera aparecer una respuesta como la siguiente:
    
    PING duckiebot.local (10.42.0.95) 56(84) bytes of data.
    64 bytes from 10.42.0.95: icmp_seq=1 ttl=64 time=0.296 ms
    64 bytes from 10.42.0.95: icmp_seq=2 ttl=64 time=0.423 ms
    64 bytes from 10.42.0.95: icmp_seq=3 ttl=64 time=0.417 ms
    64 bytes from 10.42.0.95: icmp_seq=4 ttl=64 time=0.406 ms
En caso contrario, buscar la ip usando nmap:
1. apretar el icono de redes y poner connection information
2. en la pestaña de la red creada enateriormente, ver la direccion ip del compuitador ej. 10.42.0.1
3. ejecutar en la terminal el siguiente código
    
    nmap -sn 10.42.0.0/24
En caso de no tener instalado nmap, ejecutar primero `sudo apt-get install nmap`
Buscar la ip en los reultado que muestra

##5.Conexión ssh
Abrir una nueva terminal y conectar al duckiebot escribiendo(reemplazando robot con el nombre del robot):
    
    ssh duckiebot@robot.local
    
Escribir `yes` cuando pida confirmar la conexion(solo la primera vez) y luego la contraseña `quackquack`
##6. entrar a  la carpeta duckietown
Entrar a la carpeta de duckietown ejecutando `cd duckietown/`
##7. Actualizar
Actualizar los archivos locales escribiendo en la terminal lo siguiente:
    
    git pull origin master
    
##Utilidades
###Caja
Caja es un explorador de archivos grafico. Se ejecuta escribiendo `caja` en la terminal. (añadir imagen)
###Byobu
Byobu es un emulador de terminal que permite trabajar en varias pestañas.

Se ejecuta escribiendo `byobu` en la terminal.

Las nuevas pestañas se abren con <kbd>F2</kbd> y se alternan con <kbd>alt</kbd> + la flecha izquierda o derecha del teclado
