# MUSI - Preguntas tipo test resueltas (v3)

Formato: 4 opciones (A/B/C/D), respuesta correcta y explicacion breve.
Cobertura: lecture1 a lecture6c. Nivel: examen (mezcla con trampas).

---

## 1) Fundamentos y pipeline

1. En aprendizaje supervisado, la variable objetivo esta:
   - A) ausente
   - B) parcialmente observada
   - C) etiquetada
   - D) siempre normalizada

   **Respuesta:** C

2. El error de generalizacion se estima mejor con:
   - A) solo training set
   - B) datos no vistos (validacion/test)
   - C) regularizacion cero
   - D) aumentar epocas sin limite

   **Respuesta:** B

3. Si un modelo memoriza ruido del train, hablamos de:
   - A) underfitting
   - B) overfitting
   - C) data drift
   - D) bagging

   **Respuesta:** B

4. El flujo correcto de ML en produccion suele ser:
   - A) deploy -> evaluar -> entrenar
   - B) limpiar datos -> entrenar -> validar -> desplegar -> monitorizar
   - C) entrenar -> borrar test -> desplegar
   - D) elegir modelo -> fin

   **Respuesta:** B

5. En la formulacion de Mitchell, cambiar P sin cambiar T ni E implica:
   - A) misma definicion exacta del problema
   - B) cambia la forma de medir aprendizaje
   - C) no afecta nada
   - D) imposibilidad matematica

   **Respuesta:** B

---

## 2) Preprocesado y representacion

6. Si una feature tiene unidades muy grandes frente a otras, en metodos de distancia conviene:
   - A) eliminar la feature siempre
   - B) escalar/estandarizar
   - C) discretizar etiquetas
   - D) usar train+test para calcular media

   **Respuesta:** B

7. Hacer imputacion de missing values antes del split causa sobre todo:
   - A) menor varianza
   - B) leakage
   - C) mejor AUC garantizado
   - D) nada relevante

   **Respuesta:** B

8. One-hot encoding evita principalmente:
   - A) multicolinealidad
   - B) orden artificial en categorias nominales
   - C) overfitting en todos los casos
   - D) ruido gaussiano

   **Respuesta:** B

9. Una transformacion log suele ayudar cuando una variable es:
   - A) simetrica y centrada
   - B) fuertemente sesgada a la derecha
   - C) binaria
   - D) categorica nominal

   **Respuesta:** B

10. En un pipeline con CV, los transformadores deben hacer fit:
   - A) una sola vez en todo el dataset
   - B) dentro de cada fold de train
   - C) solo en test
   - D) despues de evaluar

   **Respuesta:** B

11. En deteccion de outliers con z-score, un umbral comun en valor absoluto es:
   - A) 0.5
   - B) 1.0
   - C) 3.0
   - D) 10.0

   **Respuesta:** C

---

## 3) Bayes y fronteras de decision

12. La regla MAP selecciona la clase con mayor:
   - A) p(x)
   - B) P(wi|x)
   - C) costo fijo
   - D) varianza residual

   **Respuesta:** B

13. Si los costes de error no son simetricos, el umbral de decision:
   - A) no cambia
   - B) debe ajustarse segun costes
   - C) siempre pasa a 0.5
   - D) depende solo de N

   **Respuesta:** B

14. En dos clases gaussianas con misma covarianza, la frontera Bayesiana es:
   - A) lineal
   - B) cuadratica
   - C) exponencial
   - D) no definida

   **Respuesta:** A

15. La distancia de Mahalanobis incorpora:
   - A) solo norma L1
   - B) correlacion entre variables via covarianza
   - C) solo media
   - D) informacion temporal

   **Respuesta:** B

16. Si priors cambian fuertemente hacia una clase, sin cambiar likelihoods, la frontera:
   - A) no se mueve
   - B) se desplaza favoreciendo la clase mas probable a priori
   - C) se vuelve circular
   - D) desaparece

   **Respuesta:** B

---

## 4) Regresion y optimizacion

17. En OLS, el residuo es:
   - A) y_pred - y_true con signo opuesto obligatorio
   - B) y_true - y_pred
   - C) solo su valor absoluto
   - D) la pendiente

   **Respuesta:** B

18. En regresion lineal, multicolinealidad alta suele provocar:
   - A) coeficientes inestables
   - B) error de train cero siempre
   - C) desaparicion del sesgo
   - D) independencia entre features

   **Respuesta:** A

19. Ridge penaliza principalmente:
   - A) suma de valores absolutos
   - B) norma L2 de los coeficientes
   - C) numero de muestras
   - D) entropia del target

   **Respuesta:** B

20. Lasso puede llevar algunos coeficientes exactamente a:
   - A) 1
   - B) infinito
   - C) 0
   - D) media

   **Respuesta:** C

