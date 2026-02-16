# MUSI — Ejercicios resueltos (Set 2)

Más práctica del mismo estilo: aplicar fórmula + decisión lógica.

---

## Tema 3.1 — Bayes y clasificadores lineales

### Ejercicio 1 (MAP con priori desbalanceadas)
Datos:
- \(P(\omega_1)=0.3\), \(P(\omega_2)=0.7\)
- \(p(x|\omega_1)=0.9\), \(p(x|\omega_2)=0.4\)

**Resolución**
\[
score_1=0.9\cdot 0.3=0.27,\quad score_2=0.4\cdot 0.7=0.28
\]
\(score_2>score_1\) \(\Rightarrow\) clase \(\omega_2\).

**Resultado:** \(x\in\omega_2\).

### Ejercicio 2 (frontera de decisión)
\(g(x)=w^Tx+w_0\), \(w=(1,2)\), \(w_0=-4\).

Clasificar:
- \(x_a=(2,1)\)
- \(x_b=(1,0)\)

**Resolución**
\[
g(x_a)=1\cdot2+2\cdot1-4=0
\]
\[
g(x_b)=1\cdot1+2\cdot0-4=-3<0
\]

**Resultado:** \(x_a\) en frontera, \(x_b\) clase negativa.

### Ejercicio 3 (error de Bayes con regla)
Si para una región \(R\): \(P(\omega_1|x)=0.45\), \(P(\omega_2|x)=0.55\),
la regla Bayes decide \(\omega_2\).

**Resolución**
Error condicional mínimo en \(R\):
\[
P(error|x)=1-\max\{0.45,0.55\}=0.45
\]

**Resultado:** error mínimo local = 0.45.

---

## Tema 3.2 — Regresión lineal

### Ejercicio 1 (predicción puntual)
Modelo ajustado: \(\hat y=2.1+1.7x\).
Calcular \(\hat y\) para \(x=3.5\).

**Resolución**
\[
\hat y=2.1+1.7\cdot3.5=2.1+5.95=8.05
\]

**Resultado:** \(\hat y=8.05\).

### Ejercicio 2 (MSE)
Valores reales \(y=[4,6,7]\), predicción \(\hat y=[5,5,8]\).

**Resolución**
Errores: \([-1,1,-1]\), cuadrados: \([1,1,1]\).
\[
MSE=\frac{1+1+1}{3}=1
\]

**Resultado:** \(MSE=1\).

### Ejercicio 3 (comparar modelos por \(R^2\))
Modelo A: \(R^2=0.72\). Modelo B: \(R^2=0.64\).

**Resolución**
Mayor \(R^2\) implica mayor fracción de varianza explicada.

**Resultado:** mejor ajuste global: **Modelo A**.

---

## Tema 3.3 — Árboles y ensemble

### Ejercicio 1 (Gini rápido)
Nodo con proporciones \((0.5,0.3,0.2)\).

**Resolución**
\[
G=1-(0.5^2+0.3^2+0.2^2)=1-(0.25+0.09+0.04)=0.62
\]

**Resultado:** \(G=0.62\).

### Ejercicio 2 (entropía pura)
Nodo con todas las muestras en una sola clase.

**Resolución**
Si \(p=1\) para una clase y 0 para las demás:
\[
H=-1\log_2(1)-\sum 0\log_2(0)=0
\]

**Resultado:** entropía mínima \(H=0\).

### Ejercicio 3 (bagging vs boosting)
Dos modelos ensemble:
- A: reduce varianza combinando árboles independientes.
- B: entrena secuencialmente enfocando errores previos.

**Resolución**
A corresponde a Bagging/Random Forest.
B corresponde a Boosting.

**Resultado:** A = bagging, B = boosting.

---

## Tema 4.2 — SVM

### Ejercicio 1 (distancia a hiperplano)
Hiperplano: \(2x_1-x_2+1=0\). Punto \(x=(1,3)\).

**Resolución**
Distancia:
\[
d=\frac{|2\cdot1-3+1|}{\sqrt{2^2+(-1)^2}}=\frac{0}{\sqrt5}=0
\]

