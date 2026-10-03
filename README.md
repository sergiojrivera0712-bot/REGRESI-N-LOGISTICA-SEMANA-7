# Regresión Logística – Riesgo de impago en solicitudes de crédito

Ejercicio aplicado de **Regresión Logística** para el CADI de Big Data, Universidad de Cundinamarca.

**Autor:** Jonnathan Pazos

## Problema

Predecir si un cliente que solicita un crédito va a **incumplir el pago** (1) o **pagar** (0), a partir de la información de su solicitud: edad, ingresos, gastos, tipo de trabajo, vivienda, antecedentes, monto solicitado, etc.

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `RegresionLogistica_RiesgoCredito.ipynb` | Notebook de Google Colab con todo el ejercicio (código comentado, gráficos y conclusiones) |
| `CreditScoring.csv` | Datos originales (4.455 solicitudes, 14 variables) |

## Cómo ejecutarlo

1. Abrir el notebook en Google Colab (botón *Open in Colab* de GitHub o `Archivo > Abrir cuaderno > GitHub`).
2. `Entorno de ejecución > Ejecutar todas`.

Los datos se cargan desde internet automáticamente. Si no hay conexión, se puede subir `CreditScoring.csv` a la sesión de Colab.

## Proceso

1. Planteamiento del problema y justificación del modelo
2. Descripción de los datos y de la variable objetivo
3. Exploración (distribución de clases, tasas de incumplimiento por grupo)
4. Preparación: faltantes codificados, decodificación de categóricas, variable nueva (% de financiación), imputación, one-hot y escalado dentro de un `Pipeline`
5. División 80/20 estratificada
6. Modelo `LogisticRegression` de scikit-learn
7. Predicciones con `predict()` y `predict_proba()`
8. Evaluación: accuracy, matriz de confusión, precision, recall, F1 y AUC-ROC
9. Ajuste del umbral de decisión
10. Interpretación de coeficientes como odds ratios
11. Análisis de errores y conclusiones

## Resultados principales (conjunto de prueba)

| Métrica | Umbral 0.5 | Umbral 0.35 |
|---|---|---|
| Accuracy | 0.827 | 0.796 |
| Precision (incumple) | 0.754 | 0.619 |
| Recall (incumple) | 0.574 | 0.717 |
| F1-score (incumple) | 0.652 | 0.664 |

AUC-ROC: 0.842

## Librerías

Pandas, NumPy, Matplotlib y Scikit-learn.

## Fuente de los datos

Sánchez, G. (2012). *CreditScoring*. GitHub: https://github.com/gastonstat/CreditScoring (datos del curso de minería de datos de Tomàs Aluja, Universitat Politècnica de Catalunya).
