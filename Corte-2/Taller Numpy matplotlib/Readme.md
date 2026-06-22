# Taller Práctico No. 4 — NumPy, Matplotlib y Seaborn

**Universidad del Pacífico — Programa de Ingeniería de Sistemas**
**Asignatura:** Inteligencia Artificial
**Docente:** Wilman Andrés Quiñonez V.
**Semestre 8 — Corte II**
**Caso de estudio desarrollado:** Caso 1 — Predicción de Rotación de Empleados en una Empresa Tecnológica

## Integrantes

* Ángel Santiago Estupiñán Gómez
* Stefany Potosí
* Cristian Valderrama
* Ewdar Suárez
* Steven Cabal

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1CkHBfeFXoJQpchnyxMgIgznmyYMT6XA_?usp=sharing)

## 1. Descripción general

Este repositorio contiene el desarrollo completo del Taller Práctico No. 4, el cual integra el uso de las librerías NumPy, Matplotlib y Seaborn dentro del flujo típico de un proyecto de Inteligencia Artificial: generación de datos sintéticos, cálculo de estadísticos descriptivos, visualización de datos y análisis exploratorio orientado a la toma de decisiones.

El trabajo se desarrolla en su totalidad dentro del notebook `taller4_caso1.ipynb`, ejecutable de inicio a fin en Jupyter Notebook o Google Colab, y se complementa con este documento README, que resume la metodología, los hallazgos y las conclusiones del ejercicio.

## 2. Introducción

La Inteligencia Artificial y el Aprendizaje Automático dependen, antes que de cualquier algoritmo de modelado, de un proceso riguroso de comprensión y exploración de los datos disponibles. NumPy, Matplotlib y Seaborn constituyen el conjunto de herramientas base del ecosistema científico de Python para llevar a cabo esta tarea: NumPy permite representar y operar eficientemente sobre estructuras numéricas multidimensionales, mientras que Matplotlib y Seaborn permiten traducir esos datos en representaciones visuales que facilitan la identificación de patrones, tendencias y relaciones no evidentes mediante la simple inspección de tablas.

El trabajo desarrolla, de manera integrada, las dos partes exigidas por la guía del taller: la investigación conceptual y los ejercicios guía de cada librería, y el caso de estudio integrador seleccionado por el equipo, sobre rotación de personal en una empresa tecnológica.

## 3. Objetivo general

Aplicar las librerías NumPy, Matplotlib y Seaborn al procesamiento, análisis estadístico y visualización de un conjunto de datos sintético sobre rotación de personal, con el fin de identificar patrones y relaciones entre variables que sustenten conclusiones y recomendaciones empresariales basadas en evidencia.

## 4. Objetivos específicos

1. Identificar el papel de NumPy, Matplotlib y Seaborn dentro del ecosistema de la Inteligencia Artificial, mediante el desarrollo de la investigación conceptual y los ejercicios guía propuestos en la Parte I del taller.
2. Generar y manipular, mediante NumPy, un dataset sintético de 500 empleados, calculando sobre él los estadísticos descriptivos requeridos (promedio salarial, edad promedio, desviación estándar de salarios y porcentaje de renuncia).
3. Construir, mediante Matplotlib, visualizaciones que permitan interpretar el comportamiento individual de las variables del caso de estudio (histograma de salarios, gráfico de barras de renuncias y gráfico de dispersión salario-satisfacción).
4. Aplicar, mediante Seaborn, técnicas de visualización estadística (heatmap de correlación, boxplot y pairplot) que permitan analizar distribuciones, correlaciones y relaciones entre las variables del caso de estudio.
5. Interpretar los resultados del análisis exploratorio para formular hallazgos, conclusiones, recomendaciones empresariales y una reflexión sobre el uso de Inteligencia Artificial en la automatización de la toma de decisiones de retención de personal.

## 5. Estructura del repositorio

```
taller_practico_librerias_numpy_matplotlib_seaborn/
├── taller4_caso1.ipynb   # Notebook con el desarrollo completo del taller
└── README.md             # Este documento
```

## 6. Procedimientos Realizados

Esta sección documenta, de manera detallada, los procedimientos seguidos en cada parte del notebook, en cumplimiento del requisito de explicar el desarrollo metodológico del taller.

