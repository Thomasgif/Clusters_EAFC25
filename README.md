# Clusters_EAFC25
El proyecto se basa en un aprendizaje no supervisado de la base de datos del juego FC25(FIFA), para poder clasificar a sus jugadores en 4 clusters, usando el algoritmo K-means con 4 variaciones del mismo aplicando 3 tipos diferentes de distancias (Euclidiana, Mahalanobis, L1). Además de lo anterior se logra hacer una visualización mediante un PCA.

La base de datos paso por un EDA, para un buen procesamiento y tener concordancia de cuales e utilizaran que sean de provecho para el algoritmo, en este caso se utilizaran 45 variables para cada jugador, con una escala que ira de 0 a 100 en todas para que cada una tenga un peso similar en el procesamiento.

Para el caso de algunas variables que están clasificadas como string, como lo han sido el pie preferido se han transformado en una variable binaria, además en las categorías que había datos NaN (datos nulos) se han imputados valores en 0, como en categoría de arqueros donde estos no afectan la estadística.

Para la primera implementación de algoritmo se ha utilizado la librería de sklearns, la cual ya trae integrada Kmeans para su uso rápido, como además trae el Kmeans++ que es una forma mejorada de este algoritmo, también se ha utilizado la técnica del codo para tener en cuenta cual sería la cantidad ideal de clusters para la correcta clasificación de los datos.

En el Kmeans desarrollado a mano se han seguido los pasos del algoritmo que consta de asignar cuantos clusters serán los necesario (se ha utilizado el método del codo), se ubican una cantidad de centroides iguales a la cantidad de los clusters, después se va asignando a cuál clúster se adecua cada dato, y se procede a recalcular un centroide para seguir buscando datos, el parámetro de finalización va a ser la tolerancia que se indique que va a ser la diferencia de posición entre el clúster inicializado a la distancia que se encuentra de su antecesor. 

Después de la función general se harán varianzas entre las 3 distancias para encontrar nuevas distribuciones de la clusterización, todo esto pasara por un PCA para quedarnos con los componentes principales, que nos proporcionarán una varianza de solo un 80% de cada dato, para su próxima visualización en tablas 2D y 3D también se tendrán los centroides en términos del PCA.
