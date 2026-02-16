# MUSI — Preguntas tipo test resueltas

Formato: 4 opciones (A/B/C/D), respuesta correcta y explicación breve.

---

## 1) Bayes y clasificación

1. En clasificación Bayesiana (MAP), se asigna la clase con:
   - A) mayor \(p(x|\omega_i)\)
   - B) mayor \(P(\omega_i|x)\)
   - C) menor \(P(\omega_i)\)
   - D) mayor varianza

   **Respuesta:** B

   **Por qué:** MAP maximiza la probabilidad posterior \(P(\omega_i|x)\).

2. Si \(P(\omega_1|x)=0.49\) y \(P(\omega_2|x)=0.51\), la decisión Bayes correcta es:
   - A) \(\omega_1\)
   - B) \(\omega_2\)
   - C) empate
   - D) no se puede decidir

   **Respuesta:** B

3. Con priori iguales y costes iguales, la regla se reduce a:
   - A) minimizar distancia al origen
   - B) maximizar \(p(x|\omega_i)\)
   - C) maximizar \(P(\omega_i)\)
   - D) minimizar \(\|w\|\)

   **Respuesta:** B

---

## 2) Regresión lineal

4. En regresión lineal simple, \(R^2\) mide:
   - A) error absoluto medio
   - B) porcentaje de varianza explicada
   - C) número de variables
   - D) tamaño muestral

   **Respuesta:** B

5. Si \(RSS\) baja y \(TSS\) se mantiene, \(R^2\):
   - A) baja
   - B) no cambia
   - C) sube
   - D) se hace negativo siempre

   **Respuesta:** C

6. ¿Cuál es cierto sobre OLS?
   - A) minimiza suma de errores absolutos
   - B) minimiza suma de errores cuadrados
   - C) maximiza precisión
   - D) minimiza entropía

   **Respuesta:** B

7. Si un modelo tiene \(\hat y=b_0+b_1x\) y \(b_1<0\), entonces:
   - A) relación directa
   - B) relación inversa
   - C) no hay relación
   - D) depende de \(b_0\)

   **Respuesta:** B

---

## 3) Árboles y ensembles

8. La impureza Gini en un nodo puro vale:
   - A) 1
   - B) 0.5
   - C) 0
   - D) depende de \(N\)

   **Respuesta:** C

9. En un split de clasificación se suele elegir el que:
   - A) maximiza impureza hija
   - B) minimiza ganancia
   - C) maximiza reducción de impureza
   - D) maximiza profundidad

   **Respuesta:** C

10. Random Forest reduce principalmente:
   - A) sesgo por árboles más profundos
   - B) varianza por agregación
   - C) dimensión de datos
   - D) coste de etiquetado

   **Respuesta:** B

11. Boosting se caracteriza por:
   - A) entrenar modelos en paralelo independientes
   - B) entrenar secuencialmente corrigiendo errores
   - C) usar solo árboles de profundidad 1
   - D) no usar pesos

   **Respuesta:** B

---

## 4) SVM

12. En SVM lineal duro, el margen geométrico total es:
   - A) \(\|w\|\)
   - B) \(1/\|w\|\)
   - C) \(2/\|w\|\)
   - D) \(2\|w\|\)

   **Respuesta:** C

13. Los support vectors son puntos que:
   - A) siempre están mal clasificados
   - B) están más lejos del hiperplano
   - C) definen el margen
   - D) son outliers obligatoriamente

   **Respuesta:** C

14. Aumentar mucho \(C\) en soft-margin suele:
   - A) aumentar regularización
   - B) penalizar más errores
   - C) hacer kernel lineal
   - D) bajar dimensionalidad

   **Respuesta:** B

15. Un kernel RBF permite:
   - A) solo fronteras lineales
   - B) fronteras no lineales
   - C) eliminar soporte vectorial
   - D) calcular Gini

   **Respuesta:** B

---

## 5) kNN

16. En kNN, elegir \(k\) muy pequeño suele:
   - A) aumentar sesgo
   - B) aumentar varianza
   - C) reducir sensibilidad al ruido
   - D) impedir clasificación

   **Respuesta:** B

17. Elegir \(k\) muy grande suele:
   - A) sobreajustar
   - B) suavizar demasiado la frontera
   - C) eliminar necesidad de distancia
   - D) mejorar siempre accuracy

   **Respuesta:** B

18. En kNN con distancia euclídea, es importante escalar porque:
   - A) mejora precisión teórica garantizada
   - B) evita que variables grandes dominen distancia
   - C) reduce número de clases
   - D) convierte a lineal

   **Respuesta:** B

