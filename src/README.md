# Estructura Interna del Código

Descripción de la organización y convenciones dentro del paquete fuente (`src/mi_proyecto`).

---

## 📁 Carpeta base: `src/mi_proyecto/`

Contiene los módulos y paquetes que implementan la lógica de tu proyecto.

```text
mi_proyecto/
├── data/
├── data_engineering/
├── interfaces/
├── models/
├── pipelines/
├── training/
└── utils/
```

### `data/`

- **Propósito**: Almacenamiento de datos.
- **Subdirectorios sugeridos**:
  - `raw/`: datos originales (sin modificar)
  - `processed/`: datos transformados y listos para usar
  - `external/`: datos obtenidos de terceros

### `data_engineering/`

- **Propósito**: Código para procesos ETL/ELT.
- **Convenciones**:
  1. **Extract** (`extract_*`): conectores a BD, APIs o lectura de ficheros.
  2. **Transform** (`transform_*`): limpieza, normalización, feature engineering.
  3. **Load** (`load_*`): carga en data warehouse o lago de datos.
- **Documentación interna**: cada script o módulo debe incluir docstring o mini `README.md` con:
  - Dependencias y variables de entorno
  - Comandos de ejecución
  - Formatos de entrada y salida

### `interfaces/`

- **Propósito**: Contratos (interfaces/abstract classes) que definen firmas de métodos.
- **Convenciones**:
  - Nombre de archivo = nombre de la interface (p. ej. `IModel.py`).
  - Solo firmas de métodos y constantes, sin lógica.
  - Docstrings que describan responsabilidad y parámetros.

### `models/`

- **Propósito**: Implementaciones de modelos predictivos.
- **Contenido**:
  - Clases de modelo (scikit-learn, TensorFlow, PyTorch, wrappers ONNX).
  - Funciones de serializar/deserializar (`save()`, `load()`).
  - Subcarpeta `experiments/` (opcional) para checkpoints y resultados.

### `pipelines/`

- **Propósito**: Orquestación de flujos de trabajo.
- **Puede incluir**:
  - DAGs de Airflow, scikit-learn pipelines o similares.
  - Scripts que unen ETL, entrenamiento y validación.
  - Configuraciones de scheduling y dependencias.

### `training/`

- **Propósito**: Scripts y notebooks para entrenar y evaluar modelos.
- **Archivos tipo**:
  - `train.py`, `evaluate.py`, `hyperparam_search.py`.
  - Notebooks de experimentación.
  - Salidas de métricas y visualizaciones.

### `utils/`

- **Propósito**: Funciones auxiliares genéricas.
- **Ejemplos**:
  - Gestión de configuración (`config.py`).
  - Logging y métricas (`logger.py`, `metrics.py`).
  - Helpers de visualización y preprocesamiento común.

---

> Mantén cada carpeta enfocada en su **responsabilidad**, siguiendo convenciones de nombres y documentación para facilitar la escalabilidad y el mantenimiento.

