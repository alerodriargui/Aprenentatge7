# MUSI — Ejercicios resueltos por tema (Dr. Alberto Ortiz Rodríguez)

Formato: ejercicios lógicos de **aplicar fórmula** (estilo examen).

---

## Tema 3.1 — Clasificación Bayesiana y lineal

### Ejercicio 1 (Bayes 2 clases)
Se tiene un problema binario con:
- \(P(\omega_1)=0.6\), \(P(\omega_2)=0.4\)
- \(p(x|\omega_1)=0.20\), \(p(x|\omega_2)=0.50\)

Decidir la clase de \(x\).

**Resolución**
Regla MAP: elegir clase con mayor \(P(\omega_i|x) \propto p(x|\omega_i)P(\omega_i)\).
- \(g_1=0.20\cdot 0.6=0.12\)
- \(g_2=0.50\cdot 0.4=0.20\)

Como \(g_2>g_1\), se asigna a \(\omega_2\).

**Resultado:** \(x\in\omega_2\).

### Ejercicio 2 (frontera lineal)
Se usa el discriminante lineal \(g(x)=w^Tx+w_0\), con \(w=(2,-1)\), \(w_0=-1\).
Clasificar \(x=(1,1)\) y \(x=(3,1)\).

**Resolución**
- Para \((1,1)\): \(g=2\cdot1-1\cdot1-1=0\) (sobre frontera)
- Para \((3,1)\): \(g=2\cdot3-1\cdot1-1=4>0\)

Regla: \(g(x)>0\Rightarrow\omega_1\), \(g(x)<0\Rightarrow\omega_2\).

**Resultado:** \((1,1)\) en la frontera; \((3,1)\in\omega_1\).

---

## Tema 3.2 — Regresión lineal

### Ejercicio 1 (recta por mínimos cuadrados)
Datos: \((x,y)=\{(1,2),(2,3),(3,5),(4,4)\}\).
Calcular \(\hat y=b_0+b_1x\).

**Resolución**
\[
\bar x=2.5,\quad \bar y=3.5
\]
\[
S_{xy}=\sum (x_i-\bar x)(y_i-\bar y)=4,
\quad S_{xx}=\sum (x_i-\bar x)^2=5
\]
\[
\hat b_1=S_{xy}/S_{xx}=0.8,
\quad \hat b_0=\bar y-\hat b_1\bar x=1.5
\]

**Modelo:** \(\hat y=1.5+0.8x\).

### Ejercicio 2 (RSS y \(R^2\))
Con el modelo anterior, calcular RSS y \(R^2\).

**Resolución**
Predicciones: \(\hat y=[2.3,3.1,3.9,4.7]\).
Errores: \([-0.3,-0.1,1.1,-0.7]\).
\[
RSS=\sum (y_i-\hat y_i)^2=0.09+0.01+1.21+0.49=1.80
\]
\[
TSS=\sum (y_i-\bar y)^2=5,
\quad R^2=1-RSS/TSS=1-1.8/5=0.64
\]

**Resultado:** \(RSS=1.80\), \(R^2=0.64\).

---

## Tema 3.3 — Árboles de decisión y ensembles

### Ejercicio 1 (entropía de nodo)
Nodo con 10 muestras: 6 de clase A, 4 de clase B.
Calcular entropía.

**Resolución**
\[
p_A=0.6,\ p_B=0.4,
\quad H=-\sum p_i\log_2 p_i
\]
\[
H=-(0.6\log_2 0.6+0.4\log_2 0.4)\approx 0.971
\]

**Resultado:** \(H\approx 0.971\) bits.

### Ejercicio 2 (Gini antes y después de split)
Nodo padre: 10 muestras (6A,4B).
Split en:
- Hijo 1: 5 muestras (4A,1B)
- Hijo 2: 5 muestras (2A,3B)

Calcular mejora por Gini.

