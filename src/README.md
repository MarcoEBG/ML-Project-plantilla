# src

Este directorio contiene el código fuente del proyecto de MLOps. Aquí encontrarás los scripts y módulos necesarios para entrenar, evaluar y desplegar modelos de machine learning.

## Estructura del directorio 

- `data/`: Scripts para la carga y preprocesamiento de datos de la base da datos, así como archivos .parquet  de los datos empleados para el modelamiento.
-`data_engineering/`: ----- 
- `interfaces/`: Aquí colocamos todas las **definiciones de contratos** (interfaces) que usan nuestras clases.  
Cada archivo debe:
  1. Llevar el mismo nombre que la interfaz que contiene p. ej. `IFeatureSelector.py`, `IModelSelector.py`, 
  2. Incluir únicamente la firma de métodos y constantes.
  3. Acompañarse de un breve comentario que describa la responsabilidad de la interface.  
  4. No contener lógica ni dependencias de librerías concretas para mantenerlas puras y reutilizables.
- `models/`: Definición y entrenamiento de modelos.
- `evaluation/`: Evaluación y métricas de rendimiento de los modelos.
- `deployment/`: Scripts para el despliegue de los modelos en producción.
- `utils/`: Funciones utilitarias y herramientas auxiliares.


## Instrucciones

1. **Preprocesamiento de datos**: Ejecuta los scripts en `data/` para preparar los datos. 
2. **Entrenamiento de modelos**: Utiliza los scripts en `models/` para entrenar los modelos.
3. **Evaluación de modelos**: Evalúa el rendimiento de los modelos con los scripts en `evaluation/`.
4. **Despliegue de modelos**: Despliega los modelos en producción utilizando los scripts en `deployment/`.

## Requisitos

- Python 3.x
- Bibliotecas especificadas en `requirements.txt`

## Contribuciones

Las contribuciones son bienvenidas. Por favor, sigue las directrices del proyecto y asegúrate de que tu código sigue las mejores prácticas de MLOps.
