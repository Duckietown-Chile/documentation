#Generar un mapa de Duckietown en ROS

## Crear CSV del mapa
Se debe crear el archivo en el _package_ `duckietown_description` como el siguiente:
ej: tiles_prueba.csv

    
    x, y, type     , rotation
    0, 0, turn     , 270
    0, 1, turn     , 180
    1, 0, straight , 0
    1, 1, straight , 0
    2, 0, turn     , 0
    2, 1, turn     , 90
    
#### Tipos de piso:
**straight**
**turn**
**empty**
**3way**
**4way**
**pond**
**halfpond**

## Crear CSV de los _tags_
Se debe crear un archivo en el _package_ `duckietown_description` como el siguiente:
ej: tags_prueba.csv
    
    id, x, y, pos, rotation
    7,  2, 2, 2,   180
    512,2, 1, 2,   180
    
#### Tipos de tags
Ver en `duckietown_description/urdf/meshes/tags`

####Posiciones de _tags_
Con respecto a la esquina inferior izquierda

| pos | x´     |  y´     |
|-----|--------|--------|
| 0   | 0.09   | 0.035  |
| 1   | 0.035  | 0.09   |
| 2   | -0.035 | 0.09   |
| 3   | -0.09  | 0.035  |
| 4   | -0.09  | -0.035 |
| 5   | -0.035 | -0.09  |
| 6   | 0.035  | -0.09  |
| 7   | 0.09   | -0.035 |

##Generar archivo _xacro_
Una vez que se tengan los archivos para el mapa y los tags, se debe lanzar el nodo _csv2xacro_ para generar el _xacro_ del mapa de la siguiente forma en la terminal:
    
    roslaunch duckietown_description csv2xacro_node.launch tile_map_csv:=/path/to/<tiles_mapname>.csv tag_map_csv:=/path/to/<tags_mapname>.csv map_name:=mapname
    
El archivo generado se guardara en `duckietown_description/urdf` con el nombre dado en `map_name` de la forma `<map_name>.urdf.xacro`.

##Lanzar el mapa en _rviz_ 
El mapa generado se puede lanzar en _rviz_ con el siguiente comando:
    
    roslaunch duckietown_description duckietown_description_node.launch map_name:=mapname veh:=duckiebot gui:=true
    
Se puede cargar el mapa sin lanzar _rviz_ con `gui:=false`

###To-Do:
* ver posiciones de los tags
* ver a que corresponden las coordenadas
* ver sistema de referencia