### 6.1. Parte I — Investigación y ejercicios guía

**Investigación conceptual:** se respondieron, en prosa académica, las trece preguntas conceptuales planteadas en la guía sobre NumPy (definición, eficiencia frente a listas de Python, el objeto `ndarray`, su relación con el álgebra lineal y su uso en Deep Learning), Matplotlib (definición, tipos de gráficos, importancia de la visualización en IA y en el análisis exploratorio) y Seaborn (definición, ventajas frente a Matplotlib, mapas de calor y matrices de correlación).

**Ejercicios guía de NumPy:** se construyó una matriz de 3×3 con `np.array()` y se practicó la indexación bidimensional (`matriz[1,1]`, slicing de filas y columnas) para extraer el elemento central, la segunda fila y la tercera columna.

**Operaciones matemáticas:** sobre un arreglo de prueba se calcularon el promedio (`np.mean`), el máximo (`np.max`), el mínimo (`np.min`) y la desviación estándar (`np.std`), interpretando su significado estadístico.

**Generación de datos aleatorios:** se generaron 1.000 valores con `np.random.normal(loc=50, scale=10, size=1000)` y se visualizó su distribución mediante un histograma de Matplotlib, verificando que la media y la desviación muestral se aproximan a los parámetros teóricos.

**Visualizaciones guía:** se construyeron, de forma independiente a las del caso de estudio, un gráfico de líneas (accuracy por época con `plt.plot`), un histograma adicional, un gráfico de barras por clase (`plt.bar`), un heatmap de correlación sobre un DataFrame de ejemplo (`sns.heatmap`) y un boxplot (`sns.boxplot`), cada uno acompañado de su interpretación y de las preguntas de análisis solicitadas en la guía.

### 6.2. Parte II — Caso de estudio: rotación de empleados

**Contexto:** una empresa de desarrollo de software ha observado un aumento en la renuncia de empleados durante el último año. El área de Gestión Humana desea analizar los factores que podrían estar relacionados con la rotación del personal, con el fin de anticipar este fenómeno y diseñar estrategias de retención basadas en evidencia.

**Procedimiento de generación de datos sintéticos:** con semilla fija (`np.random.seed(42)`, para garantizar reproducibilidad), se generaron 500 registros mediante distintas distribuciones de NumPy ajustadas al significado de cada variable: `np.random.randint` para la edad (21 a 60 años), `np.random.normal` para el salario mensual (media $4.500.000, desviación $1.200.000, truncado en un piso de $1.800.000), `np.random.poisson` para las horas extras mensuales (media 8), `np.random.exponential` para la antigüedad (escala 4 años, truncada entre 0 y 25) y `np.random.randint` para la satisfacción (escala entera de 1 a 10). La variable Renunció no se generó de forma independiente: se construyó un modelo logístico (`logit` lineal sobre satisfacción, horas extras y antigüedad, transformado con la función sigmoide) que define la probabilidad de renuncia de cada empleado, y a partir de esa probabilidad se simuló el resultado binario con `np.random.rand`. Este diseño permite que el dataset contenga relaciones reales y verificables entre variables, en lugar de ruido puramente aleatorio.

**Procedimiento de análisis estadístico:** sobre el DataFrame resultante se calcularon, con funciones de NumPy, el promedio salarial (`np.mean`), la mediana salarial (`np.median`), la edad promedio, la desviación estándar de los salarios (`np.std`) y el porcentaje de empleados que renunciaron.

**Procedimiento de visualización:** se construyeron seis gráficos, tres con Matplotlib y tres con Seaborn, según lo exigido por la guía:

1. Histograma de salarios mensuales (`plt.hist`), con una línea vertical de referencia en el promedio.
2. Gráfico de barras de la distribución de renuncias (`plt.bar`), a partir del conteo de cada categoría con `value_counts()`.
3. Gráfico de dispersión entre salario y satisfacción (`plt.scatter`), coloreando los puntos según el estado de renuncia.
4. Mapa de calor de correlación (`sns.heatmap`) sobre las cinco variables numéricas y la renuncia codificada como variable binaria (0/1), lo que permite cuantificar su asociación con cada predictor mediante correlación punto-biserial.
5. Boxplot de salarios segmentado por estado de renuncia (`sns.boxplot`), para comparar medianas y dispersión entre ambos grupos.
6. Pairplot de todas las variables numéricas discriminado por color según la renuncia (`sns.pairplot`), para observar de forma conjunta las relaciones entre pares de variables.

