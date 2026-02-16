# MUSI - Preguntas tipo test resueltas (v2)

Formato: 4 opciones (A/B/C/D), respuesta correcta y explicacion breve.
Cobertura: lecture1 a lecture6c. Nivel: examen (mezcla con trampas).

---

## 1) Fundamentos y pipeline

1. En la definicion de Mitchell, el aprendizaje se formaliza como:
   - A) <P, T, E>
   - B) <T, E, P>
   - C) <E, P, T>
   - D) <T, P, E>

   **Respuesta:** B

   **Por que:** La triada es tarea, experiencia y medida de rendimiento.

2. Sobre generalizacion, es correcto afirmar que:
   - A) mejor training accuracy siempre implica mejor test accuracy
   - B) un modelo mas complejo siempre generaliza mejor
   - C) un modelo sencillo puede generalizar mejor que uno sobreajustado
   - D) el sobreajuste no existe con muchos datos

   **Respuesta:** C

3. El objetivo del feature engineering es:
   - A) maximizar dimensionalidad siempre
   - B) eliminar cualquier relacion con la salida
   - C) mejorar separacion entre clases y reducir ruido
   - D) evitar el preprocesado

   **Respuesta:** C

4. En clasificacion Bayesiana MAP, se decide la clase con mayor:
   - A) p(x|wi)
   - B) P(wi|x)
   - C) P(wi)
   - D) varianza

   **Respuesta:** B

5. Con priori iguales y costes iguales, la regla MAP se reduce a:
   - A) minimizar ||w||
   - B) maximizar P(wi)
   - C) maximizar p(x|wi)
   - D) minimizar el error total

   **Respuesta:** C

---

## 2) Analisis y preprocesado de datos

6. En preprocesado, el orden correcto para evitar leakage es:
   - A) fit scaler en todo X y luego split
   - B) split y luego fit scaler en train, transform test
   - C) fit scaler en test y luego transform train
   - D) no usar escalado

   **Respuesta:** B

7. La normalizacion min-max transforma x a:
   - A) (x - mu) / sigma
   - B) (x - min) / (max - min)
   - C) x / max
   - D) log(x)

   **Respuesta:** B

8. Un z-score se interpreta como:
   - A) porcentaje de varianza explicada
   - B) distancia en unidades de desviacion tipica
   - C) probabilidad posterior
   - D) media ponderada

   **Respuesta:** B

9. Para variables categoricas nominales, lo mas seguro es:
   - A) LabelEncoder siempre
   - B) OneHotEncoder para evitar orden artificial
   - C) mapear a float continuo
   - D) eliminar la columna

   **Respuesta:** B

10. La deteccion de outliers con IQR usa como umbral tipico:
   - A) Q3 + 0.5 * IQR
   - B) Q3 + 1.5 * IQR
   - C) Q3 + 3.0 * IQR
   - D) Q2 + 1.5 * IQR

   **Respuesta:** B

11. En exploratory data analysis, SPLOM y parallel coordinates sirven para:
   - A) entrenar modelos
   - B) visualizar relaciones multivariadas
   - C) calcular la ROC
   - D) reducir dimensionalidad automaticamente

   **Respuesta:** B

---

## 3) Bayes y clasificadores lineales

12. El clasificador Bayesiano minimiza:
   - A) el numero de parametros
   - B) el error de clasificacion esperado
   - C) el error de entrenamiento
   - D) la varianza del modelo

   **Respuesta:** B

13. Con clases gaussianas de igual covarianza, la frontera es:
   - A) cuadratica
   - B) lineal
   - C) siempre no lineal
   - D) circular en cualquier dimension

   **Respuesta:** B

14. Si las covarianzas son diferentes, la frontera tiende a ser:
   - A) lineal
   - B) cuadratica
   - C) constante
   - D) aleatoria

   **Respuesta:** B

15. Con misma covarianza y priori iguales, la regla equivale a:
   - A) distancia euclidea a la media
   - B) distancia Mahalanobis a la media
   - C) distancia Manhattan
   - D) distancia coseno

   **Respuesta:** A

16. La distancia de Mahalanobis es preferible cuando:
   - A) las features no estan correlacionadas
   - B) hay correlacion y escalas distintas
   - C) no hay covarianza
   - D) hay solo una feature

   **Respuesta:** B

---

## 4) Regresion

17. OLS minimiza:
   - A) error absoluto medio
   - B) suma de errores cuadrados
   - C) entropia cruzada
   - D) AUC

   **Respuesta:** B

