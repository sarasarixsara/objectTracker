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

Primero se inicia el nodo master de ROS


    roscore 

en una nueva terminal se ejecuta el que publica los datos:

    python3 tracker.py
   Esto inicia la cámara en una nueva ventana, debe detectar los objetos del color declarado en el código (verde lima).
   
![Captura de pantalla de 2022-11-25 03-14-14](https://user-images.githubusercontent.com/72929394/204011864-8cf93820-d99c-4104-a99f-06a454b9fa47.png)

   En otra nueva términal, ejecute el listener
   

    python listener.py

Esto le permite ver 3 datos lineales y 3 datos angulares. Según el movimiento del objeto, solo se verán modificados la posición lineal en X, que toma valor de 1 o -1; y la posición angular en Z que toma valores de 1,0.5,-0.5 o -1, dependiendo de qué tan fuerte se desee el giro. Es decir, solo se modifica el primer y último dato de la lista. 

![Captura de pantalla de 2022-11-24 21-16-40](https://user-images.githubusercontent.com/72929394/203887099-6bee779a-5d3d-48c1-a5b7-3d31d62158ab.png)

Para verificar el correcto funcionamiento se debe verificar que se obtienen las siguientes salidas:

Cuando el objeto está detenido o no se detecta un objeto, no se activan los motores y los valores son:

![Captura de pantalla de 2022-11-25 03-20-49](https://user-images.githubusercontent.com/72929394/204017646-1ee35e49-1fa0-4112-b6bd-28b15c44052a.png)

Cuando el objeto esté alejado,los motores deben avanzar por lo que los valores son:

![Captura de pantalla de 2022-11-25 03-17-30](https://user-images.githubusercontent.com/72929394/204017872-e9971ef2-9c00-4efc-9bca-a2dafe5d7530.png)

Cuando el objeto se mueva hacia la derecha, el robot debe realizar un giro a la izquierda, los valores son:

![Captura de pantalla de 2022-11-25 03-17-00](https://user-images.githubusercontent.com/72929394/204018032-6d9ceca6-0656-4df0-a7f3-49cf581ef21b.png)![Captura de pantalla de 2022-11-25 03-16-48](https://user-images.githubusercontent.com/72929394/204018234-eb01435d-d46c-4ce3-ad39-3ef5af6e8c8f.png)


Cuando el objeto se mueva hacia la izquierda, el robot debe realizar un giro a la derecha, los valores son:

![Captura de pantalla de 2022-11-25 03-16-55](https://user-images.githubusercontent.com/72929394/204018126-420422e3-78f2-45a6-87ea-63d6226ffefb.png)![Captura de pantalla de 2022-11-25 03-16-36](https://user-images.githubusercontent.com/72929394/204018281-b76c8a22-fb53-4001-902a-0256c48d5c72.png)


Para finalizar el programa del tracker, presione la letra 'q' en el frame de la cámara y digite Ctrl+C en la terminal donde se ejecutó el tracker. Para finalizar el listener presione Ctrl+C
## Autores

Sara Valentina Cuy

