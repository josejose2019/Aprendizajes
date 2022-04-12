# Aprendizajes
Cuadernos para aprendizaje automático

PRACTICA 1
ML Niveles de estrés humano.
1. Importación de librerías y datos
1. Importación de librerías y datos
Cargamos los datos en un dataframe.
2. Análisis de los datos (EDA)
Nuestro dataset se compone de 2001 filas y 4 columnas
Lo que queremos predecir el nivel de estrés de alguna persona, por lo que nuestra columna objetivo será “Stress Level”, entonces veamos cuantas clases tiene.
Se observa que tiene tres clases que son 0, 1 y 2, entonces estamos hablando de un modelo de clasificación con tres valores.
Podemos seguir viendo más información, entonces veamos qué tipo de variables son las que tenemos disponibles:
El resultado muestra que todas las variables, en número de cuatro, son de tipo numérico, sin embargo, existe una pequeña diferencia tres son de tipo numérico con decimales y una es de tipo entero, también podemos observar que no tenemos valores nulos. Entonces podemos continuar y para obtener más detalles de las características del dataset con un método que nos muestre referencias a nivel estadísticos, entonces
El resultado no muestra un identificador “Id” de dato, que generalmente no aporta en nada y no hace falta incluir código para eliminar la columna de identificación.
2.1 Verificación de valores nulos.
En necesario realizar una verificación de valores nulos, para esto hacemos uso de:
El resultado muestra que existen valores nulos en: humedad 11 valores, temperatura 24 valores y en conteo de pasos 17 valores nulos.
Dado que los valores faltantes son en pequeña cantidad y la eliminación de alguna de las variables podría sesgar los resultados a falta de información, lo que haremos para resolver el problema de los valores nulos será el de completar con “ceros”.
Habiendo ejecutado los comandos para completar los datos nulos, verifiquemos los resultados:
2.3 Distribución y correlación de datos.
Ahora veamos cómo se distribuyen los datos entre las tres clases que queremos clasificar, entonces de acuerdo a la columna que queremos entender:
De manera gráfica observamos que:
Hay mayor número casos con niveles de estrés de tipo normal si consideramos que: 
•	El estrés bajo es “0”
•	El estrés normal es “1”
•	El estrés alto es “2”
A partir de estas conclusiones, podemos ir viendo las correlaciones de las variables, así podemos ver:
Con estos datos podemos entender que variables tienen alta correlación y cuáles de ellas no aportan mucho y podríamos prescindir de ella y eliminarlas(, recurramos a un mapa de calor para ver la correlación entre variables, esto es:
Así mismo para más claridad sobre la correlación podemos identificar cuáles son los atributos que tienen mayor correlación a partir de:
Podemos generar graficas de las correlaciones para analizar a las variables:
De acuerdo a la gráfica no hay mucha correlación entre las variables.
2.4 División de datos en Train, Validación y Test.
Se recomienda dividir el Data set, entonces es:
Nuestra muestra no es muy grande, entonces haremos una división manual de los datos en tres partes; en Test, Validación y Train, para que en el proceso de entrenamiento toquemos valores que no hayan sido vistos.
Ya tenemos dividido nuestro dataset en dos grupos, el que mandaremos a entrenar (Train) será el df_.
Hagamos la división clásica de train, test, Split. De acuerdo a nuestra tabla Stress Level se encuentra al final, entonces la sacaremos:
Ahora veamos la variable objetivo:
Ahora veamos la variable objetivo:
No siempre los valores que algunas variables tienen como numéricos son tales, para asegurar que el valor objetivo de estudio no sea categórico aplicamos el método get.dummies.
Para dar continuidad al algoritmo y aun no ingresar en la complejidad de colocar más de una clase a la variable objetivo, para este caso de variable objetivo ternaria lo que haremos es seleccionar una sola clase, de acuerdo al problema planteado de predecir el nivel de estrés, tomaremos la clase “nivel de estrés alto” = “2”, entonces:
Lo que haremos es dividir el Dataset tanto para entrenamiento como para validación.
Con el ultimo método el Dataset está listo para ingresar al modelo.
3. Preparamos el modelo.
El algoritmo que utilizare es el de vecinos cercanos el cual se ajusta también para problemas de clasificación.
Entonces importamos de la librería el algoritmo y creamos nuestro modelo: 
Ahora veamos el evaluar el modelo.
4.- Evaluación del modelo
De acuerdo a los valores que hubiera tomado las variables X_train y Y_train, aparentemente nos da un valor de precisión del 99% y este dato o resultado es muy interesante.
Para los valores de X_Train, y_Train; X_valid, y_valid también obtenemos un resultado muy atrayente.
Así también para el Test también se obtiene un resultado bastante atrayente.
Lo anterior implica que nuestro modelo está generalizando muy bien para los datos que se utiliza.
Finalmente hagamos algunas predicciones.
ESTO ES SOLO UN EJEMPLO !!!!   Gracias.
