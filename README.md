# Seguimiento de objeto con Python
Este repositorio contiene un nodo de ROS que ejecuta el algoritmo de seguimiento de objeto realizado con Python. Asimismo, está el archivo que permite visualizar los datos que se están generando.

![Captura de pantalla de 2022-11-25 03-12-05](https://user-images.githubusercontent.com/72929394/204010901-6b9a85f7-5512-4a02-8238-387584b2fb81.png)


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

Primero se inicia el noso master de ROS


    roscore 

en una nueva terminal se ejecuta el que publica los datos:

    python3 tracker.py
   Esto inicia la cámara en una nueva ventana, debe detectar los objetos del color declarado en el código (verde lima).
   
![Captura de pantalla de 2022-11-24 21-19-26](https://user-images.githubusercontent.com/72929394/203887341-523efa0d-56cc-4d97-b4c0-a12522bf6de4.png)

   En otra nueva términal, ejecute el listener
   

    python listener.py

Esto le permite ver 3 datos lineales y 3 datos angulares. Según el movimiento del objeto, solo se verán modificados la posición lineal en X, que toma valor de 1 o -1; y la posición angular en Z que toma valores de 1,0.5,-0.5 o -1, dependiendo de qué tan fuerte se desee el giro. Es decir, solo se modifica el primer y último dato de la lista. 

![Captura de pantalla de 2022-11-24 21-16-40](https://user-images.githubusercontent.com/72929394/203887099-6bee779a-5d3d-48c1-a5b7-3d31d62158ab.png)



Para finalizar el programa del tracker, presione la letra 'q' en el frame de la cámara y digite Ctrl+C en la terminal donde se ejecutó el tracker. Para finalizar el listener presione Ctrl+C
## Autores

Sara Valentina Cuy

