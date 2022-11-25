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


## files

You can export the current file by clicking **Export to disk** in the menu. You can choose to export the file as plain Markdown, as HTML using a Handlebars template or as a PDF.


# 
