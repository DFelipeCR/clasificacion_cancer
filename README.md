# clasificacion_cancer
Despliegue de modelo en un servicio web para la predicción de tumores de cáncer de mama 

Para este despliegue primero se creo el modelo y se guardo un archivo llamado modelo_cancer.plk, este modelo recibe 30 valores que son las variables y son de la libreria scikit-learn:

radius (mean):
texture (mean):
perimeter (mean):
area (mean):
smoothness (mean):
compactness (mean):
concavity (mean):
concave points (mean):
symmetry (mean):
fractal dimension (mean):
radius (standard error):
texture (standard error):
perimeter (standard error):
area (standard error):
smoothness (standard error):
compactness (standard error):
concavity (standard error):
concave points (standard error):
symmetry (standard error):
fractal dimension (standard error):
radius (worst):
texture (worst):
perimeter (worst):
area (worst):
smoothness (worst):
compactness (worst):
concavity (worst):
concave points (worst):
symmetry (worst):
fractal dimension (worst):

Esto se puede ver en https://scikit-learn.org/stable/datasets/toy_dataset.html#breast-cancer-dataset

A continuacion se creo la API donde su endpoint es "/predict" y es del tipo post, este endpoint recibe un json del tipo:
{
  "features": [9.0, 12.0, 60.0, 250.0, 0.1, 0.08, 0.05, 0.02, 0.15, 0.05,
               0.4, 0.5, 2.0, 20.0, 0.005, 0.03, 0.02, 0.005, 0.02, 0.004,
               10.0, 15.0, 65.0, 300.0, 0.12, 0.09, 0.06, 0.03, 0.17, 0.06]
}

y genera una prediccion de 0 si es un tumor benigno o de un 1 si es un tumor maligno. esto se puede ver a continuación:
Tumor maligno (1):
![image](https://github.com/user-attachments/assets/085e2b8f-bef4-404a-aeaa-df35610ed505)
Tumor benigno (0):
![image](https://github.com/user-attachments/assets/f78ac063-9f6e-4126-8487-f729e1a3f4b9)

Luego de funcionar en un entorno local se creo un puente a través de ngrok:
![image](https://github.com/user-attachments/assets/487e5a24-4c2c-402a-ac20-28649e8148da)

y todas estas solicitudes de quedan guardadas en el archivo app.log:
![image](https://github.com/user-attachments/assets/a7dfcd63-dc4c-497d-8855-1761233a0621)

