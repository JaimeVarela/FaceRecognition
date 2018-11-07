# Reconocimiento Facial

Esta aplicación se ha desarrollado empleando las librerías de OpenCV. Su objetivo es reconocer el rostro de la persona que aparece en escena tanto en un vídeo como por medio de una cámara. Consta de dos fases: entrenamiento y predicción.

1. Fase de entrenamiento: se crea una base de datos que contenga la información sobre los rasgos faciales de las personas de la galería de imágenes que proporcionemos al programa. Se recomienda utilizar 400 fotografías de 40 personas, 10 fotografías por persona. Para agilizar la obtención de las fotografías pueden emplearse las facilitadas por la página AT&T Facedatabase, las cuales están pensadas para programas de reconocimiento facial. Es recomendable emplear una serie de fotografías de las caras con diferentes gestos faciales, con el objetivo de obtener una información más robusta en la fase de entrenamiento. Estas fotografías han de ser del mismo tamaño, en escala de grises y con el mismo formato.

La clase FisherFaces facilitada por OpenCV genera la base de datos. Consiste en fijar un rango de valores a cada persona y separándolo de los rangos de valores de otras personas, por lo que tener más personas a analizar ayuda a distinguir mejor entre dos personas en la fase de predicción. Para leer las fotografías el programa encargado de esta fase emplea el archivo CSV.txt, donde se encuentra la ruta de cada fotografía en la que está guardada, en vez de tener que introducir manualmente en el programa la ruta de cada fotografía. Una vez creada la base de datos el programa la guarda como un archivo XML, llamado “datos.xml”.

![entrenamiento](https://user-images.githubusercontent.com/44776831/48133965-c9011d80-e298-11e8-9a6c-c5d3c5d6cb26.png)

2. Fase de predicción: una vez producida la base de datos, se procede a realizar la predicción en un vídeo o lo que capture una cámara, de la siguiente forma:

2.1. Captura un frame, por lo que el módulo debería conectarse de forma que se encuentre en mitad de la transmisión de un flujo de vídeo.

2.2. Carga el archivo “haarcascade_frontalface_alt.xml” para detectar la cara en el frame.

2.3. Carga el archivo “datos.xml” para predecir quién es la persona que aparece en el frame.

![prediccion](https://user-images.githubusercontent.com/44776831/48134157-65c3bb00-e299-11e8-9b6a-6a01c4d9bf4b.png)

Como resultado aparecerá el rostro de la persona encuadrada junto al nombre (o número) de la persona que el programa considera que corresponde:

![image](https://user-images.githubusercontent.com/44776831/48134257-b9ce9f80-e299-11e8-8b3e-31f06ef32410.png)
