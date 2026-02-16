# MUSI - Super resumen (lectures 1-6)

Enfocado a examen tipo test del Dr. Alberto Ortiz Rodriguez. Resumen medio con conceptos, formulas y decisiones tipicas.

---

## Lecture 1 - Introduccion a ML

- ML como subcampo de IA: aprende de datos para mejorar desempeno en una tarea T con experiencia E y medida P (Mitchell).
- Clasificacion vs regresion: clasificacion -> etiquetas; regresion -> valores continuos.
- Flujo basico: captura de datos -> preprocesado -> extraccion de caracteristicas -> modelo -> evaluacion.
- Ejemplo de peces: una sola feature puede ser pobre; combinar features mejora separacion.
- Regla de decision: elegir clase con mayor $P(\omega_i|x)$ (MAP). Con priori iguales, comparar $p(x|\omega_i)$.
- Generalizacion: evitar sobreajuste; modelo simple suele generalizar mejor (navaja de Occam).
- Matriz de confusion y accuracy: $Acc=(TP+TN)/(TP+TN+FP+FN)$.

---

## Lecture 2 - Analisis de datos

- Exploracion inicial: estadisticos (media, varianza), histogramas, SPLOM, parallel coordinates.
- Limpieza basica: eliminar columnas irrelevantes, duplicados, revisar nulos.
- Preprocesado:
  - Categorical -> numerico: LabelEncoder o OneHotEncoder.
  - Outliers: detectar y tratar (IQR, z-score, inspeccion).
  - Normalizacion / estandarizacion: min-max o z-score.
  - Missing values: imputacion (media/mediana/moda) o eliminar.
- Medidas de bondad: seleccionar features con alta separacion entre clases y baja varianza intra-clase.
- Feature selection vs dimensionality reduction: elegir subset vs transformar (p.ej. PCA).
- Pipelines: evitar leakage; ajustar transformaciones solo con train.

---

## Lecture 3.1 - Clasificacion Bayesiana y lineal

- Regla Bayesiana: asignar a clase con mayor posterior $P(\omega_i|x)$.
- Error de Bayes: minimo teorico; mover el umbral aumenta $P_e$.
- Gaussianas:
  - Diferentes covarianzas -> clasificador cuadratico.
  - Misma covarianza -> clasificador lineal; frontera hiperplano.
- Con $\Sigma=\sigma^2 I$: decision por distancia euclidea a las medias.
- Con $\Sigma$ generica: decision por distancia de Mahalanobis.
- Estimacion de densidades:
  - Parametrica: ML (max likelihood).
  - No parametrica: Parzen, kNN.
- Lineal discriminante / perceptron: frontera hiperplano, aprende $w$.

---

## Lecture 3.2 - Regresion

- Regresion lineal: minimizar RSS. Solucion cerrada (normal equations).
- $R^2$ mide varianza explicada; cuanto mayor, mejor ajuste.
- Errores estandar y CI para parametros; RSE estima varianza del ruido.
- Regresion multiple: solucion matricial con pseudoinversa $X^+$.
- Regresion polinomial: es lineal en parametros tras expandir features.
- Gradiente descendente: iterativo, requiere learning rate; pros/contras vs solucion cerrada.
- Regresion logistica:
  - Usa sigmoid $g(z)=1/(1+e^{-z})$.
  - Loss: entropia cruzada binaria (no MSE).

---

## Lecture 3.3 - Arboles y ensembles

- Decision trees (OBCT): preguntas del tipo $x_k <= \alpha_k$.
- Criterios de split: entropia (ID3) o Gini (CART).
- Elegir split que maximiza reduccion de impureza.
- Parada/pruning: pureza, min samples, max depth, min impurity decrease.
- Regression trees: minimizan MSE en lugar de impureza.
- Ensembles:
  - Voting (hard/soft).
  - Bagging: reduce varianza.
  - Boosting: aprende secuencial corrigiendo errores.
  - Random Forest: bagging + submuestreo de features.

---

## Lecture 4.1 - Instance-based learning (IBL)

- No hay modelo global; usa ejemplos almacenados.
- Ventaja: adapta rapido a nuevos datos; coste de memoria alto.
- Algoritmos: kNN, SVM, RBFN, etc.
- Reduccion de instancias para evitar sobreajuste y coste.

