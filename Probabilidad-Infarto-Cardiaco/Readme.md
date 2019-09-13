# Resumen

Acontinuación se realizará una clasificación binaria para predecir en base a las variables si un paciente con un determinado número de medidas médicas es susceptible de tener enfermedad de corazón o no.

La clasificación se considerará satisfactoria si alcanza una exactitud de 0.9.

Para ello se realizará un análisis exploratorio de las variables evaluando que variables aportan a la predicción, posteriormente se dividirán los datos en conjunto de entrenamiento (80%) y conjunto de validación (20%).

Con esto se realizarán diversos algoritmos de clasificación binaria mediante ternsorflow, donde el entrenamiento se realizará utilizando validación cruzada aleatoria (en cada algoritmo hay una descripción del procedimiento utilizado).

Finalmente la comparación de los algoritmos se relizará con la exactitud de cada algoritmo sobre el conjunto de validación.

# Antecedentes de los datos

Esta base de datos contiene 76 atributos, pero todos los experimentos publicados se refieren al uso de un subconjunto de 14 de ellos. En particular, la base de datos de Cleveland es la única que los investigadores de ML han utilizado hasta la fecha. El campo "objetivo" se refiere a la presencia de enfermedad cardíaca en el paciente. Tiene un valor entero de 0 (sin presencia) a 4.

Información de los atributos:
1. **(age)**     : edad
2. **(sex)**     : sexo
3. **(cp)**      : tipo de dolor en el pecho (4 valores)
4. **(trestbps)**: presión arterial en reposo
5. **(chol)**    : colesterol sérico en mg/dl
6. **(fbs)**     : azúcar en sangre (en ayunas) > 120 mg/dl
7. **(restecg)** : Resultados electrocardiográficos en reposo (valores 0,1,2)
8. **(thalach)** : frecuencia cardíaca máxima alcanzada
9. **(exang)**   : angina inducida por ejercicio
10. **(oldpeak)** : depresión del ST inducida por el ejercicio relativo al descanso
11. **(slope)**   : pendiente del segmento ST de ejercicio máximo
12. **(ca)**      : número de vasos principales (0-3) coloreados por flourosopía
13. **(thal)**    : 3 = normal; 6 = defecto fijo; 7 = defecto reversible

Fuente: https://www.kaggle.com/ronitf/heart-disease-uci