**Resultado:** el punto está sobre el hiperplano.

### Ejercicio 2 (clasificación)
\(g(x)= -x_1 + 0.5x_2 + 2\).
Clasificar \((2,2)\), \((5,1)\).

**Resolución**
\[
g(2,2)=-2+1+2=1>0
\]
\[
g(5,1)=-5+0.5+2=-2.5<0
\]

**Resultado:** primero positivo, segundo negativo.

### Ejercicio 3 (efecto de C)
Compara SVM con \(C\) muy alto vs \(C\) bajo.

**Resolución**
- \(C\) alto: penaliza más errores, margen más estrecho, riesgo de sobreajuste.
- \(C\) bajo: admite más errores, margen más ancho, más regularización.

**Resultado:** \(C\) controla el compromiso margen-error.

---

## Tema 4.3 — kNN

### Ejercicio 1 (1-NN)
Puntos clase A: \((0,0),(1,0)\), clase B: \((3,3),(4,3)\).
Clasificar \(q=(1.2,0.1)\) con \(k=1\).

**Resolución**
Vecino más cercano: \((1,0)\) (clase A).

**Resultado:** clase A.

### Ejercicio 2 (k=5 y mayoría)
Entre 5 vecinos más cercanos: clases \([A,B,A,A,B]\).

**Resolución**
Conteo: A=3, B=2.

**Resultado:** clase A.

### Ejercicio 3 (normalización)
Variables: edad (18–70) e ingresos (1k–200k).

**Resolución**
Sin escalar, domina ingresos en distancia euclídea.
Se recomienda estandarizar antes de kNN.

**Resultado:** aplicar escalado (z-score o min-max).

---

## Tema 4.4 — Normalización y outliers

### Ejercicio 1 (min-max)
Para una variable con \(\min=10\), \(\max=40\), normaliza \(x=25\).

**Resolución**
\[
x' = \frac{x-\min}{\max-\min} = \frac{25-10}{40-10} = \frac{15}{30} = 0.5
\]

