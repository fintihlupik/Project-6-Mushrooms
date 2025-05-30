# 🍄 Mushroom Clustering and PCA Analysis
Proyecto de **Machine Learning No Supervisado** para identificación automática de setas comestibles vs. venenosas mediante clustering y PCA.

## 📋 Descripción
Análisis de un dataset de 8,124 setas utilizando técnicas de clustering para descubrir patrones naturales sin conocimiento previo de toxicidad. El objetivo es evaluar si es posible **identificar automáticamente setas peligrosas** usando solo características morfológicas.

## 💾 Dataset
**Fuente:** [UCI Mushroom Classification](https://www.kaggle.com/uciml/mushroom-classification)
- **8,124 setas** con 22 características categóricas (eliminada `veil-type`)
- **Variable objetivo:** comestible (edible) vs. venenosa (poisonous)
- **Balance:** 52% comestibles, 48% venenosas
- **Sin valores nulos** (excepto 30.5% en `stalk-root` tratado como categoría)

## 🛠️ Tecnologías
- **Python 3.12** + pandas, numpy, scikit-learn
- **PCA** - Reducción dimensional
- **K-Means** - Clustering no supervisado  
- **Random Forest** - Baseline supervisado
- **matplotlib/seaborn** - Visualización

## 📊 Resultados Principales

### PCA - Reducción Dimensional
- **95 → 5 variables** (95% reducción) manteniendo 99.4% precisión
- **Visualización 2D** con 31.1% varianza explicada
- **Separación clara** entre clases

### Clustering K-Means (K=2)
| Cluster | Comestibles | Venenosas | Pureza |
|---------|-------------|-----------|---------|
| 0 | 5 | 2,080 | **99.8%** |
| 1 | 2,825 | 533 | **84.1%** |

### Comparación de Métodos
| Método | Precisión | Información |
|--------|-----------|-------------|
| Random Forest | 100.0% | Con etiquetas |
| K-Means | ~90.1% | Sin etiquetas |

## 🎯 Hallazgos Clave
- **Separabilidad natural excepcional** - Características morfológicas permiten distinción automática
- **Estructura dimensional simple** - Solo 5 componentes contienen información discriminativa  
- **Clustering altamente efectivo** - 99.8% precisión identificando setas venenosas sin supervisión
- **Coincidencia biológica** - Clusters automáticos coinciden con taxonomía real

## 📱 Aplicaciones
- **Herramienta de campo** para identificación automática
- **Sistema de alerta** para micólogos
- **Clasificación preliminar** de especies desconocidas
- **Investigación botánica** para descubrimiento de patrones

## 📁 Estructura
```
├── workshop-clustering-pca.ipynb       # Notebook principal
├── data/mushrooms.csv                  # Dataset
└── README.md                          # Este archivo
```

## 🔍 Metodología
1. **Preprocesamiento** - Limpieza, One-Hot encoding, train/test split
2. **PCA** - Reducción dimensional y visualización  
3. **Clustering** - K-Means con método del codo
4. **Evaluación** - Pureza de clusters y comparación supervisada

---
**Resultado:** El clustering no supervisado demostró ser altamente efectivo para identificar setas peligrosas, ofreciendo una herramienta valiosa para seguridad alimentaria.
