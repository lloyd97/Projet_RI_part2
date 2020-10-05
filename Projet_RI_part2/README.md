# Projet RI partie 2
Ce repo contient les packages de la deuxième partie du projet.

### part_two_urdf
Ce package contient l'urdf pour un robot quadruped ainsi qu'un launch file correspondant.

### udm_project_moveitconfig
Ce package a été généré avec moveit assistant

### udm_project_control
Ce package contient les noeuds pour l'urdf, les services et les launch file nécéssaire pour déplacer le robot 
en ligne droite, à droite, à gauche et en arrière. 

## Installation
Pour installer ce noeud il faut le cloner dans le dossier src de votre catkin workspace (catkin_ws).

```
cd catkin_ws/src
git clone https://github.com/lloyd97/PROJET_ROS/Projet_RI_part2.git
catkin build
cd ..
source devel/setup.bash
```
## Execution 
### Visualiser la jambe
Pour visualiser, il faut executer le code suivant dans le terminal:

```
source devel/setup.bash
roslaunch part_two_urdf simulate.launch
```
### Controler la jambe à l'aide de la cinématique directe

Dans le premier terminal de votre catkin workspace:
```
source devel/setup.bash
roslaunch udm_project_moveitconfig demo.launch
```

Ouvrez un deuxieme terminal et executez le code suivant:
```
source devel/setup.bash
roslaunch udm_project_control control.launch
```

Ouvrez un troisieme terminal et executez le code suivant:
```
source devel/setup.bash
rosservice call /control "mouvement:
 data: 'front'"
```
NB: Vous pouvez choisir d'autres valeurs parmis les valeurs suivantes: 'front' , 'right' , 'left' , 'back'. 
