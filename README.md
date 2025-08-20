# 📡 TelecomX LATAM - Análisis de Churn  

Este proyecto corresponde al **Challenge 2 de Data Science en Alura Latam**, cuyo objetivo es **analizar la evasión de clientes (Churn) en la empresa ficticia TelecomX LATAM**.  

El análisis busca identificar **factores asociados al abandono de clientes** y proponer **acciones estratégicas** para mejorar la retención.  

---

## 🎯 Propósito del Análisis  

- Comprender el comportamiento de los clientes que abandonan la compañía.  
- Detectar patrones en las variables de contrato, servicios y métodos de pago.  
- Identificar los segmentos con mayor probabilidad de churn.  
- Generar recomendaciones para **estrategias de retención** y reducción de pérdidas.  

---

## 📂 Estructura del Proyecto  

El notebook sigue la metodología **ETL + análisis exploratorio**:  

1. **📌 Extracción**  
   - Carga de datos desde un archivo JSON alojado en GitHub.  
   - Conversión a un `DataFrame` con Pandas.  

2. **🔧 Transformación**  
   - Limpieza de datos: tratamiento de valores nulos y conversiones numéricas.  
   - Normalización de categorías y revisión de inconsistencias.  

3. **📊 Análisis Exploratorio**  
   - Distribución de la variable `Churn`.  
   - Relación de churn con variables categóricas (contrato, método de pago, internet).  
   - Comparación de variables numéricas (`tenure`, `MonthlyCharges`, `TotalCharges`).  

4. **📄 Informe Final**  
   - Insights clave sobre los factores que influyen en el churn.  
   - Recomendaciones de negocio para la retención de clientes.  

---

## 📈 Ejemplos de Gráficos e Insights  

- **Distribución de Churn**  
  > Se observa un fuerte desbalance: la mayoría de clientes **no hacen churn**, pero el grupo que sí lo hace presenta patrones comunes.  

- **Tipo de contrato**  
  > Los clientes con contrato **Month-to-Month** tienen una tasa de churn significativamente más alta.  

- **Método de pago**  
  > Los clientes que usan **Electronic check** presentan mayor evasión que quienes usan transferencia bancaria o tarjeta.  

- **Servicios de internet**  
  > Los clientes con **Fibra Óptica** muestran más churn que los que tienen DSL.  

- **Antigüedad (Tenure)**  
  > Los clientes con poca antigüedad son los más propensos a abandonar la compañía.  

*(En el notebook encontrarás los gráficos generados con Seaborn y Matplotlib, incluyendo countplots, boxplots y comparaciones de distribución).*  

---

## ⚙️ Ejecución en Google Colab  

### 1️⃣ Abrir el notebook en Colab  
- Ve a [Google Colab](https://colab.research.google.com/).  
- Sube el archivo:
```bash
TelecomX_LATAM (1).ipynb
```

### 2️⃣ Instalar dependencias necesarias  
Ejecuta en una celda de Colab:  
```python
!pip install pandas numpy seaborn matplotlib requests
```
### 3️⃣ Ejecutar las celdas en orden

* El dataset se descarga automáticamente desde GitHub mediante requests.

* Los gráficos se mostrarán directamente en el notebook.

## 📦 Dependencias

* pandas → Manipulación de datos.

* numpy → Operaciones numéricas.

* seaborn → Visualizaciones estadísticas.

* matplotlib → Gráficos y boxplots.

* requests → Descarga de datos desde API/URL.

## 🛠️ Posibles Problemas y Soluciones

| Problema                                    | Causa                              | Solución                                                         |
| ------------------------------------------- | ---------------------------------- | ---------------------------------------------------------------- |
| ❌ Error al descargar datos (`requests.get`) | URL caída o sin internet           | Verificar conexión o actualizar la URL del JSON en GitHub        |
| ❌ `ModuleNotFoundError`                     | Librerías no instaladas            | Ejecutar `!pip install pandas numpy seaborn matplotlib requests` |
| ❌ Gráficos no aparecen en Colab             | Problemas de renderizado           | Asegurar `plt.show()` después de cada gráfico                    |
| ❌ Errores en `TotalCharges`                 | Valores no numéricos en la columna | Se corrige con `pd.to_numeric(..., errors="coerce")`             |
| ❌ Dataset desbalanceado                     | Mayoría de clientes no hacen churn | Usar técnicas de balanceo en futuros modelos predictivos         |

## ✅ Conclusiones

* Los contratos Month-to-Month, el pago con Electronic Check, el servicio de Fibra Óptica, la baja antigüedad y los cargos mensuales altos son los principales indicadores de churn.

* Estrategias sugeridas:

  * Incentivar contratos a largo plazo.
  * Mejorar experiencia del pago electrónico.
  * Revisar calidad del servicio de Fibra Óptica.
  * Programas de fidelización para clientes nuevos.
  * Construcción futura de modelos predictivos de churn.
