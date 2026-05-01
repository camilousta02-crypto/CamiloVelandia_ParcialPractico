# Detección de Fraude Bancario - Parcial Práctico

**Estudiante:** Camilo Velandia  
**Universidad:** Universidad Santo Tomás  
**Programa:** Estadística  
**Periodo:** 2026-I  
**Modelo asignado:** AdaBoost (scikit-learn)

---

## 📋 Descripción del Proyecto

Construcción de un sistema automatizado de Machine Learning para detectar transacciones bancarias fraudulentas en un dataset altamente desbalanceado (~0.17% de fraudes). Se comparan 3 modelos y se entregan predicciones para evaluación tipo competencia.

### Dataset
| Archivo | Filas | Descripción |
|---------|-------|-------------|
| train.csv | 199,364 | Datos de entrenamiento con labels (Class) |
| test.csv | 42,720 | Datos de prueba sin labels (predicciones) |
| sample_submission.csv | 42,720 | Formato de entrega esperado |

### Variables
- **Time:** Segundos transcurridos desde la primera transacción
- **V1 - V28:** Features numéricas resultado de PCA (anonimizadas)
- **Amount:** Monto de la transacción
- **Class:** Target binario (0 = normal, 1 = fraude)

---

## 🗂️ Estructura del Repositorio
CamiloVelandia_ParcialPractico/
├── notebooks/
│   └── parcial_CamiloVelandia.ipynb    # Notebook completo con EDA + 3 modelos
├── docker/
│   ├── Dockerfile                      # Imagen Docker con PySpark
│   └── docker-compose.yml              # Orquestación del contenedor
├── data/
│   ├── train.csv                       # Datos de entrenamiento
│   ├── test.csv                        # Datos de prueba
│   └── sample_submission.csv           # Ejemplo de formato
├── submission.csv                        # Predicciones del MEJOR modelo (GBT)
├── reporte.pdf                         # Reporte de 1 página máximo
└── README.md                           # Este archivo


## Cómo ejecutar
1. Clonar repositorio
2. `cd docker && docker-compose up -d`
3. Abrir Jupyter en `http://localhost:8888`
4. Ejecutar `notebooks/parcial_CamiloVelandia.ipynb`

## Semilla utilizada
**7273** (últimos 4 dígitos de cédula)

## Resultados
| Modelo | F1-Score | Framework |
|--------|----------|-----------|
| Logistic Regression | 0.9936 | PySpark |
| GBT | **0.9994** | PySpark |
| AdaBoost | 0.8636 | scikit-learn |

**Mejor modelo:** GBT (Gradient Boosted Trees)