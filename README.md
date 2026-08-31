# Predicción de Incumplimiento Crediticio

Proyecto ABP desarrollado para la materia **Ciencia de Datos II - Estadística y Exploración de Datos II**, Módulo Analista de Datos II, de la **Tecnicatura Superior en Ciencia de Datos e Inteligencia Artificial** - Instituto Superior Politécnico de Córdoba (ISPC).

## Descripción del problema

Las entidades financieras necesitan tomar decisiones de otorgamiento de crédito reduciendo el riesgo de pérdidas económicas. Este proyecto desarrolla una **Prueba de Concepto (PoC)** para estimar la probabilidad de que un solicitante de crédito incumpla sus pagos, utilizando un modelo de **regresión logística**.

**Pregunta de negocio:** ¿cómo podemos identificar anticipadamente clientes con mayor probabilidad de incumplir un crédito para mejorar la toma de decisiones del área de riesgo financiero?

## Dataset

[Home Credit Default Risk](https://www.kaggle.com/c/home-credit-default-risk) (Kaggle, 2018). Se utiliza únicamente el archivo `application_train.csv`, que contiene información demográfica, laboral, económica y del préstamo solicitado, junto con la variable objetivo `TARGET` (0 = cliente cumplidor, 1 = default).

## Estado del proyecto

| Evidencia | Contenido | Estado |
|---|---|---|
| **Evidencia 1** | Comprensión del negocio, comprensión del dataset y análisis exploratorio (EDA) | ✅ Completa |
| **Evidencia 2** | Ingeniería de características y preparación del dataset | ⏳ Pendiente |
| **Evidencia 3** | Modelo baseline y desarrollo de la solución | ⏳ Pendiente |

## Contenido de la Evidencia 1

- **Comprensión del negocio:** contexto financiero, necesidad del stakeholder (Área de Riesgo Financiero) y Marco de Valor Esperado (costo de falsos negativos vs. falsos positivos).
- **Comprensión del dataset:** inventario estructural (307.511 filas × 122 columnas), separación estratificada de train/test, diccionario de variables agrupado en 10 bloques temáticos, análisis de valores faltantes y distribución de la variable objetivo (desbalance de clases ~92% / ~8%).
- **Análisis Exploratorio de Datos (EDA):** distribuciones, relación de cada variable con `TARGET`, análisis de correlaciones y detección de multicolinealidad, y recopilación de problemas de calidad de datos a resolver en la próxima etapa (valores centinela, nulos no aleatorios, outliers, variables redundantes).

### Principales hallazgos

- Fuerte desbalance de clases (11 clientes cumplidores por cada 1 en default), lo que descarta el *accuracy* como métrica principal de evaluación.
- Los **scores externos** (`EXT_SOURCE_1/2/3`) son las variables con mayor relación con el riesgo, aunque también las que más datos faltantes tienen.
- La **edad** y la **antigüedad laboral** muestran una relación clara e inversa con el riesgo de incumplimiento.
- El **perfil socioeconómico** (educación, tipo de ingreso, ocupación) genera diferencias de hasta 6 veces en la tasa de default entre categorías.
- Se detectaron problemas de calidad de datos a resolver antes de modelar: un valor centinela en `DAYS_EMPLOYED`, redundancia masiva en el bloque de variables de vivienda (63 pares de variables con correlación > 0.90), y variables casi constantes sin poder predictivo.

## Notebook

📓 [Ver notebook en Google Colab] (https://colab.research.google.com/drive/1sosXUNJGE3o1gIdj4cum1IeWOeyv1bbP?usp=sharing)

## Estructura del repositorio

```
├── Modulo_Analista.ipynb          # Notebook con el desarrollo completo del EDA
├── Grupo 7 - Entregables, Evidencia 1.pdf       # Entrega: portada + informe ejecutivo + anexo técnico + recursos digitales
└── README.md
```

## Tecnologías utilizadas

- Python (pandas, numpy)
- Visualización: matplotlib, seaborn
- Entorno: Google Colab

## Integrantes

- Negro, Clarisa
- Verdú, Lucía
- Pucheta, Matías
- Virga, Camila

## Docentes

Barbero, Maciel y Pratta, Nahuel