21. En descenso por gradiente, batch GD usa:
   - A) una muestra por actualizacion
   - B) todo el dataset por paso
   - C) solo outliers
   - D) mini-batches aleatorios de tamaño fijo 1

   **Respuesta:** B

22. En regresion logistica binaria, la salida del modelo antes de umbral es:
   - A) probabilidad en [0,1] tras sigmoide
   - B) distancia euclidea
   - C) score de silhouette
   - D) SSE

   **Respuesta:** A

---

## 5) Arboles y ensembles

23. En un arbol de decision, un split util produce:
   - A) mayor impureza media
   - B) menor impureza media ponderada
   - C) menos datos siempre
   - D) clases aleatorias

   **Respuesta:** B

24. Limitar `max_depth` normalmente:
   - A) reduce varianza y puede subir sesgo
   - B) reduce sesgo y varianza siempre
   - C) solo afecta tiempo, no generalizacion
   - D) impide entrenar

   **Respuesta:** A

25. Random Forest introduce aleatoriedad con:
   - A) una sola semilla y sin bootstrap
   - B) bootstrap y submuestreo de features
   - C) solo regularizacion L2
   - D) etiquetas sinteticas

   **Respuesta:** B

26. En boosting, cada nuevo modelo intenta:
   - A) ignorar los errores previos
   - B) corregir errores de los modelos anteriores
   - C) entrenarse en paralelo independiente
   - D) maximizar bagging score

   **Respuesta:** B

27. Comparado con un arbol unico profundo, un RF suele:
   - A) tener mas varianza
   - B) ser mas robusto y menos sensible al overfitting
   - C) requerir menos memoria siempre
   - D) no permitir multiclass

   **Respuesta:** B

---

## 6) Instance-based learning y kNN

28. kNN se considera lazy learner porque:
   - A) no entrena explicitamente un modelo parametrico complejo
   - B) nunca usa distancia
   - C) optimiza una funcion convexa en train
   - D) necesita backprop

   **Respuesta:** A

29. Usar `weights='distance'` en kNN implica:
   - A) todos los vecinos pesan igual
   - B) vecinos cercanos influyen mas
   - C) solo cuenta el vecino mas lejano
   - D) elimina necesidad de escalar

   **Respuesta:** B

30. Aumentar mucho `k` tiende a:
   - A) bajar sesgo y subir varianza
   - B) subir sesgo y bajar varianza
   - C) bajar ambos siempre
   - D) no cambiar nada

   **Respuesta:** B

31. En alta dimensionalidad, kNN puede degradar por:
   - A) maldicion de la dimensionalidad
   - B) exceso de etiquetas
   - C) falta de convexidad
   - D) no usar GPU

   **Respuesta:** A

32. En reduccion de prototipos IBL, el objetivo principal es:
   - A) aumentar el set de entrenamiento
   - B) mantener rendimiento reduciendo almacenamiento/calculo
   - C) convertir problema en supervisado
   - D) forzar linealidad

   **Respuesta:** B

---

## 7) SVM

33. Hard-margin SVM es aplicable cuando los datos son:
   - A) perfectamente separables linealmente
   - B) no separables
   - C) no etiquetados
   - D) solo 1D

   **Respuesta:** A

34. En soft-margin SVM, `C` pequeno suele:
   - A) penalizar mucho errores
   - B) permitir mas violaciones del margen
   - C) eliminar regularizacion
   - D) forzar margen nulo

   **Respuesta:** B

35. Un kernel RBF puede modelar:
   - A) solo fronteras lineales
   - B) fronteras no lineales
   - C) solo regresion
   - D) un unico support vector

   **Respuesta:** B

36. En formulacion dual de SVM, solo puntos con alpha>0 son:
   - A) outliers obligatorios
   - B) support vectors
   - C) centroides
   - D) datos sinteticos

   **Respuesta:** B

37. En OVR para M clases se entrenan:
   - A) M(M-1)/2 clasificadores
   - B) M clasificadores binarios
   - C) 1 clasificador multicapa obligatorio
   - D) 2M+1 clasificadores

   **Respuesta:** B

---

## 8) Clustering y validez

38. En clustering, usar etiquetas reales para evaluar pureza es:
   - A) valida solo si existen labels de referencia externas
   - B) obligatorio siempre
   - C) imposible
   - D) equivalente a silhouette

   **Respuesta:** A

39. K-means asume implicitamente clusters:
   - A) arbitrarios y no convexos
   - B) aproximadamente esfericos y de varianza similar
   - C) jerarquicos estrictos
   - D) siempre balanceados exactos

   **Respuesta:** B

40. En K-means, un mal inicializado puede:
   - A) converger a minimos locales pobres
   - B) garantizar optimo global
   - C) romper el algoritmo
   - D) impedir calcular distancias

   **Respuesta:** A

41. El indice silhouette promedio se interpreta mejor cuando:
   - A) es cercano a -1
   - B) es cercano a 0
   - C) es alto y positivo
   - D) es exactamente 0.5 siempre

   **Respuesta:** C

