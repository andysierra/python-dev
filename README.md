<div align="center">

# 🐍 Python Playground

**Mi espacio para jugar, romper cosas y aprender Python.**

De los operadores básicos y los primeros DataFrames a diseñar un microservicio de producción con arquitectura hexagonal.

![Python](https://img.shields.io/badge/Python-3.12+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)

![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat-square&logo=python&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)

</div>

---

## 🧭 ¿Qué es esto?

Este repositorio no es un producto: es una **bitácora de aprendizaje**. Aquí guardo cuadernos de práctica, análisis de datasets reales y el diseño de proyectos más ambiciosos. Algunos son ejercicios de clase; otros, la base de algo que quiero llevar a producción.

La idea es simple: **probar, equivocarse, aprender y dejar registro.**

---

## 🗺️ El camino recorrido

```mermaid
flowchart LR
    A["➕ Fundamentos<br/><sub>Operadores · Tipos</sub>"] --> B["🔢 NumPy<br/><sub>Arrays · Vectorización</sub>"]
    B --> C["🐼 Pandas<br/><sub>Series · DataFrames</sub>"]
    C --> D["📊 Visualización<br/><sub>Matplotlib · Seaborn</sub>"]
    D --> E["🔍 EDA<br/><sub>Datasets reales</sub>"]
    E --> F["🏛️ Backend<br/><sub>FastAPI · Hexagonal</sub>"]
```

---

## 📂 Estructura

```
python-dev/
├── 📊 analisis-de-datos/     # Notebooks de Jupyter: NumPy, Pandas, gráficos y EDA
└── 🏛️ scaffold-python/       # Specs para un microservicio FastAPI con arquitectura hexagonal
```

---

## 📊 `analisis-de-datos/` — Ciencia de datos con Jupyter

### 📚 Fundamentos

| Notebook | Qué aprendí |
|---|---|
| [`1. Operadores en Python`](analisis-de-datos/1.%20Operadores%20en%20Python.ipynb) | Operadores aritméticos, de asignación, de comparación, lógicos, de pertenencia y de identidad |
| [`2. Numpy`](analisis-de-datos/2.%20Numpy.ipynb) | Arrays y operaciones vectorizadas |
| [`3. Visualización de datos`](analisis-de-datos/3.%20Visualizaci%C3%B3n%20de%20datos.ipynb) | Gráficos de barras, líneas, dispersión e histogramas con Matplotlib y Seaborn |
| [`4. Introducción a Pandas`](analisis-de-datos/4.%20Introducci%C3%B3n%20a%20Pandas%20(vac%C3%ADo).ipynb) | Series, DataFrames y operaciones básicas (plantilla para practicar) |

### 🔍 Análisis de datasets

| Notebook | Dataset | Qué explora |
|---|---|---|
| [🏨 `EDA`](analisis-de-datos/EDA.ipynb) | `reservaciones.csv` | Reservas de hotel: conteo y proporción de reservas canceladas vs. no canceladas |
| [❤️ `heart diseases`](analisis-de-datos/heart%20disease/heart%20diseases.ipynb) | `heart.csv` | Primer vistazo y estadística descriptiva de variables clínicas para predecir enfermedad cardíaca |
| [📺 `youtube channel analisys`](analisis-de-datos/youtube%20channel%20analisys/youtube%20channel%20analisys.ipynb) | `data.csv` | Los canales de YouTube con más suscriptores: idioma, categoría y país |

---

## 🏛️ `scaffold-python/` — Microservicio de producción

Un proyecto **spec-driven**: antes de escribir código, cada decisión de arquitectura y estándar queda documentada en un spec. El objetivo es construir un microservicio de grado producción en Python, **no un ejercicio desechable**.

Está basado en el [Scaffold Clean Architecture de Bancolombia](https://github.com/bancolombia/scaffold-clean-architecture), el mismo que uso en mis proyectos Java, adaptado a FastAPI.

| Capa | Tecnología |
|---|---|
| Framework | FastAPI (async-first) + Pydantic v2 |
| Persistencia | PostgreSQL + SQLAlchemy async + Alembic |
| Caché | Redis |
| Seguridad | Validación de JWT |
| Observabilidad | Logging estructurado + OpenTelemetry |
| Calidad | pytest, tipado estricto, linting, SonarQube |
| Contenedores | Docker + Docker Compose |

```mermaid
flowchart LR
    EP["🌐 Entry Points<br/><sub>FastAPI routers</sub>"] --> UC
    subgraph DOMAIN["🧠 Domain"]
        UC["Use Cases"] --> M["Models · Gateways"]
    end
    DA["🔌 Driven Adapters<br/><sub>SQLAlchemy · Redis</sub>"] -.implementa.-> M
```

### 📜 Los specs

| Spec | Contenido |
|---|---|
| [`AGENTS.md`](scaffold-python/AGENTS.md) | Punto de entrada: intención, stack y cómo se usan los specs |
| [`architecture.md`](scaffold-python/specs/architecture.md) | Capas, patrón Gateway, reglas de importación y equivalencias Java/Spring → Python |
| [`backend-standards.md`](scaffold-python/specs/backend-standards.md) | Tipado, DTOs, manejo de errores, logging, configuración y Dockerfile |
| [`security.md`](scaffold-python/specs/security.md) | Autenticación con JWT y autorización |
| [`testing.md`](scaffold-python/specs/testing.md) | Tests unitarios, mocking, async y cobertura |
| [`business.md`](scaffold-python/specs/business.md) | Dominio del negocio *(por definir)* |

---

## ▶️ Cómo correr los notebooks

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install jupyterlab numpy pandas matplotlib seaborn
jupyter lab
```

---

## 📝 Notas

- Los datasets (`.csv`) son públicos y se versionan junto a su notebook para que cada análisis se pueda reproducir.
- Los entornos virtuales, cachés de Python y checkpoints de Jupyter no se versionan.
- Los secretos se pasan por variables de entorno (`.env`), que tampoco se versionan.

<div align="center">

---

Hecho con 🐍 y mucha curiosidad por **[Andrés Sierra](https://github.com/andysierra)**

</div>
