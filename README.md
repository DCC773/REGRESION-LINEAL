# 📈 Estimación de Parámetros Económicos con Gradiente Descendente  
## Modelo Keynesiano de Consumo

## 1. Introducción
Este proyecto aplica el **algoritmo de gradiente descendente** para estimar los parámetros de un modelo económico clásico, específicamente el **modelo keynesiano de consumo**, en el cual el consumo privado depende del ingreso disponible.

Se utilizan **datos reales del Banco Central de Reserva del Perú (BCRP)** para el período **2000–2024**, con el objetivo de ilustrar cómo técnicas de optimización y aprendizaje automático pueden emplearse en el análisis económico aplicado.

---

## 2. Objetivo
Aplicar el método de **gradiente descendente** para estimar los parámetros del siguiente modelo lineal de consumo:

\[
C = c_0 + c \cdot YD
\]

donde:

- **C**: Consumo privado  
- **YD**: Ingreso nacional disponible  
- **c₀**: Consumo autónomo (intercepto)  
- **c**: Propensión marginal a consumir (pendiente)

---

## 3. Fundamento Teórico
El **gradiente descendente** es un algoritmo de optimización que busca minimizar una función de costo mediante actualizaciones iterativas de los parámetros del modelo.

En este caso, la función de costo utilizada es el **Error Cuadrático Medio (MSE)** entre los valores reales y los valores predichos del consumo. Los coeficientes del modelo se ajustan utilizando las **derivadas parciales del MSE** con respecto a cada parámetro, permitiendo converger hacia los valores que minimizan el error.

---

## 4. Datos Reales
Los datos corresponden a:

- **Consumo privado**
- **Ingreso nacional disponible**

para el Perú, proporcionados por el **BCRP**, en el período **2000–2024**, expresados en **millones de soles constantes de 2007**.

Previo a la estimación, los datos son **cargados y normalizados**, lo que facilita la convergencia del algoritmo de gradiente descendente.

---

## 5. Implementación del Modelo con Gradiente Descendente
El modelo se implementa en **Python**, utilizando principalmente las bibliotecas:

- `numpy`
- `sklearn` (para la normalización de los datos)

### ⚙️ Configuración del algoritmo
- Parámetros iniciales:
  - `m`: pendiente (propensión marginal a consumir)
  - `b`: intercepto (consumo autónomo)
- Tasa de aprendizaje (`alpha`)
- Número de épocas

En cada iteración, el algoritmo:
1. Calcula las predicciones del consumo.
2. Evalúa el MSE.
3. Calcula las derivadas parciales del error con respecto a `m` y `b`.
4. Actualiza los parámetros hasta alcanzar la convergencia.

### 📊 Resultados de la estimación
- **Propensión marginal a consumir (c)**: ≈ **0.996**
- **Consumo autónomo estimado (c₀ normalizado)**: ≈ **0.0**
- **Error final (MSE)**: ≈ **0.00799**

La estimación muestra que por cada sol adicional de ingreso disponible, las familias consumen aproximadamente **S/ 0.996**, lo que refleja una **muy baja propensión al ahorro**. El consumo autónomo cercano a cero se explica por la normalización de los datos y no necesariamente representa su valor real en niveles.

El bajo valor del MSE indica un **excelente ajuste del modelo** a los datos observados.

---

## 6. Visualización de Resultados

### a) Evolución del Error
Se grafica la convergencia del **Error Cuadrático Medio (MSE)** a lo largo de las épocas, mostrando cómo el gradiente descendente reduce progresivamente el error hasta estabilizarse.

### b) Ajuste del Modelo: Valores Reales vs. Predichos
Se presenta un gráfico de dispersión que compara el consumo real con el consumo estimado por el modelo, evidenciando un ajuste muy cercano a la línea de 45°.

- **Coeficiente de Determinación (R²)**: **0.9920**

---

## 7. Conclusión
El modelo keynesiano estimado mediante gradiente descendente demuestra que el **consumo privado en el Perú está fuertemente determinado por el ingreso disponible**.

Una propensión marginal a consumir de **0.996** sugiere que la mayor parte del ingreso adicional se destina al consumo. Asimismo, un **R² de 0.992** indica que el modelo explica aproximadamente el **99.2% de la variabilidad del consumo**, confirmando la solidez empírica del enfoque keynesiano para el período analizado.

---

## ▶️ Uso
Para reproducir el análisis:

1. Clona el repositorio.
2. Abre el cuaderno de **Jupyter Notebook** o **Google Colab**.
3. Ejecuta las celdas en orden para replicar la estimación y las visualizaciones.

---
