# Seguimiento de objeto con Python
Este repositorio contiene un nodo de ROS que ejecuta el algoritmo de seguimiento de objeto realizado con Python. Asimismo, está el archivo que permite visualizar los datos que se están generando.

## Hardware
se requiere pc con ros
una camara

## Requerimientos de Software
Para el funcionamiento del código se requiere de:

 - ROS Melodic
 - Python 3
 - Librerias de Python
	  -   `sudo apt-get install python-pip`
	  - `pip install --upgrade imutils`
	  - `sudo apt-get install python3-opencv`
	  - `sudo apt-get install python-argparse`
	  - `pip install numpy`


## ¿Cómo instalar?
Para clonar el repositorio, se digita en consola: 

    git clone https://github.com/sarasarixsara/objectTracker.git

En la terminal, ingrese a la ubicación del archivo descargado. La carpeta contiene dos archivos: el *prueba2.py* detecta el objeto y publica información tipo Twist, sobre una coordenada angular y otra lineal. El *listener.py* imprime en consola los datos generados por el otro archivo Python. Con esta información se puede controlar el movimiento de los motores.


Primero se ejecuta el que publica los datos:

    python3 tracker.py
   Esto inicia la cámara en una nueva ventana, debe detectar los objetos del color declarado en el código (verde lima).
   
![Captura de pantalla de 2022-11-24 21-16-40](https://user-images.githubusercontent.com/72929394/203887099-6bee779a-5d3d-48c1-a5b7-3d31d62158ab.png)

   En una nueva términal, ejecute el listener
   

    python listener.py

Esto le permite ver 3 datos lineales y 3 datos angulares. Según el movimiento del objeto, solo se verán modificados la posición lineal en X, que toma valor de 1 o -1; y la posición angular en Z que toma valores de 1,0.5,-0.5 o -1, dependiendo de qué tan fuerte se desee el giro. Es decir, solo se modifica el primer y último dato de la lista. 

![Captura de pantalla de 2022-11-24 21-16-40](https://user-images.githubusercontent.com/72929394/203887099-6bee779a-5d3d-48c1-a5b7-3d31d62158ab.png)




## Autores

Sara Valentina Cuy

