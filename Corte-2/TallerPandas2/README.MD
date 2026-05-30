<a href="https://colab.research.google.com/drive/1_g4k5Kx2KBMYZFfigOTiRnOY7V37MM2a#scrollTo=M2IwYwPV9d7C"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>

# Programa de Ingeneria en Sistemas

<div style="display: flex; justify-content: space-between; align-items: center;">
  <img src="https://github.com/wilmanAQ/Inteligencia_Artificial/blob/IA/icono_unipacifico.jpeg?raw=1" width="100" alt="Icono UniPacífico">
  <img src="https://github.com/wilmanAQ/Inteligencia_Artificial/blob/IA/icono_PIS.png?raw=1" width="270" alt="Icono PIS">
</div>

## **Taller Práctico de Pandas y Operaciones Matemáticas**

### **Asignatura:** Inteligencia Artificial - Corte II

**Grupo:** IS08N1.

**Integrantes:**<br/>
Jhon Edwar Suarez Quiñonez <br/>
Cristian David Garcia Valderrama<br/>
Stefany Potosi<br/>
Santiago Estupiñan<br/>

## **Objetivo de este taller:**

Aplicar conceptos fundamentales de análisis de datos utilizando la librería Pandas en Python, realizando operaciones matemáticas, estadísticas y manipulación de columnas.

## Archivos del trabajo

- Notebook del taller: [Taller2_Pandas.ipynb](Taller2_Pandas.ipynb)
- Dataset utilizado: [productos.csv](productos.csv)

## Dataset base

El taller utiliza un conjunto de datos de productos tecnológicos y de oficina con columnas como:

- Producto
- Precio
- Cantidad
- Costo_Envio
- Categoría

El archivo [productos.csv](productos.csv) contiene los datos base para desarrollar el ejercicio.

## Actividades realizadas

### 1. Creación y exploración del DataFrame

- Crear el DataFrame con Pandas.
- Mostrar las primeras filas y las últimas filas.
- Verificar los tipos de datos de cada columna.
- Consultar el tamaño del DataFrame.
- Obtener un resumen estadístico general.

### 2. Operaciones matemáticas entre columnas

- Crear la columna **Total_Venta = Precio \* Cantidad**.
- Crear la columna **Costo_Total = Total_Venta + Costo_Envio**.
- Calcular el promedio de **Total_Venta**.
- Identificar el producto con mayor y menor **Total_Venta**.

### 3. Porcentajes y análisis

- Crear la columna **IVA** con el 19% del total de ventas.
- Crear la columna **Ganancia_Estimada** con el 25% de **Total_Venta**.
- Crear la columna **Perdida_Estimada** con el 0.05% de **Total_Venta**.
- Calcular el porcentaje de ventas de cada producto.
- Filtrar productos con porcentaje superior al 15%.

### 4. Estadística descriptiva

- Calcular media, mediana y moda de la columna **Precio**.
- Calcular la desviación estándar de **Cantidad**.
- Hallar el valor máximo y mínimo de **Total_Venta**.
- Interpretar los resultados obtenidos.

### 5. Filtrado y ordenamiento

- Mostrar únicamente los productos de la categoría **Tecnología**.
- Ordenar los productos de mayor a menor según **Total_Venta**.

### 6. Trabajo adicional (opcional)

- Investigar cómo exportar el DataFrame final a Excel (**.xlsx**).
- Realizar la exportación si se solicita.

## Resultados esperados

El trabajo debe dejar evidencia de:

- La manipulación de datos con Pandas.
- El cálculo de métricas comerciales y estadísticas.
- Un análisis organizado y documentado del dataset.
- La entrega del notebook y del material del taller en el repositorio.
