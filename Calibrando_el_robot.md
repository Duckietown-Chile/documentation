# Calibración de la cámara
## Calibración intrínseca





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
    
    
     
    

    
   
    
    
    

    