---

## Lecture 4.2 - SVM

- Objetivo: hiperplano con maximo margen (mejor generalizacion).
- Support vectors: puntos que definen el margen.
- Formulacion primal y dual con KKT.
- Soft margin: variables de holgura $\xi_i$ y parametro $C$ (penaliza errores).
- No lineal: kernels (polinomial, RBF); evita mapear explicitamente.
- Multiclase: OVR o OVO.

---

## Lecture 4.3 - kNN

- Clasifica por mayoria de los $k$ vecinos mas cercanos.
- Distancias: Minkowski, euclidea, etc.
- Elegir $k$: pequeno -> varianza alta; grande -> sesgo alto.
- Ties: voto ponderado por distancia o clase del vecino mas cercano.
- Coste alto en inferencia; usar k-d tree, ball tree o ANN.
- Condensed NN: reducir instancias manteniendo precision.

---

## Lecture 5.1 - Unsupervised learning: introduccion

- Objetivo: descubrir estructura sin etiquetas (clustering).
- Clustering = particion en grupos con alta similitud interna y separacion externa.
- Medidas de proximidad:
  - Dissimilarity: metricas $L_p$ (Minkowski), Canberra, Bray-Curtis.
  - Similarity: coseno, Tanimoto.
  - Binario: Hamming/Jaccard.
  - Categorial/ordinal: codificar con cuidado.
- Proximidad entre clusters: min, max, avg o centroides.

---

## Lecture 5.2 - Clustering jerarquico

- Produce jerarquia (dendrograma), no una sola particion.
- Agglomerative (bottom-up) vs divisive (top-down).
- Linkage:
  - Single-link: efecto cadena (clusters alargados).
  - Complete-link: clusters compactos.
  - Average-link: intermedio.
  - Ward: minimo incremento de varianza.
- Cortar dendrograma: buscar saltos grandes o clusters con vida larga.
- Monotonicidad: dendrograma valido si distancias de fusion no disminuyen.

---

## Lecture 5.3 - Clustering basado en optimizacion

- Hard clustering: asignacion binaria $u_{ij}\in{0,1}$.
- K-means: minimiza suma de distancias al cuadrado; sensible a init y outliers.
- K-means++: mejor inicializacion.
- K-medoids (PAM): usa medoids, mas robusto a outliers.
- Soft clustering: Fuzzy c-Means, $u_{ij}\in[0,1]$, controla fuzzifier $q$.
- Possibilistic clustering (PCM): memberships independientes, mas robusto a ruido.
- Mixture models: idea de clusters como distribuciones (GMM).

---

## Lecture 6a - Evaluacion supervisada

- Bias-variance tradeoff: complejidad alta -> varianza; baja -> sesgo.
- Metricas:
  - Precision $=TP/(TP+FP)$
  - Recall $=TP/(TP+FN)$
  - F1 $=2PR/(P+R)$
  - Macro vs micro en multiclase.
- Validacion: holdout, k-fold, stratified k-fold, LOOCV, nested CV.
- ROC y AUC: mayor AUC mejor; diagonal = azar.
- Learning curves: detectar under/overfitting.
- Tuning: grid search sobre hiperparametros.

---

## Lecture 6b - Validez de clustering

- Clusterability: SPLOM, parallel coordinates, Hopkins (H~0.5 no estructura; H1->0 clusterable; H2->1 clusterable), VAT.
- Elbow: elegir $M$ donde mejora adicional baja.
- Silhouette $s(i)$: cerca de 1 bueno, 0 frontera, negativo mal asignado.
- Indices internos: Dunn (max), Davies-Bouldin (min).
- Indices externos: homogeneity, completeness, V-measure.

---

## Lecture 6c - Preprocesado, tuning y evaluacion en sklearn

- Evitar leakage: ajustar scalers solo con train, luego transformar test.
- GridSearchCV: define param_grid, scoring y CV; refit al mejor.
- Cross-validate: usar StratifiedKFold en clasificacion.
- Pipeline: encadena scaler + modelo para CV limpia.
- Metricas en sklearn: accuracy, precision, recall, f1, classification_report.
