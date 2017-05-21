# Instrucciones para habilitar lanzamiento remoto de roslaunchs
Referencia: https://docs.google.com/document/d/1HP5ao3LwgQ1EkdRb3ksiMg8zdrpJXjSIH_XG2RFHyes/edit#

## En los laptops
### Conectarse por ssh al duckiebot

    laptop $ ssh ubuntu@duckiebot.local 
    
### Crear el directorio ssh (si no existe)

    laptop $ mkdir -p ~/.ssh

### Instalar la clave ssh de duckietown

    laptop $ wget -O ~/.ssh/duckietown_key1 "https://www.dropbox.com/s/q23qptu01u7ur3y/duckietown_key1?dl=1"

### Cambiar permisos de la clave

    laptop $ chmod 600 ~/.ssh/duckietown_key1

### Regenerar la clave pblica

    laptop $ ssh-keygen -f ~/.ssh/duckietown_key1 -y > ~/.ssh/duckietown_key1.pub

### Editar el archivo config de SSH

    laptop $ nano ~/.ssh/config
    
Dentro del archivo, con la interfaz de `nano`, escribir
    
    Host duckiebot
        Hostname duckiebot.local
	      User ubuntu
	      IdentityFile ~/.ssh/duckietown_key1
        HostKeyAlgorithms ssh-rsa

### Ahora se deberia poder acceder al robot con el comando

    laptop $ ssh duckiebot


## En los duckiebots
### Crear el directorio SSH (si no existe) y habilitar permisos

    mkdir .ssh
    chmod g-rwx,o-rwx .ssh
    
### Descargar las claves

    wget -O .ssh/authorized_keys https://www.dropbox.com/s/pxyou3qy1p8m4d0/duckietown_key1.pub?dl=1


