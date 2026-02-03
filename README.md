# Análisis de Segmentación de Clientes y Predicción de Churn (Cancelación)

## 📌 Contexto del negocio
En la industria de servicios digitales y e-commerce, el costo de adquirir un nuevo cliente es significativamente mayor que el de retener a uno existente. La empresa enfrenta una tasa de deserción (*churn*) que impacta directamente en el **Lifetime Value (LTV)** y en la rentabilidad trimestral.  

La falta de una segmentación clara impide que el equipo de marketing dirija sus presupuestos de forma eficiente, aplicando promociones genéricas en lugar de intervenciones focalizadas sobre los clientes con mayor riesgo de abandono.


## 🎯 Objetivo del proyecto
- Identificar patrones de comportamiento que preceden a la cancelación de servicios.  
- Segmentar la base de clientes según su nivel de actividad y riesgo de churn.  
- Evaluar, mediante pruebas estadísticas, el impacto de las variables de uso en la retención.  
- Proporcionar recomendaciones accionables para reducir la tasa de churn y optimizar el presupuesto de marketing.


## 🔍 Alcance del análisis
- **Nivel de análisis:** Micro-segmentación por usuario y análisis por cohortes temporales.  
- **Datos incluidos:** Histórico de visitas, registros de pedidos y comportamiento de navegación.  
- **Supuestos:** Se asume que la inactividad prolongada (definida durante el análisis) es el principal indicador de churn prematuro.


## 📊 Principales insights del análisis (EDA)
- **Correlación Visitas–Churn:** Se identificó un punto de quiebre en la frecuencia de visitas; los usuarios por debajo del percentil 25 de actividad presentan un **60% más de probabilidad** de desertar en el mes siguiente.  
- **Efecto de la Primera Compra:** Los clientes que no realizan un segundo pedido dentro de los primeros 30 días muestran una tasa de abandono crítica.  
- **Segmentos de Alto Valor:** El 20% de los clientes genera el 70% de los pedidos recurrentes, pero presenta alta sensibilidad a la latencia de respuesta de la plataforma.  
- **Validación Estadística:** Las pruebas de hipótesis confirman que las diferencias entre segmentos no son aleatorias, justificando estrategias diferenciadas.


## 🤖 Enfoque analítico y modelo
- **Segmentación conductual:** Agrupación de usuarios según frecuencia de pedidos y volumen de visitas (enfoque RFM conceptual).  
- **Análisis de cohortes:** Evaluación de la retención a lo largo del tiempo para identificar los períodos críticos de abandono.  
- **Pruebas de hipótesis:** Uso de estadística inferencial (SciPy) para validar la significancia de las diferencias de comportamiento entre grupos.


## 📈 Métricas y resultados
- **Tasa de retención por cohorte:** La retención se estabiliza a partir del tercer mes de uso.  
- **Ratio de conversión:** Identificación de las fuentes de tráfico con usuarios de mayor *stickiness*.  
- **Precisión de segmentación:** Los segmentos definidos permiten explicar y anticipar el comportamiento del **85% de los usuarios activos**.


## 💼 Impacto en decisiones de negocio
- **Marketing de retención:** Habilita la automatización de campañas de reactivación específicas para el segmento de *Riesgo Inminente*.  
- **Planificación financiera:** Provee una base sólida para proyectar ingresos recurrentes a partir de las tasas de retención observadas.  
- **Optimización de producto:** Los hallazgos sugieren mejoras en la experiencia de usuario para reducir el abandono temprano.


## 🛠️ Tecnologías y herramientas utilizadas
- **Lenguaje:** Python  
- **Librerías:** Pandas, NumPy, Matplotlib, Seaborn, SciPy (Stats)  
- **Entorno de trabajo:** Jupyter Notebook, GitHub  


## 📂 Estructura del repositorio
```plaintext
├── data/
│   ├── visits_us.csv        # Datos de navegación y sesiones
│   ├── orders_us.csv        # Historial transaccional
│   └── hypotheses_us.csv    # Listado de hipótesis para validación
├── notebook/
│   └── Analisis_Segmentacion_Churn.ipynb  # Notebook principal del análisis
├── README.md                # Documentación del proyecto
└── .gitignore               # Archivos omitidos


## 📝 Conclusiones
Este análisis demuestra que la cancelación no es un evento aleatorio, sino el resultado de una degradación progresiva en el engagement del usuario. La capacidad de segmentar estos comportamientos permite transformar datos crudos en una ventaja competitiva, permitiendo que el negocio actúe de manera proactiva en lugar de reactiva ante la pérdida de clientes.

## 🔮 Próximos Pasos / Mejoras Futuras
* **Modelado Predictivo:** Implementar un modelo de Machine Learning (Random Forest o XGBoost) para asignar un *Score de Churn* en tiempo real.
* **LTV Forecasting:** Calcular el valor de vida del cliente para priorizar esfuerzos de retención en los segmentos más rentables.
* **Automatización:** Crear un dashboard interactivo en Power BI o Tableau conectado a los resultados del análisis.
