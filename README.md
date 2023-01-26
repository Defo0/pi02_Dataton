## pi02_Dataton

# Random Forest

En mi proyecto, utilicé Random Forest para predecir si un alquiler sería **"caro"** *(más de 999 dólares)* o **"barato"** *(menos que 999 dólares)* , según los datos que me fueron brindados.
El dataset que utilicé contenía aproximadamente 400000 filas y 22 columnas, tanto numéricas como categóricas. Utilicé la funcion get_dummies de Pandas para tratar las variables categóricas y transformarlas en 1 y 0, teniendo como resultado como 400 y pico columnas, me asusté un poco pense que mi compu iba a reventar pero se la aguantó como una campeona.

La razón por la que elegí Random Forest es debido a varias ventajas que tiene sobre otros algoritmos de aprendizaje automático. En primer lugar, es un algoritmo altamente preciso, ya que combina varios árboles de decisión y reduce el sesgo. En segundo lugar, es capaz de manejar un gran número de variables y es robusto a la presencia de datos faltantes. Además, es un algoritmo fácil de entender, explicar y aplicar.

#Selección de parámetros
Para seleccionar los parámetros optimos utilicé la técnica de Grid Search para buscar los mejores parámetros del modelo. Grid Search es una técnica de optimización de hiperparámetros que consiste en probar varios valores de los parámetros para encontrar el mejor conjunto de parámetros para el modelo. Esto me permitió obtener un modelo más preciso al ajustar los parámetros de Random Forest a las características específicas del dataset.


# EDA y Transformaciones

Utilicé la biblioteca Pandas Profiling para realizar un análisis exploratorio de los datos (EDA, por sus siglas en inglés) antes de comenzar a construir el modelo. Pandas Profiling es una herramienta útil para obtener una visión general de las características del dataset, como la distribución de las variables, las relaciones entre las variables, y las posibles outliers. Esto me permitió tener una mejor comprensión de los datos y tomar decisiones informadas sobre cómo preparar los datos para el modelo. si bien no es la mejor herramienta o la mas completa, permite realizar el análisis sin romperse mucho la cabeza y lo deja presentado muy bonito.


# Resultados:

Pude obtener muy buenos resultados frente a datos conocidos y desconocidos, con los valores por defecto que nos da el propio código logré una acuracy de 0.929 y un recall de 0.931

## Métrica a utilizar
​
Como método de evaluación del desempeño, dependerá del modelo que usted decida implementar.
​
1. Para el modelo de aprendizaje supervisado, se utilizará la métrica `Accuracy` para las propiedades de precio bajo (low) a partir de la matriz de confusión (Confusion Matrix).

$$ Accuracy=\frac{TP+TN}{P+N}$$

siendo $TP$ los verdaderos positivos (las propiedades de precio 'low' que realmente lo son), $TN$ verdaderos negativos (las propiedades que realmente NO son de precio 'low') y $P+N$ población total.

Como métrica adicional para verificar el desempeño de su modelo, también se utilizará la métrica de precisión (Recall) para las propiedades baratas.

$$ Recall=\frac{TP}{TP+FN}$$

​
Donde $TP$ son los verdaderos positivos (las propiedades de precio 'low' que realmente lo son) y $FN$ los falsos negativos (las propiedades de precio 'low' que fueron marcadas incorrectamente).


#selección de valores

id: Fuera
url: fuera
region: convertido en datos numéricos, cada valor unico representa una columna
region_url: fuera
price: se utilizó para determinar si era low o not low
type: se pasó a dato numérico, cada valor representa una columna
sqfeet: Metros cuadrados de la propiedad.
beds: Cantidad de dormitorios.
baths: Cantidad de baños.
cats_allowed: Si se permiten gatos en la propiedad toma el valor 1, 0 para caso contrario.
dogs_allowed: Si se permiten perros en la propiedad toma el valor 1, 0 para caso contrario.
smoking_allowed: Si se permite fumar en la propiedad toma el valor 1, 0 para caso contrario.
wheelchair_access: Si la propiedad posee acceso para sillas de ruedas toma el valor 1, 0 para caso contrario.
electric_vehicle_charge: Si la propiedad posee cargador para vehículos eléctricos toma el valor 1, 0 para caso contrario.
comes_furnished: Si la propiedad viene amueblada toma el valor 1, 0 para caso contrario.
laundry_options: tenia muchos valores faltantes asi que la saqué
parking_options: tenia muchos valores faltantes asi que la saque
image_url: fuera
description: si bien se podia hacer un analisis de lenguaje, tambien, fuera. 
lat: teniendo la zona geografica el punto exacto no me parecia necesario
long: idem anterior
state: Código del estado al que pertenece la propiedad. - convertido a dato numérico con get_dummies
.

## conclusión
En conclusión, creo que pude lograr un muy buen resultado, si tuviera mas tiempo me ponia a entrenar mas modelos, hubo procesos que llevaron mas de 10 horas, tuve un par de errores que tuve que solucionar, empecé encarando mal el problema... me di cuenta demasiado tarde. pero pude lograr el objetivo planteado en el tiempo que se suponia que debia realizarlo asi que estoy muy contento, y quede bastante arriba en la tabla de resultados asi que más contento todavia. 