19. En empate de votos, una estrategia común es:
   - A) descartar muestra
   - B) usar clases aleatorias
   - C) ponderar por distancia
   - D) bajar \(k\) a 1 siempre

   **Respuesta:** C

---

## 6) Normalizacion y outliers

20. La normalizacion min-max transforma una variable \(x\) a:
   - A) \((x-\mu)/\sigma\)
   - B) \(x/\max(x)\)
   - C) \((x-\min)/(\max-\min)\)
   - D) \(\log(x)\)

   **Respuesta:** C

21. Un outlier en regresion suele:
   - A) reducir el error de test
   - B) afectar fuertemente a la pendiente OLS
   - C) no influir en el ajuste
   - D) mejorar siempre \(R^2\)

   **Respuesta:** B

---

## 7) Clustering jerárquico

22. Single-link entre dos clusters usa:
   - A) distancia máxima entre pares
   - B) distancia media
   - C) distancia mínima entre pares
   - D) distancia al centroide

   **Respuesta:** C

23. Complete-link usa:
   - A) distancia mínima
   - B) distancia máxima
   - C) mediana
   - D) varianza total

   **Respuesta:** B

24. En Ward se fusiona el par que:
   - A) minimiza incremento de varianza intra
   - B) minimiza distancia Manhattan
   - C) maximiza silhouette
   - D) maximiza número de muestras

   **Respuesta:** A

---

## 8) k-means

25. k-means optimiza principalmente:
   - A) accuracy
   - B) SSE / inercia intra-cluster
   - C) AUC
   - D) F1

   **Respuesta:** B

26. El centroide de un clúster en k-means es:
   - A) muestra más cercana al origen
   - B) media de puntos asignados
   - C) mediana global
   - D) punto con mayor densidad

   **Respuesta:** B

27. k-means++ se usa para:
   - A) elegir k óptimo
   - B) inicializar centroides mejor
   - C) calcular silhouette
   - D) reducir dimensiones

   **Respuesta:** B

28. Una limitación clásica de k-means es:
   - A) no necesita \(k\)
   - B) no sensible a inicialización
   - C) favorece clusters aproximadamente esféricos
   - D) funciona mejor con categorías

   **Respuesta:** C

---

## 9) Evaluación supervisada

29. Precision se define como:
   - A) \(TP/(TP+FN)\)
   - B) \(TP/(TP+FP)\)
   - C) \((TP+TN)/N\)
   - D) \(TN/(TN+FP)\)

   **Respuesta:** B

30. Recall (TPR) se define como:
   - A) \(TP/(TP+FN)\)
   - B) \(TP/(TP+FP)\)
   - C) \(FP/(FP+TN)\)
   - D) \(TN/(TN+FN)\)

   **Respuesta:** A

31. En ROC, el eje X es:
   - A) TPR
   - B) Precision
   - C) FPR
   - D) Accuracy

   **Respuesta:** C

32. AUC cercana a 0.5 indica:
   - A) clasificador casi aleatorio
   - B) clasificador perfecto
   - C) overfitting seguro
   - D) error cero

   **Respuesta:** A

33. F1-score es la media:
   - A) aritmética de P y R
   - B) geométrica de P y R
   - C) armónica de P y R
   - D) ponderada por TN

   **Respuesta:** C

34. En datos desbalanceados, accuracy alta puede ser:
   - A) siempre confiable
   - B) engañosa
   - C) igual a F1
   - D) equivalente a AUC

   **Respuesta:** B

---

## 10) Validez de clustering y tuning

35. En silhouette, valor cercano a 1 sugiere:
   - A) mala separación
   - B) buena cohesión y separación
   - C) ruido puro
   - D) demasiados clusters siempre

   **Respuesta:** B

36. En el método del codo, se elige \(k\) donde:
   - A) WCSS sube
   - B) WCSS se hace cero
   - C) la mejora adicional empieza a ser pequeña
   - D) silhouette es negativa

   **Respuesta:** C

37. Para evitar data leakage en tuning con CV:
   - A) escalar antes de dividir
   - B) pipeline dentro de CV
   - C) usar test set para elegir hiperparámetros
   - D) repetir train-test split al azar

   **Respuesta:** B

38. GridSearchCV elige hiperparámetros según:
   - A) score medio de validación
   - B) score de entrenamiento
   - C) menor tiempo de cómputo
   - D) mayor número de parámetros

   **Respuesta:** A

---

## Plantilla rápida para resolver tipo test

1. Detecta la fórmula/definición clave.
2. Descarta opciones incompatibles por rango/definición.
3. Si hay números, calcula en 2 pasos y compara.
4. Marca y revisa al final las dudosas.

Si quieres, te preparo ahora un **test cronometrado de 50 preguntas** (nivel examen real) con hoja de respuestas y nota automática.