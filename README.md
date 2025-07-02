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
2. **Ajusta metadatos en**
   - Abre `pyproject.toml` y edita bajo `[project]`:
     ```toml
     name = "nombre-de-mi-proyecto"
     version = "0.1.0"
     description = "Breve descripción de tu proyecto"
     authors = ["Tu Nombre <tu@email.com>"]
     ```
3. **Renombra el paquete fuente**
   ```bash
   mv src/ml_project_plantilla src/mi_proyecto
   ```

4. **Configura tu repositorio Git**
   ```bash
   git remote remove origin
   git remote add origin git@github.com:tu-org/mi_proyecto.git
   git push -u origin main
   ```

---

## ⚙️ Instalación y entorno

1. **Crear el .env en el directorio raiz**

   ```bash
   poetry config virtualenvs.in-project true
   ```

2. **Instala dependencias**

   ```bash
   poetry install
   ```

3. **Acceder al entorno virtual creado en PowerShell**

   ```bash
   Invoke-Expression (poetry env activate)
   ```

4. **Corre un script**

   ```bash
   poetry run python path/to/tu_script.py
   ```

5. **Agrega dependencias de producción**

   ```bash
   poetry add <nombre_paquete>
   ```

6. **Agrega dependencias de desarrollo**

   ```bash
   poetry add --dev <nombre_paquete_dev>
   ```

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