42. En Davies-Bouldin, menor valor indica:
   - A) peor separacion relativa
   - B) mejor compromiso cohesion/separacion
   - C) mas clusters obligatorios
   - D) sobreajuste supervisado

   **Respuesta:** B

43. En clustering jerarquico aglomerativo, el dendrograma permite:
   - A) elegir cortes para distintos numeros de clusters
   - B) calcular ROC
   - C) entrenar SVM
   - D) obtener gradientes

   **Respuesta:** A

---

## 9) Evaluacion, CV y model selection

44. Hold-out simple puede dar estimaciones inestables cuando:
   - A) dataset pequeno
   - B) dataset enorme y balanceado
   - C) modelo lineal
   - D) hay escalado

   **Respuesta:** A

45. Stratified k-fold en clasificacion ayuda a:
   - A) mantener proporcion de clases por fold
   - B) aumentar k automaticamente
   - C) eliminar leakage
   - D) mejorar siempre accuracy

   **Respuesta:** A

46. En nested CV, la estimacion menos sesgada de rendimiento final sale del:
   - A) loop interno
   - B) loop externo
   - C) train global
   - D) mejor fold interno

   **Respuesta:** B

47. Si optimizas hiperparametros con test set, el resultado suele:
   - A) ser valido y no sesgado
   - B) sobreestimar rendimiento real
   - C) mejorar calibracion siempre
   - D) equivaler a nested CV

   **Respuesta:** B

48. En clases desbalanceadas, PR-AUC suele ser util porque:
   - A) ignora falsos positivos
   - B) enfatiza precision/recall de clase positiva
   - C) sustituye toda metrica
   - D) solo sirve en regresion

   **Respuesta:** B

49. Macro-F1 frente a weighted-F1: macro-F1:
   - A) pondera por frecuencia
   - B) da igual peso a cada clase
   - C) ignora clases minoritarias
   - D) siempre es mayor

   **Respuesta:** B

50. Una matriz de confusion en binario contiene:
   - A) TP, FP, FN, TN
   - B) solo precision y recall
   - C) AUC y accuracy
   - D) SSE y MSE

   **Respuesta:** A

---

## 10) Preguntas de integracion (trampas de examen)

51. Si escalas antes de separar train/test y luego haces CV, el riesgo principal es:
   - A) underfitting
   - B) leakage y score inflado
   - C) mayor tiempo sin impacto
   - D) overfitting eliminado

   **Respuesta:** B

52. Si train acc=99% y val acc=70%, la accion mas razonable primero es:
   - A) aumentar complejidad
   - B) regularizar/simplificar modelo o mejorar datos
   - C) eliminar validacion
   - D) usar test para entrenar

   **Respuesta:** B

53. En un problema con coste FN >> FP, conviene normalmente:
   - A) subir umbral de clase positiva
   - B) bajar umbral para aumentar recall
   - C) maximizar solo precision
   - D) ignorar costes

   **Respuesta:** B

54. Si dos modelos tienen AUC similar, pero uno tiene mejor recall en umbral operativo, elegirlo puede ser correcto porque:
   - A) AUC decide todo siempre
   - B) la decision depende del punto operativo/coste
   - C) recall no importa
   - D) ROC invalida PR

   **Respuesta:** B

55. En GridSearchCV con pipeline, el prefijo de hiperparametro correcto de un paso `clf` es:
   - A) `param_clf__`
   - B) `clf__`
   - C) `step.clf.`
   - D) `model:`

   **Respuesta:** B

56. En k-means, comparar SSE entre distintos datasets para elegir k es:
   - A) correcto directamente
   - B) no comparable sin contexto/escala
   - C) siempre mejor que silhouette
   - D) equivalente a DB index

   **Respuesta:** B

57. Si una clase tiene recall muy bajo y precision alta, suele indicar:
   - A) predicciones positivas conservadoras (muchos FN)
   - B) demasiados FP
   - C) error de etiquetado siempre
   - D) calibracion perfecta

   **Respuesta:** A

58. En RF, aumentar mucho numero de arboles normalmente:
   - A) empeora siempre
   - B) estabiliza rendimiento hasta saturar
   - C) sube sesgo drasticamente
   - D) elimina necesidad de validacion

   **Respuesta:** B

59. En SVM RBF, escoger gamma demasiado alto suele:
   - A) frontera muy suave
   - B) frontera muy flexible con riesgo de overfitting
   - C) equivalente a lineal
   - D) impedir convergencia siempre

   **Respuesta:** B

60. La mejor practica final antes de reportar metricas es:
   - A) elegir mejor split y reportar ese
   - B) fijar protocolo de evaluacion y reportar media/dispersion
   - C) ajustar en test para mejorar numeros
   - D) usar solo accuracy

   **Respuesta:** B

---

Fin del test.
