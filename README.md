# An-lisisSUBE

link del dataset que utilice: https://drive.google.com/file/d/1uBcQY957tmnk5lLnsHc5AFpN-7kZsSPJ/view?usp=drive_link

# Análisis de Datos SUBE - Transporte Público Paraná

Este proyecto consiste en la creación de un **Data Warehouse** basado en datos de transacciones del sistema SUBE, utilizado en el Área Metropolitana de Paraná. El objetivo es analizar patrones de uso en el transporte público para optimizar el servicio, especialmente durante las horas pico.

---

## 🎯 Objetivo

- Construir un **Data Warehouse** de tipo estrella para gestionar datos de transacciones SUBE.
- Aplicar un proceso **ETL** (Extract, Transform, Load) para preparar los datos.
- Generar métricas útiles para la toma de decisiones.
- Crear visualizaciones interactivas mediante **Power BI**.

---

## 🗃️ Dataset

- Fuente: Base de datos del sistema SUBE.
- Registros: 1.698.204 filas.
- Variables utilizadas:
  - `IDLINEA`: Número de colectivo.
  - `CODIGOCONTRATO`: Tipo de contrato del usuario (estudiante, jubilado, etc.).
  - `MONTO`: Monto pagado en cada viaje.
  - `FECHATRX`: Fecha y hora de la transacción.
  - `DESCUENTO`: Valor del descuento aplicado.

---

## 🏛️ Modelo de Datos

Modelo de base de datos **estrella** compuesto por:

### Dimensiones
- **Tiempo** (`id_tiempo`, `fecha`, `mes`, `día_semana`, `hora`)
- **Contrato** (`id_contrato`, `tipo`)
- **Línea** (`id_linea`, `número`)

### Tabla de hechos
- **Hechos** (`id_hechos`, `id_tiempo`, `id_contrato`, `id_linea`, `cantidad`, `monto`, `descuento`)

---

## 🛠️ Tecnologías usadas

- **Python** (pandas, psycopg2)
- **PostgreSQL** (base de datos)
- **Power BI** (dashboard de visualización)
- **Modelo de diseño**: Metodología **Kimball** para Data Warehousing.

---

## ⚙️ Proceso ETL

- **Extracción**: Se seleccionaron columnas relevantes de la base SUBE.
- **Transformación**: 
  - Se tradujeron códigos numéricos de `IDLINEA` y `CODIGOCONTRATO` usando diccionarios de datos.
  - Se crearon nuevas variables a partir de `FECHATRX` (mes, día de semana, hora).
- **Carga**:
  - Inserción de datos en PostgreSQL.
  - Inserción de dimensiones y tabla de hechos respetando claves primarias y foráneas.

---

## 📊 Visualizaciones

Se desarrolló un dashboard en Power BI que permite:

- Filtrar datos por tipo de contrato.
- Visualizar cantidad de transacciones por hora del día.
- Analizar transacciones por número de línea de colectivo.
- Ver actividad por día de la semana.

---

## 📄 Informe completo

El informe técnico detallado del proyecto se encuentra en el archivo [`Informe académico.pdf`](docs/Informe académico.pdf).

---

## 👨‍💻 Autor

- Rodrigo Zamora  
(Tecnicatura Universitaria en Procesamiento y Explotación de Datos)

---