**Resolución**
\[
G_{padre}=1-(0.6^2+0.4^2)=0.48
\]
\[
G_1=1-(0.8^2+0.2^2)=0.32,
\quad G_2=1-(0.4^2+0.6^2)=0.48
\]
Gini ponderado tras split:
\[
G_{split}=\tfrac{5}{10}0.32+\tfrac{5}{10}0.48=0.40
\]
Ganancia:
\[
\Delta G=0.48-0.40=0.08
\]

**Resultado:** mejora de impureza \(0.08\).

---

## Tema 4.2 — SVM

### Ejercicio 1 (margen geométrico)
Hiperplano \(w^Tx+w_0=0\), con \(w=(3,4)\).
Calcular ancho del margen \(2/\|w\|\).

**Resolución**
\[
\|w\|=\sqrt{3^2+4^2}=5,
\quad \text{margen}=2/5=0.4
\]

**Resultado:** ancho de margen \(0.4\).

### Ejercicio 2 (clasificación con SVM lineal)
Modelo: \(g(x)=w^Tx+w_0\), \(w=(1,-2)\), \(w_0=0.5\).
Clasificar \(x=(2,0)\), \(x=(0,1)\).

**Resolución**
- \(g(2,0)=1\cdot2-2\cdot0+0.5=2.5>0\)
- \(g(0,1)=0-2+0.5=-1.5<0\)

**Resultado:** primer punto clase positiva, segundo clase negativa.

---

## Tema 4.3 — k-NN

### Ejercicio 1 (k=3 con distancia euclídea)
Datos etiquetados:
- A: \((1,1),(2,1),(1,2)\)
- B: \((4,4),(5,4),(4,5)\)
Clasificar \(q=(2,2)\) con \(k=3\).

**Resolución**
Distancias a A:
- \(d((2,2),(1,1))=\sqrt2\)
- \(d((2,2),(2,1))=1\)
- \(d((2,2),(1,2))=1\)

Distancias a B (todas > 2.8 aprox).
Los 3 vecinos más cercanos son de A.

**Resultado:** \(q\) se clasifica como **A**.

### Ejercicio 2 (k par y desempate por distancia)
Con \(k=4\), vecinos de \(q\):
- Clase A a distancias: 1.0, 2.0
- Clase B a distancias: 1.1, 1.2

Votos: 2 vs 2.

**Resolución**
Desempate por suma de distancias:
- A: \(1.0+2.0=3.0\)
- B: \(1.1+1.2=2.3\)

**Resultado:** gana clase **B** (más cercana en conjunto).

---

## Tema 5.2 — Clustering jerárquico

### Ejercicio 1 (single-link)
Distancias entre puntos \(x_1,x_2,x_3\):
- \(d_{12}=2\), \(d_{13}=5\), \(d_{23}=3\)

Aplicar single-link y dar primer merge.

**Resolución**
En single-link se fusiona el par con menor distancia.
Mínima distancia: \(d_{12}=2\).

**Resultado:** primer clúster \(\{x_1,x_2\}\).

### Ejercicio 2 (complete-link entre clústeres)
Sea \(C_A=\{x_1,x_2\}\), \(C_B=\{x_3,x_4\}\) con:
\(d_{13}=4, d_{14}=7, d_{23}=5, d_{24}=6\).

**Resolución**
Complete-link:
\[
d(C_A,C_B)=\max\{4,7,5,6\}=7
\]

**Resultado:** distancia complete-link = 7.

---

## Tema 5.3 — Clustering por optimización (k-means)

### Ejercicio 1 (asignación a centroides)
Centroides iniciales: \(\mu_1=(1,1)\), \(\mu_2=(5,5)\).
Puntos: \((2,1),(4,5),(5,4)\).

**Resolución**
Comparando distancia euclídea al cuadrado:
- \((2,1)\): a \(\mu_1\)=1, a \(\mu_2\)=25 \(\Rightarrow C_1\)
- \((4,5)\): a \(\mu_1\)=25, a \(\mu_2\)=1 \(\Rightarrow C_2\)
- \((5,4)\): a \(\mu_1\)=25, a \(\mu_2\)=1 \(\Rightarrow C_2\)

