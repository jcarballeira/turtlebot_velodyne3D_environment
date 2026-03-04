# Repositorio original Multi-turtlebot3-Gazebo-ROS2
https://github.com/Taeyoung96/Multi-turtlebot3-Gazebo-ROS2

# Requisitos
Tener instalado Gazebo

## Build 
Crear carpeta turtlebot_ws y clonar repositorio. Renombrar carpeta descargada como src. Desde turtlebot_ws compilar:

```
colcon build --symlink-install
```
Cargar directamente el setup al arrancar terminal para Gazebo y este paquete. Añadir al path de búsqueda de modelos de Gazebo los directorios.
Abrir archivo .bashrc:
```
sudo gedit .bashrc
```
Copiar al final:
```
source ~/nombre_workspace/install/setup.bash
source /usr/share/gazebo/setup.bash
export GAZEBO_MODEL_PATH=/usr/share/gazebo-11/models:\
$HOME/nombre_workspace/install/turtlebot3_gazebo/share/turtlebot3_gazebo/models:\
$HOME/nombre_workspace/install/velodyne_description/share
```
Se recomienda también copiar:
```
source /opt/ros/humble/setup.bash
```
```
source install/setup.bash
```

### Multi-turtlebot3  

```
ros2 launch turtlebot3_gazebo multi_turtlebot3_world.launch.py
```

### Turtlebot3 with Velodyne VLP-16
```
ros2 launch turtlebot3_gazebo turtlebot3_velodyne_burger.launch.py
```
### Mutli-turtlebot3 with Velodyne VLP-16
```
ros2 launch turtlebot3_gazebo multi_turtlebot3_velodyne_world.launch.py
```
### Turtlebot with Velodyne 3D casa vacía (Para SLAM)
```
ros2 launch turtlebot3_gazebo turtlebot3_velodyne_burger_houseSLAM.launch.py
```
### Turtlebot with Velodyne 3D casa obstaculos (Para Localización)
```
ros2 launch turtlebot3_gazebo turtlebot3_velodyne_burger_house.launch.py
```
### For keyboard teleop  
Cargar modelo del robot (se puede poner también en el .bashrc)
```
export TURTLEBOT3_MODEL=burger
```
```
ros2 run turtlebot3_teleop teleop_keyboard 
```

### Check TF   

```
ros2 run tf2_tools view_frames
```

