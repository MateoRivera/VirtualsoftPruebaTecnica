# Prueba Técnica – Científico de Datos

Este repositorio contiene el desarrollo de la prueba técnica para el cargo de Científico de Datos. Se abordan dos problemas mediante análisis exploratorio, modelado y evaluación de resultados.

## Estructura del proyecto

```text
.
├── data/
│   ├── abuso_bonos.csv
│   ├── embeddings.csv
│   ├── embeddings.npy
│   └── usuarios.csv
├── notebooks/
│   ├── punto1.ipynb
│   └── punto2.ipynb
├── src/
│   └── prueba_modelamiento/
├── .gitignore
├── .python-version
├── pyproject.toml
├── uv.lock
└── README.md
```

## Requisitos

- Python, en la versión definida en `.python-version`.
- [uv](https://docs.astral.sh/uv/), para la gestión del entorno y las dependencias.
- JupyterLab.

## Instalación

Clonar el repositorio:

```bash
git clone https://github.com/MateoRivera/VirtualsoftPruebaTecnica.git
cd VirtualsoftPruebaTecnica
```

Sincronizar el entorno e instalar las dependencias:

```bash
uv sync --locked
```

Este comando utiliza las dependencias declaradas en `pyproject.toml` y las versiones fijadas en `uv.lock`.

## Ejecución

Desde la raíz del proyecto, iniciar JupyterLab:

```bash
uv run jupyter lab
```

Desde la interfaz de JupyterLab, abrir los notebooks ubicados en `notebooks/` y ejecutar sus celdas en orden.

## Desarrollo de la prueba

### Punto 1. Identificación de usuarios con posible abuso de bonos

Notebook: `notebooks/punto1.ipynb`

Se analiza el histórico de reclamaciones de bonos para desarrollar una alternativa al criterio de revisión vigente.

El análisis incluye:

- Exploración y validación de los datos.
- Identificación de registros revisados y etiquetas confirmadas.
- Separación de los datos por marca para mantener las unidades monetarias correspondientes.
- Entrenamiento y comparación de modelos de clasificación.
- Selección de umbrales de decisión considerando el coste de revisión y el beneficio económico estimado.
- Evaluación sobre un conjunto de prueba y análisis de la capacidad operativa.

### Punto 2. Análisis de embeddings de usuarios

Notebook: `notebooks/punto2.ipynb`

Se estudian representaciones vectoriales de 64 dimensiones generadas mediante aprendizaje contrastivo a partir de secuencias de eventos de usuarios.

El análisis incluye:

- Validación y alineación de los archivos CSV y NPY.
- Análisis de las normas de los embeddings.
- Reducción de dimensionalidad mediante PCA.
- Exploración de relaciones entre los embeddings y las características de los usuarios.
- Evaluación de agrupamientos mediante K-Means.
- Caracterización de segmentos según preferencias de juego y patrones de interacción.

Los segmentos identificados se consideran exploratorios y constituyen un punto de partida para posibles aplicaciones en CRM y recomendación de contenido.

## Tecnologías utilizadas

- Python
- uv
- JupyterLab
- NumPy
- pandas
- Matplotlib
- Seaborn
- scikit-learn
- SciPy

## Reproducibilidad

Los notebooks utilizan rutas relativas para acceder a los archivos de la carpeta `data/`. Se recomienda conservar la estructura del repositorio al ejecutarlos.

La gestión de dependencias se realiza mediante `pyproject.toml` y `uv.lock`, lo que permite mantener un entorno reproducible.