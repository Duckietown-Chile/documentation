# Calibración de la cámara
## Calibración intrínseca
Conectar al duckiebot por ssh
    
    shh -X duckiebot@robot.local
Cambiar a la carpeta duckietown

    duckiebot $ cd ~/duckietown 
Hacer source

    duckiebot $ source environment.sh 
    duckiebot $ source set_ros_master.sh alphaduck
Lanzar el nodo para calibracion intrínseca

    duckiebot $ roslaunch duckietown intrinsic_calibration.launch veh:=alphaduck
    
A continuacion se abrirá una ventana. Toma el tablero de calibración (ajedrez) y posicionalo frente al duckiebot. 

Mueve el tablero frente a la camara variando la distancia y girandolo hasta que las barras de los parametros _x_, _y_, _yaw_ y _size_ esten en verde. Se necesitan varias tomas para que la calibracion quede bien, pero no es necesario exagerar.
Una vez que tenga suficientes muestras, el boton <kbd>calibrate</kbd> se activará.Presionelo y la pantalla se oscurecerá por unos minutos. Cuando finalize, seleccione <kbd>commit</kbd>
**TO DO:
escribir explicación para mac (xquartz)**

###Nota para usuarios de mac:

Deben descargar xquartz https://www.xquartz.org/ lo cual les permitirá correr ssh como si estuvieran en linux luego abrir aplicacion-> terminal y proseguir de manera normal.

#Calibración de ruedas
conectarse al robot via ssh

    user:~$ ssh -X duckiebot@duckiebot.local
    
conectarse a byobu

    duckiebot@duckiebot:~$ byobu
    
hacer source


    duckiebot@duckiebot:~$ cd /duckietown
    
    duckiebot@duckiebot:~/duckietown$ source environment.sh 
    
    duckiebot@duckiebot:~/duckietown$ source set_vehicle_name.sh duckiebot
    
    
    
 probar el joystick
 
     duckiebot@duckiebot:~/duckietown$ roslaunch duckietown joystick.launch veh:=duckiebot
     
     
     
 una vez hecho lo anterior probar el funcionamiento del robot en una linea recta.
notará
    
    
     
    

    
   
    
    
    

    
