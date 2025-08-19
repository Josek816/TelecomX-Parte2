# 📊 TelecomX – Predicción de Churn (Parte 2)

## 🎯 Propósito del análisis
El objetivo principal de este proyecto es predecir la cancelación de clientes (churn) en TelecomX, usando variables relevantes.  
Esto permite anticipar bajas, aplicar estrategias de retención y mejorar la satisfacción del cliente.

---

## 📂 Estructura del proyecto
TelecomX-Parte2/
- notebook_principal.ipynb   -> Cuaderno con EDA, preprocesamiento, modelos y evaluación
- data/
    - datos_originales.csv    -> Dataset inicial
    - datos_tratados.csv      -> Dataset limpio y transformado
    - datos_listos_modelo.csv -> Dataset final en formato numérico
- visualizaciones/
    - correlacion.png
    - boxplot_contrato.png
    - scatter_factura.png
    - matrices_confusion.png
- README.md                  -> Documentación del proyecto
- requirements.txt           -> Dependencias necesarias

---

## 🧹 Preparación de datos
1. Clasificación de variables:
   - Categóricas: Género, Método de pago, Tipo de contrato, Servicios de internet y telefonía.
   - Numéricas: MesesCliente, FacturaMensual, FacturaTotal, FacturaDiaria.

2. Transformaciones:
   - Eliminación de columnas irrelevantes (customerID).
   - Conversión de variables booleanas a 0/1.
   - Codificación de variables categóricas con One-Hot Encoding.
   - Normalización de variables para modelos basados en distancia.

3. Separación en entrenamiento y prueba:
   - División 70/30 estratificada (train_test_split).

4. Justificación de decisiones:
   - Se usó SMOTE para balancear las clases.
   - Normalización solo en modelos sensibles a la escala (Logística, KNN).
   - Árboles (Random Forest) no requieren normalización.

---

## 📊 Exploración y hallazgos (EDA)
Ejemplos de gráficos:
- Matriz de correlación.
- Boxplot: Contrato vs Cancelación.
- Scatter: Factura vs Cancelación.
- Matrices de confusión de los modelos.

Insights clave:
- Contrato mensual incrementa riesgo de cancelación.
- Clientes con baja antigüedad cancelan más.
- Método de pago electronic check está más asociado a churn.
- Facturas altas aumentan la probabilidad de abandono.
- Servicios adicionales de internet ayudan a retener clientes.

---

## 🤖 Modelos utilizados
- Regresión Logística (con normalización): baseline interpretable.
- Random Forest (sin normalización): mayor desempeño y mejor recall.

---

## ▶️ Instrucciones de ejecución
1. Instalar dependencias:
pip install -r requirements.txt

2. Cargar el dataset:
import pandas as pd
df = pd.read_csv("data/datos_listos_modelo.csv")

3. Ejecutar el cuaderno notebook_principal.ipynb.

---

## ✅ Conclusión
Este análisis demuestra que el churn está relacionado principalmente con el tipo de contrato, la antigüedad del cliente, el método de pago y la factura mensual.  
El modelo permite anticipar qué clientes están en mayor riesgo y orientar campañas de retención más efectivas.