18. Un R2 cercano a 1 indica:
   - A) bajo ajuste
   - B) varianza explicada alta
   - C) alta varianza del modelo
   - D) clasificacion perfecta

   **Respuesta:** B

19. En regresion multiple, la solucion cerrada usa:
   - A) eigenvectors de y
   - B) pseudoinversa de X
   - C) kernel trick
   - D) kNN

   **Respuesta:** B

20. La regresion polinomial sigue siendo lineal en:
   - A) x
   - B) y
   - C) los parametros
   - D) el ruido

   **Respuesta:** C

21. En gradiente descendente, un learning rate muy alto suele:
   - A) acelerar convergencia sin riesgos
   - B) divergir u oscilar
   - C) dar el minimo global siempre
   - D) eliminar overfitting

   **Respuesta:** B

22. En regresion logistica, la funcion de perdida adecuada es:
   - A) MSE
   - B) entropia cruzada binaria
   - C) hinge loss
   - D) log loss multiclass

   **Respuesta:** B

---

## 5) Arboles y ensembles

23. La impureza Gini de un nodo puro es:
   - A) 1
   - B) 0.5
   - C) 0
   - D) depende de N

   **Respuesta:** C

24. El split optimo en un arbol busca:
   - A) maximizar impureza
   - B) minimizar profundidad
   - C) maximizar reduccion de impureza
   - D) maximizar numero de hojas

   **Respuesta:** C

25. El overfitting en arboles se controla con:
   - A) aumentar profundidad
   - B) reducir min_samples_leaf o max_depth
   - C) aumentar min_samples_leaf o limitar profundidad
   - D) eliminar regularizacion

   **Respuesta:** C

26. En bagging, el efecto principal es:
   - A) reducir sesgo
   - B) reducir varianza
   - C) aumentar sesgo
   - D) aumentar error

   **Respuesta:** B

27. En boosting, los modelos se entrenan:
   - A) en paralelo
   - B) secuencialmente corrigiendo errores
   - C) solo con features aleatorias
   - D) sin pesos

   **Respuesta:** B

---

## 6) Instance-based learning

28. Un metodo instance-based:
   - A) crea un modelo global compacto
   - B) necesita la base de ejemplos para predecir
   - C) no usa distancia
   - D) no puede generalizar

   **Respuesta:** B

29. Reducir instancias en IBL sirve para:
   - A) aumentar coste de memoria
   - B) reducir sobreajuste y tiempo de busqueda
   - C) empeorar generalizacion
   - D) eliminar necesidad de datos

   **Respuesta:** B

---

## 7) SVM

30. El margen geometrico total en SVM hard-margin es:
   - A) ||w||
   - B) 1/||w||
   - C) 2/||w||
   - D) 2||w||

   **Respuesta:** C

31. Los support vectors son:
   - A) todos los puntos
   - B) los que definen el margen
   - C) los outliers obligatorios
   - D) los mas lejanos al hiperplano

   **Respuesta:** B

32. En soft-margin, aumentar C suele:
   - A) permitir mas errores
   - B) penalizar mas errores
   - C) ampliar margen siempre
   - D) eliminar los SV

   **Respuesta:** B

33. En SVM no lineal, el kernel permite:
   - A) evitar la optimizacion
   - B) trabajar en un espacio de mayor dimension implcito
   - C) eliminar regularizacion
   - D) hacer el modelo lineal siempre

   **Respuesta:** B

34. En multiclase, OVO implica:
   - A) M clasificadores
   - B) M(M-1)/2 clasificadores
   - C) un solo clasificador
   - D) 2M clasificadores

   **Respuesta:** B

---

## 8) kNN

35. Elegir k muy pequeno en kNN produce:
   - A) sesgo alto
   - B) varianza alta
   - C) frontera muy suave
   - D) menor sensibilidad al ruido

   **Respuesta:** B

36. Escalar features en kNN es importante porque:
   - A) mejora la teoria de Bayes
   - B) evita que una feature domine la distancia
   - C) reduce el numero de clases
   - D) hace al modelo lineal

   **Respuesta:** B

37. Una forma de romper empates en kNN es:
   - A) elegir la clase mas lejana
   - B) voto ponderado por distancia
   - C) ignorar la muestra
   - D) fijar k=2

   **Respuesta:** B

38. El coste de inferencia de kNN es alto porque:
   - A) requiere resolver un QP
   - B) calcula distancias a muchos puntos
   - C) necesita backprop
   - D) recalcula los centroides

   **Respuesta:** B