**Resultado:** \(C_1=\{(2,1)\}\), \(C_2=\{(4,5),(5,4)\}\).

### Ejercicio 2 (actualización de centroides)
Con los clústeres anteriores, recalcular centroides.

**Resolución**
\[
\mu_1'=\frac{(2,1)}{1}=(2,1)
\]
\[
\mu_2'=\frac{(4,5)+(5,4)}{2}=(4.5,4.5)
\]

**Resultado:** nuevos centroides \(\mu_1'=(2,1)\), \(\mu_2'=(4.5,4.5)\).

---

## Tema 6a — Evaluación de modelos supervisados

### Ejercicio 1 (Precision, Recall, F1)
Matriz de confusión binaria:
- TP=42, FP=8, FN=18, TN=32

**Resolución**
\[
P=\frac{TP}{TP+FP}=\frac{42}{50}=0.84
\]
\[
R=\frac{TP}{TP+FN}=\frac{42}{60}=0.70
\]
\[
F1=\frac{2PR}{P+R}=\frac{2\cdot0.84\cdot0.70}{0.84+0.70}=0.764
\]

**Resultado:** \(P=0.84\), \(R=0.70\), \(F1\approx0.764\).

### Ejercicio 2 (FPR y TPR para ROC)
Con los mismos datos:
\[
FPR=\frac{FP}{FP+TN}=\frac{8}{40}=0.20,
\quad TPR=R=0.70
\]

**Resultado:** punto ROC \((0.20,0.70)\).

---

## Tema 6b — Validez de clustering

### Ejercicio 1 (Silhouette de una muestra)
Para una muestra \(x\):
- distancia media intra-clúster \(a(x)=2.0\)
- mejor distancia media al clúster vecino \(b(x)=5.0\)

**Resolución**
\[
s(x)=\frac{b-a}{\max(a,b)}=\frac{5-2}{5}=0.6
\]

**Resultado:** silhouette de \(x\) = 0.6 (buena separación).

### Ejercicio 2 (método del codo)
WCSS para \(k=1..5\): \([500,260,180,150,140]\).

**Resolución**
Descensos:
- \(1\to2\): 240
- \(2\to3\): 80
- \(3\to4\): 30
- \(4\to5\): 10

El cambio fuerte se frena a partir de \(k=3\).

**Resultado:** codo en \(k\approx3\).

---

## Tema 6c — Preprocesado, tuning y evaluación (GridSearch)

### Ejercicio 1 (selección por validación cruzada)
Se prueban parámetros de SVM (CV media):
- C=0.1, gamma=0.1 \(\Rightarrow\) 0.84
- C=1, gamma=0.1 \(\Rightarrow\) 0.89
- C=10, gamma=0.01 \(\Rightarrow\) 0.87

**Resolución**
Se escoge la combinación con mayor score CV medio.

**Resultado:** mejor \((C=1, \gamma=0.1)\).

### Ejercicio 2 (evitar fuga de datos)
Se quiere normalizar y clasificar con CV.
Opciones:
1) escalar todo el dataset y luego CV
2) usar pipeline (Scaler + modelo) dentro de CV

**Resolución**
La opción 1 fuga información del test fold al train fold.
La opción 2 ajusta el escalado solo con train en cada fold.

**Resultado:** correcta la opción **2**.

---

## Checklist rápido para examen (estilo del profesor)

1. Identifica qué te piden (clase, métrica, \(k\), parámetro, etc.).
2. Escribe primero la fórmula exacta.
3. Sustituye con orden (sin saltarte unidades/definiciones).
4. Haz una comprobación lógica final (rango de valores: p.ej. \(0\le F1\le1\)).
5. Si comparas modelos, decide por **criterio explícito** (menor error / mayor score).

---

Si quieres, en el siguiente paso te preparo un **simulacro de examen completo de MUSI (90 min)** con plantilla de corrección y nota estimada.