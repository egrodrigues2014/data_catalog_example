# Data Catalog Guide

## 🎯 Objectivo:

Proporcionar una guía centralizada para la gestión de datos que incluya:

- Diccionario de datos detallado  
- Clasificación de sensibilidad de los datos  
- Responsables de negocio y técnicos (Data Ownership)  
- Relación de tablas con sus pipelines y dashboards asociados 

# 🏗 Data Model 

## 1️⃣ Diccionario de Datos: Tablas

| Propiedad | Tipo | Descripción |
|------------|------|-------------|
| Nombre Dataset | Title | Nombre oficial |
| Dominio | Select | Comercial, Finanzas, Marketing, Ops |
| Data Owner | Person | Responsable de negocio |
| Data Steward | Person | Responsable técnico |
| Sistema Origen | Text | CRM, ERP, App |
| Base de Datos | Text | Postgres, MySQL, Snowflake, BigQuery, etc |
| Esquema | Text | Schema |
| Frecuencia | Select | Diario, Semanal, Mensual |
| Tipo de Carga | Select |Carga Completa (Full Load), Carga Incremental, Change Data Capture (CDC) |
| Sensibilidad | Select | Público, Interno, Confidencial, PII |
| Dashboard Relacionado | Relation | Dashboards relacionados |
| Pipeline | Text | Cron/Airflow/dbt |


## 2️⃣ Diccionario de Datos: Columnas 


| Propiedad | Tipo | Descripción |
|------------|------|-------------|
| Tabla | Relation | Relación con Datasets |
| Nombre Campo | Title | nombre_columna |
| Tipo de Dato | Select | INT, VARCHAR, DATE |
| Descripción | Text | Definición clara |
| Ejemplo | Text | Valor ejemplo |
| Sensible | Checkbox | publico,interno, confidencial, sensible|
| Regla de Calidad | Text | No nulo, >0, unico, etc |
| Regla de Calculo (Solo si aplica) | Text | Detalle de como se calcula |

---

## 3️⃣ Inventario de Dashboards

| Propiedad | Tipo |
|------------|------|
| Nombre | Titulo |
| Tool | Power BI, Looker, Tableau, etc|
| Owner | Person |
| Dataset Fuente | Tablas / vistas usadas en el informe |
| Link | URL |


# 🔗 Relaciones clave

- Dataset ↔ Campos (1 a muchos)
- Dataset ↔ Dashboards (1 a muchos)
  
<img width="340" height="308" alt="image" src="https://github.com/user-attachments/assets/7a8adf89-f936-41c5-ba06-d9b58fbd54a9" />
  

Esto te permite:

- Ver qué dashboards impacta una tabla  
- Ver qué campos tiene cada dataset  
- Hacer análisis de impacto simple
  

## ⚠️ Consideraciones

Especificar limitaciones conocidas y definiciones a nivel de arquitectura.


