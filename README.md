# Análisis de datos del American Gut Project (AGP)

## Descripción

Este repositorio contiene el código desarrollado para el análisis de datos del **American Gut Project (AGP)**.

El objetivo del proyecto es estudiar posibles relaciones entre la **microbiota humana** y diferentes características de los individuos, como la alimentación, el índice de masa corporal (IMC), el sueño, la actividad física, el consumo de fibra, las enfermedades crónicas o el uso de antibióticos.

El análisis se realiza principalmente mediante **Python**, utilizando diferentes herramientas para el tratamiento y análisis de datos microbiológicos.

## Objetivos

Los principales objetivos del proyecto son:

* Preparar y organizar los datos del American Gut Project.
* Seleccionar las variables de interés de los metadatos.
* Relacionar los metadatos con la información de abundancia microbiana.
* Calcular la **diversidad alfa mediante el índice de Shannon**.
* Calcular la abundancia relativa de diferentes filos bacterianos.
* Obtener la relación **Firmicutes/Bacteroidetes (F/B)**.
* Analizar la posible relación entre la microbiota y diferentes factores relacionados con el estilo de vida y el estado de salud.

## Estructura del repositorio

```text
Codigo_AGP/
│
├── Code/
│   ├── agp_analysis.py
│   ├── agp_extract_columns.py
│   ├── diversity.py
│   ├── enfermedadesCronicas.py
│   ├── inspect_meta.py
│   └── select_conditions.py
│
└── README.md
```

## Descripción de los programas

### `agp_analysis.py`

Realiza el análisis general de los datos. Sus principales funciones son:

* Cargar la tabla de abundancias en formato BIOM.
* Cargar los metadatos de las muestras.
* Identificar las muestras comunes entre ambos conjuntos de datos.
* Calcular las diversidades
* Exportar los datos procesados en archivos CSV.

### `agp_extract_columns.py`

Selecciona y organiza las variables de interés a partir de los metadatos.

Entre las variables consideradas se encuentran:

* ID de muestra
* Edad
* Sexo
* IMC
* Tipo de dieta
* Estado de salud
* Uso de antibióticos
* Actividad física
* Horas de sueño
* Consumo de fibra
* Consumo de frutas y verduras
* Ingesta de azúcares añadidos
* Ansiedad y estrés
* Enfermedades crónicas
* Consumo de alcohol
* Bienestar subjetivo
* Diversidad de Shannon

También permite calcular la abundancia relativa de algunos filos bacterianos y la relación Firmicutes/Bacteroidetes.

### `diversity.py`

Calcula diferentes métricas relacionadas con la composición de la microbiota a partir del archivo BIOM.

En concreto, obtiene:

* Índice de diversidad de **Shannon**.
* Porcentaje de **Firmicutes**.
* Porcentaje de **Bacteroidetes**.
* Porcentaje de **Actinobacteria**.
* Porcentaje de **Proteobacteria**.
* Relación **Firmicutes/Bacteroidetes**.

Los resultados se guardan en un archivo CSV para su posterior análisis.

### `select_conditions.py`

Selecciona del archivo de metadatos las variables relacionadas con diferentes enfermedades y condiciones.

Entre ellas se incluyen:

* Diabetes
* IBD
* Alergias
* Migraña
* Asma
* PKU

El resultado se guarda en un nuevo archivo CSV para facilitar el análisis posterior.

### `enfermedadesCronicas.py`

Procesa las variables relacionadas con enfermedades crónicas y las agrupa en una única variable con tres posibles valores:

* **SI**
* **NO**
* **NO_DATA**

Esto permite disponer de una variable más sencilla para utilizar en análisis posteriores.

### `inspect_meta.py`

Es un programa auxiliar utilizado para explorar y revisar los metadatos.

Permite:

* Comprobar el número de filas y columnas.
* Consultar los nombres de las variables disponibles.
* Revisar el número de valores no nulos de cada columna.
* Generar una lista con los nombres de las columnas.

## Flujo de trabajo

El procesamiento de los datos sigue, de forma general, el siguiente esquema:

```text
Datos del American Gut Project
            ↓
    Carga de los datos
            ↓
    Revisión y limpieza
            ↓
 Selección de variables de interés
            ↓
 Cálculo de métricas de microbiota
            ↓
 Integración con los metadatos
            ↓
    Exportación de resultados
            ↓
   Análisis y visualización
```

## Tecnologías utilizadas

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **BIOM**
* **scikit-bio**
* **SciPy**
* **h5py**

## Datos

Los datos utilizados proceden del **American Gut Project (AGP)**.

El proyecto combina información sobre la composición de la microbiota obtenida mediante secuenciación con información sobre las características, hábitos y estado de salud de los participantes.

Debido al tamaño de los archivos originales, los datos completos no se incluyen necesariamente en este repositorio. Los programas utilizan los archivos de datos almacenados localmente, por lo que las rutas de acceso pueden necesitar ser modificadas para ejecutar el código en otro ordenador.

## Instalación

Para ejecutar los programas se necesita tener instalado **Python** y las bibliotecas utilizadas en el proyecto.

Las principales dependencias pueden instalarse mediante:

```bash
pip install pandas numpy matplotlib seaborn biom-format scikit-bio scipy h5py
```

Antes de ejecutar los programas, es necesario comprobar las rutas de los archivos de entrada y adaptarlas a la ubicación de los datos en el ordenador.

## Autora

**Adriana López Ferrer**

Proyecto de análisis de datos del **American Gut Project (AGP)**.
