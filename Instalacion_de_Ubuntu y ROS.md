# Instalación de Ubuntu

Descargar [Ubuntu Desktop 16.04.2](https://www.ubuntu.com/download/desktop)

Para instalarlo, asesórate con el equipo de Duckietown Chile

# Instalación de ROS
Seguiremos las instrucciones oficiales de la [documentacion](http://wiki.ros.org/kinetic/Installation/Ubuntu)

## 1.1 Configura los repositorios de Ubuntu
Aprieta la tecla Super (el logo de windows, ups) y escribe _Software y Actualizaciones_ (_Software and Updates_). Ahi debes tener seleccionadas las opciones *main*, *universe*, *restricted* y *multiverse*.

## 1.2 Abre una terminal
Busca la terminal o aprieta `Ctrl + ALt + T` en tu teclado. Desde ahora usaremos solo la terminal.

## 1.3 Actualiza tu archivo _sources.list_
El archivo `sources.list` es una lsita de direcciones desde las que Ubuntu accede a programas y paquetes. Vamos a incluir la dirección desde la que obtener ROS.
Copia y pega el siguiente comando en la terminal (o escríbelo)

    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
    
## 1.4 Configura tus claves para acceder al servidor donde se encuentra ROS
Copia y pega el siguiente comando en la terminal:

    sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116
    
## 1.5 Asegúrate de que tengas tu lista de paquetes actualizada
Esto asegura que cuando instales nuevo software, instales la última versión disponible. Para hacerlo, escribe:

    sudo apt-get update
    
## 1.6 Instalación de ROS
Enhorabuena! (léase con el acento que prefieras). Ha llegado el momento de instalar ROS e instalaremos la versión Kinetic completa en tu laptop.
El comando para instalarlo es:

    sudo apt-get install ros-kinetic-desktop-full
    
## 1.7 Inicializa rosdep
Rosdep permite instalar fácilmente las dependencias cuando necesites compilar algún programa de ROS (** TODO: buscar una descripción mas clara**)

    sudo rosdep init
    sudo rosdep update

## 1.8 Configura tu entorno para trabajar con ROS
ROS necesita cargar variables de entorno para reconocer en qué carpetas se almacena cada una de sus partes. Para eso, hay un archivo que debe cargarse cada vez que iniciamos sesión en nuestro computador. Esto lo haremos escribiendo el archivo `.bashrc` que se encuentra oculto en nuestra carpeta `home`.

    echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc

Luego, debemos indicar a la consola que estamos usando actualmente que hicimos este cambio. Para ello usamos el comando `source`:
     
     source ~/.bashrc
    
## 1.9 Obtén rosinstall
**TODO: Escribir una buena explicación de rosinstall (o decir que no es necesario y punto)**

    sudo apt-get install python-rosinstall
    

** Estamos listos! **