---

## 9) Clustering - conceptos y jerarquico

39. Clustering busca:
   - A) minimizar error supervisado
   - B) descubrir estructura sin etiquetas
   - C) predecir y
   - D) ajustar hiperparametros

   **Respuesta:** B

40. Single-link tiende a:
   - A) clusters compactos
   - B) efecto cadena
   - C) minimizar varianza interna
   - D) clusters esfericos

   **Respuesta:** B

41. Complete-link tiende a:
   - A) clusters compactos
   - B) efecto cadena
   - C) maximizar varianza
   - D) clusters alargados

   **Respuesta:** A

42. Ward elige la fusion que:
   - A) minimiza aumento de varianza intra
   - B) maximiza distancia minima
   - C) minimiza distancia maxima
   - D) maximiza silhouette

   **Respuesta:** A

---

## 10) k-means y variantes

43. K-means minimiza:
   - A) SSE intra-cluster
   - B) AUC
   - C) precision
   - D) entropia

   **Respuesta:** A

44. K-means es sensible a:
   - A) inicializacion y outliers
   - B) solo al numero de features
   - C) solo al escalado de etiquetas
   - D) no es sensible a nada

   **Respuesta:** A

45. K-means++ se usa para:
   - A) elegir k
   - B) inicializar centroides mejor
   - C) calcular silhouette
   - D) eliminar outliers

   **Respuesta:** B

46. K-medoids difiere porque:
   - A) usa centroides no reales
   - B) usa puntos reales como representantes
   - C) no necesita distancia
   - D) es igual a k-means

   **Respuesta:** B

47. Fuzzy c-means permite:
   - A) pertenencia binaria
   - B) pertenencia suave a varios clusters
   - C) solo 2 clusters
   - D) no usa distancia

   **Respuesta:** B

---

## 11) Validez de clustering

48. El metodo del codo selecciona k donde:
   - A) WCSS sube
   - B) la mejora adicional se vuelve pequena
   - C) silhouette es negativa
   - D) DB index es maximo

   **Respuesta:** B

49. Silhouette cerca de 1 indica:
   - A) mala asignacion
   - B) buena cohesion y separacion
   - C) clusters solapados
   - D) azar

   **Respuesta:** B

50. Davies-Bouldin se optimiza:
   - A) maximizando
   - B) minimizando
   - C) igualando a 1
   - D) haciendo 0 la varianza

   **Respuesta:** B

---

## 12) Evaluacion y tuning

51. En datos desbalanceados, accuracy puede ser:
   - A) siempre fiable
   - B) enganosa
   - C) igual a F1
   - D) equivalente a AUC

   **Respuesta:** B

52. En ROC, el eje X es:
   - A) TPR
   - B) Precision
   - C) FPR
   - D) Accuracy

   **Respuesta:** C

53. AUC cercana a 0.5 implica:
   - A) clasificador casi aleatorio
   - B) clasificador perfecto
   - C) overfitting seguro
   - D) error cero

   **Respuesta:** A

54. En nested CV, el bucle interno se usa para:
   - A) medir performance final
   - B) tuning de hiperparametros
   - C) aumentar dataset
   - D) crear features

   **Respuesta:** B

55. GridSearchCV elige hiperparametros segun:
   - A) score medio de validacion
   - B) score de entrenamiento
   - C) tiempo de ejecucion
   - D) numero de parametros

   **Respuesta:** A

56. Un learning curve con baja accuracy en train y val sugiere:
   - A) alta varianza
   - B) alto sesgo (underfitting)
   - C) leakage
   - D) problema resuelto

   **Respuesta:** B

57. Un learning curve con gran gap train>>val sugiere:
   - A) alto sesgo
   - B) alta varianza (overfitting)
   - C) buen ajuste
   - D) error irreducible

   **Respuesta:** B

58. Para evitar leakage en CV, lo correcto es:
   - A) escalar antes de CV
   - B) pipeline dentro de CV
   - C) usar test para tuning
   - D) mezclar train y test

   **Respuesta:** B

59. En multiclass, el macro-average:
   - A) pesa todas las clases por igual
   - B) pesa por numero de muestras
   - C) usa solo la clase mayoritaria
   - D) no se puede calcular

   **Respuesta:** A

60. Precision y recall altos implican:
   - A) F1 alto
   - B) F1 bajo
   - C) AUC bajo
   - D) accuracy baja siempre

   **Respuesta:** A

---

Fin del test.
