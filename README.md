# 📊 Análisis Global del Impacto y Adopción de la Inteligencia Artificial (2025-2026)

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Pivot Tables](https://img.shields.io/badge/Tablas_Dinámicas-107C41?style=for-the-badge&logo=microsoft&logoColor=white)
![Status](https://img.shields.io/badge/Estado-Completado-success?style=for-the-badge)

---

## 🎯 1. Definición del Problema y Objetivos

### Contexto
En los últimos tres años, la Inteligencia Artificial (IA) ha pasado de ser una tecnología experimental a convertirse en un motor principal de la economía global. Sin embargo, existe un debate importante en la industria: **¿las empresas realmente están obteniendo un retorno de inversión (ROI) claro de la IA, o se trata principalmente de pilotos y expectativas?**

### Objetivos del Proyecto
* **Objetivo Principal:** Analizar la tasa global de adopción empresarial de la IA, los sectores líderes en inversión y la brecha existente entre el uso generalizado y el impacto real en los resultados financieros.
* **Preguntas Clave:**
  1. ¿Qué porcentaje de organizaciones utiliza IA en sus operaciones diarias y en cuántas funciones de negocio la han integrado?
  2. ¿Cuáles son las industrias con mayor nivel de adopción e inversión en IA Generativa?
  3. ¿Qué proporción de empresas está logrando un impacto financiero significativo (*EBIT*) atribuible a la IA?

---

## 🔍 2. Búsqueda y Obtención de Datos

### Fuentes de Información
Los datos utilizados en este proyecto provienen del procesamiento y consolidación de reportes globales reconocidos en la industria:
* **McKinsey & Company:** *Global Survey on the State of AI* (Encuesta a 1,993 líderes en 105 países).
* **Stanford University:** *AI Index Annual Report* (Datos de inversión corporativa y adopción tecnológica).

### Variables del Dataset (`data/processed/AI_Global_Adoption_2026.xlsx`)
* `organizacion_id`: Identificador único de la empresa encuestada.
* `sector_industrial`: Sector (Tecnología, Salud, Finanzas, Retail, Manufactura, etc.).
* `region`: Región geográfica (Norteamérica, Europa, Asia-Pacífico, Latinoamérica).
* `adopcion_ia`: Estado de implementación (*No usa*, *En piloto*, *Usada en 1 función*, *Escalada en la empresa*).
* `inversion_anual_usd`: Presupuesto anual destinado a soluciones e infraestructura de IA.
* `impacto_ebit_pct`: Porcentaje del beneficio operativo atribuido al uso de IA (<1%, 1-5%, >5%).

---

## 🧹 3. Limpieza y Preparación de Datos en Microsoft Excel

El tratamiento y la transformación de los datos se llevaron a cabo dentro de Excel utilizando **Power Query** y **Fórmulas Avanzadas**:

1. **Estandarización de Variables Categóricas:** Mediante `BUSCARX` (XLOOKUP) y limpieza con Power Query, se homologaron las categorías de sectores que venían codificadas con distintos nombres regionales.
2. **Tratamiento de Valores Nulos y Duplicados:** Se identificaron y filtraron registros incompletos en la variable `inversion_anual_usd` utilizando filtros condicionales.
3. **Creación de Variables Calculadas (Feature Engineering):**
   * **Rango de Inversión:** Uso de `=SI(C2>=1000000; "Alta Inversión"; SI(C2>=250000; "Inversión Media"; "Baja Inversión"))`.
   * **Categorización de Desempeño:** Creación de la etiqueta *"Alto Rendimiento (High Performer)"* para empresas con un impacto en EBIT mayor al 5%.
4. **Modelado con Tablas Dinámicas:** Agrupación y segmentación multidimensional por región, sector e impacto financiero.

---

## 📊 4. Visualización, Análisis y Hallazgos

### Hallazgos Clave

#### 📌 Hallazgo 1: Adopción Masiva vs. Impacto Financiero Real (El "AI ROI Gap")
A pesar de que el **88% de las empresas** reporta utilizar IA en al menos una función operativa, **solo el 6% de las organizaciones se clasifica como "Alto Rendimiento"**, logrando atribuir más del 5% de su EBIT directamente a soluciones de IA.

![Gráfico de Adopción vs Impacto EBIT](./assets/grafico_adopcion_impacto.png)
*Figura 1: Porcentaje de organizaciones según su nivel de madurez e impacto financiero atribuible a la IA.*

---

#### 📌 Hallazgo 2: Líderes por Sector Industrial
El sector de **Tecnología** y **Servicios Financieros** lidera el nivel de adopción avanzada con más del 40% de las empresas escalando agentes y asistentes de IA en múltiples departamentos. Sectores como **Retail** y **Manufactura** concentran su uso principalmente en marketing, atención al cliente y optimización de la cadena de suministro.

![Gráfico Comparativo por Sector](./assets/grafico_sectores_ia.png)
*Figura 2: Distribución del nivel de integración de IA por sector industrial.*

---

#### 📌 Hallazgo 3: Crecimiento de la Inversión Global
La inversión corporativa global en IA alcanzó un pico histórico de más de **$580 mil millones de dólares**, con un fuerte crecimiento concentrado en infraestructura de IA Generativa y desarrollo de código asistido (donde más del 80% de los desarrolladores ya utiliza herramientas de IA).

![Gráfico de Tendencia de Inversión](./assets/grafico_inversion_global.png)
*Figura 3: Evolución de la inversión corporativa en tecnología e infraestructura de IA.*

---

## 💡 Recomendaciones / Conclusiones
1. **Superar la etapa de piloto:** El principal cuello de botella de las empresas no es el acceso al modelo de IA, sino la integración de los datos y la capacitación del personal para llevar los proyectos a escala.
2. **Enfoque en casos de alto valor:** Las empresas de alto rendimiento concentran sus esfuerzos en 2 o 3 casos de uso específicos alineados a sus ingresos, en lugar de dispersar recursos en múltiples experimentos aislados.

---

## 🛠️ Herramientas Utilizadas de Excel
* **Power Query:** Extracción, transformación y limpieza automatizada de los datos.
* **Tablas y Gráficos Dinámicos:** Creación de resúmenes por sector, región e impacto.
* **Fórmulas:** `BUSCARX` (XLOOKUP), `CONTAR.SI.CONJUNTO`, `SUMAR.SI.CONJUNTO`, `SI` anidados.
* **Dashboard Interactivo:** Creación de un panel final con segmentadores de datos (*Slicers*) e indicadores clave (KPIs).

---

## 📁 Estructura del Repositorio
```text
├── data/
│   ├── raw/                  # Archivos CSV/XLSX originales
│   └── processed/            # Dataset limpio en Excel
├── dashboard/
│   └── Dashboard_IA_2026.xlsx # Libro de trabajo interactivo con Dashboard
├── assets/                   # Capturas de gráficos y tablas para el README
└── README.md                 # Presentación principal del proyecto