Cada gráfico se acompaña, dentro del notebook, de su interpretación individual inmediatamente después de generarse.

**Procedimiento de análisis exploratorio:** a partir de los seis gráficos y de la matriz de correlación, se respondieron las preguntas de análisis de la guía (relación entre satisfacción y renuncia, entre horas extras y renuncia, y variable más influyente), se elaboró el informe ejecutivo solicitado como entregable, y se formularon las conclusiones, recomendaciones y la reflexión sobre Inteligencia Artificial que se documentan en las secciones siguientes.

## 7. Resultados Obtenidos

- La **satisfacción laboral** es, con amplio margen, la variable más asociada con la renuncia (correlación ≈ -0.35): los empleados con menores niveles de satisfacción presentan una probabilidad de renuncia notablemente mayor.
- La **antigüedad** actúa como factor protector moderado (correlación ≈ -0.13): a mayor tiempo en la empresa, menor probabilidad de renuncia.
- Las **horas extras**, el **salario** y la **edad** muestran correlaciones débiles con la renuncia (todas por debajo de 0.10 en valor absoluto) y no resultan determinantes de forma aislada en este conjunto de datos.
- No se identificó multicolinealidad relevante entre las variables predictoras analizadas.

## 8. Conclusiones

1. La satisfacción laboral es, con amplio margen, el factor más asociado con la decisión de renunciar (correlación ≈ -0.35), muy por encima de cualquier otra variable disponible.
2. La antigüedad en la empresa actúa como un factor protector moderado frente a la renuncia (correlación ≈ -0.13), consistente con dinámicas reales de permanencia y arraigo organizacional.
3. Las horas extras muestran una asociación débil con la renuncia (correlación ≈ 0.06) en este conjunto de datos, por lo que no deben asumirse como un factor determinante de forma aislada, aunque ameritan seguimiento preventivo.
4. El salario, de forma aislada, no constituye un predictor relevante de la rotación (correlación ≈ -0.07), por lo que las estrategias de retención centradas únicamente en ajustes salariales tendrían un impacto limitado.
5. El desbalance entre empleados que permanecen (77.8%) y empleados que renuncian (22.2%) debe considerarse al diseñar un futuro modelo predictivo, dado que podría requerir técnicas de balanceo de clases.

## 9. Recomendaciones empresariales

1. Priorizar la medición y el seguimiento de la satisfacción laboral (encuestas de clima organizacional), dado que es, con diferencia, el factor más asociado con la renuncia en este análisis.
2. Diseñar programas de acompañamiento para empleados de baja antigüedad, segmento con mayor propensión a la rotación según el análisis.
3. Mantener un monitoreo preventivo de las horas extras por empleado, aunque su asociación directa con la renuncia fue débil en esta muestra, dado que constituye un factor de riesgo razonable para el bienestar laboral.

## 10. Reflexión sobre Inteligencia Artificial

El análisis exploratorio desarrollado constituye la base para un futuro modelo de clasificación (regresión logística, árboles de decisión o random forest) entrenado principalmente sobre satisfacción y antigüedad —las variables con mayor poder explicativo identificado— para estimar la probabilidad de renuncia de cada empleado activo. Esto permitiría al área de Gestión Humana priorizar de forma objetiva sus acciones de retención, dirigiendo recursos hacia los colaboradores con mayor riesgo identificado, siempre bajo un uso ético y responsable de la información laboral.

## 11. Cómo ejecutar el notebook

1. Abrir `taller4_caso1.ipynb` en Jupyter Notebook o subirlo a Google Colab.
2. Instalar las dependencias si es necesario: `pip install numpy pandas matplotlib seaborn`.
3. Ejecutar todas las celdas en orden (`Run All`).

## 12. Autoría

Desarrollado por el equipo listado en la sección Integrantes, como entrega del Taller Práctico No. 4 de la asignatura Inteligencia Artificial, Semestre 8, Corte II, Universidad del Pacífico, Programa de Ingeniería de Sistemas, bajo la guía del docente Wilman Andrés Quiñonez V.