**Resultado:** \(x'=0.5\).

### Ejercicio 2 (z-score)
Media \(\mu=70\), desviación \(\sigma=5\). Calcula el z-score de \(x=80\).

**Resolución**
\[
z = \frac{x-\mu}{\sigma} = \frac{80-70}{5} = 2
\]

**Resultado:** \(z=2\).

### Ejercicio 3 (outlier con IQR)
Para una variable con \(Q_1=10\), \(Q_3=22\), determina si \(x=41\) es outlier.

**Resolución**
\[
IQR = Q_3 - Q_1 = 12
\]
\[
	ext{Límite superior} = Q_3 + 1.5\cdot IQR = 22 + 18 = 40
\]
Como \(41>40\), es outlier.

**Resultado:** \(x=41\) es outlier.

---

## Tema 5.2 — Clustering jerárquico

### Ejercicio 1 (average-link)
Entre \(C_A=\{x_1,x_2\}\), \(C_B=\{x_3,x_4\}\):
\(d_{13}=2\), \(d_{14}=6\), \(d_{23}=4\), \(d_{24}=8\).

**Resolución**
\[
d_{avg}(C_A,C_B)=\frac{2+6+4+8}{4}=5
\]

**Resultado:** distancia average-link = 5.

### Ejercicio 2 (Ward, idea)
Se fusionan dos pares candidatos:
- Fusión A incrementa varianza intra en 3.2
- Fusión B incrementa varianza intra en 1.1

**Resolución**
Ward elige menor aumento de varianza.

**Resultado:** elegir **Fusión B**.

### Ejercicio 3 (corte de dendrograma)
Al cortar a altura \(h=7\) aparecen 4 grupos; a \(h=12\), 2 grupos.

**Resultado:** mayor altura de corte \(\Rightarrow\) menos clusters.

---

## Tema 5.3 — k-means y optimización

### Ejercicio 1 (SSE de un clúster)
Clúster \(C\): \((1,1),(2,1),(1,2)\), centro \(\mu=(1.33,1.33)\).

**Resolución**
\[
SSE=\sum_{x\in C}\|x-\mu\|^2
\]
Aproximando:
- \((1,1)\): 0.22
- \((2,1)\): 0.56
- \((1,2)\): 0.56
\[
SSE\approx1.34
\]

**Resultado:** \(SSE\approx1.34\).

### Ejercicio 2 (criterio de parada)
Iteración \(t\): centroides cambian \(<10^{-4}\) en norma.

**Resultado:** se puede parar (convergencia práctica).

### Ejercicio 3 (inicialización)
¿Por qué usar k-means++ frente a inicialización aleatoria pura?

**Resolución**
k-means++ separa mejor centroides iniciales y suele evitar malos mínimos locales.

**Resultado:** más estabilidad y mejor coste final en promedio.

---

## Tema 6a — Evaluación supervisada

### Ejercicio 1 (accuracy)
TP=50, TN=30, FP=10, FN=10.

**Resolución**
\[
Accuracy=\frac{TP+TN}{TP+TN+FP+FN}=\frac{80}{100}=0.8
\]

**Resultado:** accuracy = 0.80.

### Ejercicio 2 (F\(_\beta\), \(\beta=2\))
Con \(P=0.75\), \(R=0.60\):
\[
F_\beta=\frac{(1+\beta^2)PR}{\beta^2P+R},\quad \beta=2
\]
\[
F_2=\frac{5\cdot0.75\cdot0.60}{4\cdot0.75+0.60}=\frac{2.25}{3.60}=0.625
\]

**Resultado:** \(F_2=0.625\).

### Ejercicio 3 (macro vs micro)
En multiclase desbalanceada, ¿qué promedio es más sensible a clases minoritarias?

**Resolución**
Macro promedia por clase dando igual peso a cada una.

**Resultado:** usar **macro** cuando importan clases minoritarias.

---

## Tema 6b — Validez de clustering

### Ejercicio 1 (silhouette medio)
Silhouettes de 5 muestras: \([0.7,0.4,0.5,0.2,0.6]\).

**Resolución**
\[
\bar s=\frac{0.7+0.4+0.5+0.2+0.6}{5}=0.48
\]

**Resultado:** silhouette medio = 0.48.

### Ejercicio 2 (interpretación Hopkins)
Se obtiene \(H=0.18\).

**Resolución**
Valores bajos suelen indicar estructura de clúster (no distribución uniforme aleatoria).

**Resultado:** hay evidencia de clusterabilidad.

### Ejercicio 3 (elbow)
WCSS: \([900,500,320,250,230]\).

**Resolución**
Grandes descensos hasta \(k=3\), luego mejora marginal.

**Resultado:** elección razonable \(k=3\).

---

## Tema 6c — Tuning y pipeline

### Ejercicio 1 (selección de hiperparámetros)
Resultados CV:
- modelo A: 0.86 ± 0.03
- modelo B: 0.88 ± 0.07
- modelo C: 0.87 ± 0.02

**Resolución**
B tiene media mayor, pero varianza alta; C es más estable con media muy cercana.
En examen, justificar criterio: rendimiento medio vs estabilidad.

**Resultado:** elección defendible: **C** (si priorizas robustez) o **B** (si solo max media).

### Ejercicio 2 (data leakage)
Se hace selección de variables antes de cross-validation con todo el dataset.

**Resolución**
Eso filtra información del test fold.
Debe ir dentro de pipeline + CV.

**Resultado:** procedimiento correcto = pipeline completo en cada fold.

### Ejercicio 3 (nested CV, concepto)
¿Por qué nested CV para tuning + evaluación final?

**Resolución**
Separa optimización de hiperparámetros (bucle interno) de estimación imparcial (externo).

**Resultado:** reduce optimismo en la métrica final.

---

## Mini checklist de uso rápido

1. Escribe la fórmula exacta antes de calcular.
2. Comprueba rangos (p.ej. métricas en \([0,1]\)).
3. Si hay empate/varias opciones, usa criterio explícito y justifícalo.
4. En kNN/k-means, piensa siempre en escalado de variables.
5. En evaluación, evita leakage (pipeline + CV).