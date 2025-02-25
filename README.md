# ML-Project-plantilla

## Ejecución con poetry
```bash
#Crear el .env en el directorio raiz 
poetry config virtualenvs.in-project true

# Instalar dependencias
poetry install

# Acceder al entorno virtual creado en PowerShell
Invoke-Expression (poetry env activate)

# Ejecutar el proyecto
poetry run python main.py
```
