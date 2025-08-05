# ML Project Template

Plantilla escalable para iniciar proyectos de Machine Learning con estructura modular y gestión de dependencias mediante Poetry.

---

## 🌟 Características

- Estructura clara separada por responsabilidades
- Gestión de entornos y dependencias con Poetry
- Preparada para publicar como paquete Python
- Pasos automáticos para clonar, renombrar y configurar tu propio repositorio

---

## 🛠️ Prerrequisitos

- **Git** instalado y configurado
- **Python 3.8+** en tu sistema
- **Poetry** (gestor de dependencias y publicación de paquetes)

---

## 🚀 Crear tu proyecto basado en esta plantilla

1. **Clona y renombra**
   ```bash
   git clone https://github.com/tu-org/ml_project_template.git nombre_de_mi_proyecto
   cd nombre_de_mi_proyecto
   ```

2. **Renombra el paquete fuente**
   ```bash
   mv src/ml_project_plantilla src/mi_proyecto
   ```

3. **Configura tu repositorio Git**
   ```bash
   git remote remove origin
   git remote add origin git@github.com:tu-org/mi_proyecto.git
   git push -u origin main
   ```

---

## ⚙️ Instalación y entorno

### Opción A: Entorno virtual manejado por Poetry

1. **Inicializa Poetry en tu proyecto**

   Desde la raíz del repositorio ejecuta:

   ```bash
   poetry init
   ```

   El asistente te guiará para crear el `pyproject.toml`.
   Responde paso a paso:

   - **Package name**: `ml-project-plantilla` (o el nombre de tu proyecto).
   - **Version**: `0.1.0` es la predeterminada.
   - **Description**: breve descripción del proyecto.
   - **Author**: tu nombre y correo.
   - **License**: licencia que usarás (por ejemplo, `MIT`).
   - **Compatible Python versions**: `>=3.10,<3.13`.
   - Cuando pregunte por dependencias, puedes responder `no` y agregarlas después.

   Al finalizar se generará el archivo `pyproject.toml`.

2. **Crea el entorno virtual dentro del proyecto**

   ```bash
   poetry config virtualenvs.in-project true
   ```

3. **Agrega dependencias de producción**

   ```bash
   poetry add zope
   ```

4. **Agrega dependencias de desarrollo**

   ```bash
   poetry add --dev pytest pytest-cov pre-commit flake8 black isort mypy jupyterlab ipykernel
   ```

5. **Instala el entorno**

   ```bash
   poetry install
   ```

6. **Activa el entorno virtual**

   En PowerShell:

   ```bash
   Invoke-Expression (poetry env activate)
   ```

   En otros shells:

   ```bash
   poetry shell
   ```

7. **Ejecuta un script**

   ```bash
   poetry run python path/to/tu_script.py
   ```

### Opción B: Usar un entorno existente de Anaconda

Si trabajas dentro de un entorno creado con **Anaconda** o **Miniconda**, puedes usar ese mismo entorno como base y dejar que Poetry solo gestione las dependencias:

1. **Crea o activa tu entorno de Anaconda**

   ```bash
   conda create -n mi_entorno python=3.10
   conda activate mi_entorno
   ```

2. **Instala Poetry dentro de ese entorno**

   ```bash
   conda install -c conda-forge poetry   # o pip install poetry
   ```

3. **Indica a Poetry que use el entorno actual**

   Esto evita que se cree un `.venv` adicional.

   ```bash
   poetry config virtualenvs.create false
   ```

4. **Inicializa el proyecto y agrega dependencias** (procede igual que en la opción anterior)

   Dentro del entorno activo:

   ```bash
   poetry init
   poetry install
   ```

De esta forma, el entorno de Anaconda funciona como tu entorno de ejecución y Poetry se encarga de manejar las dependencias dentro de él.

---

## 📂 Estructura de carpetas (resumen)

```text
nombre_de_mi_proyecto/
├── .venv/             # Entorno virtual (oculto en git)
├── docs/             # Documentación adicional
├── notebooks/        # Notebooks de prototipado y desarrollo
├── src/              # Código fuente del paquete
│   └── mi_proyecto/  # Módulo principal con subcarpetas internas
├── tests/            # Pruebas unitarias
├── pyproject.toml    # Configuración de Poetry
├── README.md         # Este archivo
└── .gitignore
```

---

## 📦 Uso e importación de módulos

Una vez instalado el entorno y agregadas las dependencias, puedes importar y usar los módulos de tu paquete en tus scripts o notebooks de la siguiente manera:

Supón que tu paquete principal se llama `mi_proyecto` y tienes un módulo llamado `utils.py` dentro de `src/mi_proyecto/`:

```python
from src.mi_proyecto import utils

# Usar una función del módulo utils
resultado = utils.mi_funcion(param1, param2)
print(resultado)
```

Si tienes submódulos o subcarpetas, puedes importarlos así:

```python
from src.mi_proyecto.submodulo import otra_funcion
```

Para ejecutar un script que use tu paquete desde la raíz del proyecto:

```bash
poetry run python path/to/tu_script.py
```

Recuerda que el entorno virtual debe estar activado o usar `poetry run` para que Python encuentre tu paquete correctamente.

Además solo podrás llamar a los modulos y submódulos que esten dentro de `src`, estos los podrás llamar en cualquier parte  e incluso dentro de los mismos submodulos de `src`.

---
## NOTA IMPORTANTE: Una vez leído los README, recuerda eliminarlos y adapatarlos a tu proyecto especifico

---

## 📝 Cómo contribuir

1. Crea una **rama** nueva: `git checkout -b feature/nueva-funcionalidad`
2. Realiza **commits** claros y atómicos
3. Abre un **Pull Request** describiendo tus cambios

---


