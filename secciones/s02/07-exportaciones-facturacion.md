---
title: Configurando exportaciones de facturación
seccion: 2
clase: 7
---

## 🧠 Idea clave

La **exportación de facturación** envía los datos de **uso y costos** de tus proyectos a **BigQuery**, el almacén de datos escalable y **sin servidor** de Google Cloud. Ahí puedes hacer **consultas y análisis detallados** y estimar cargos diarios o mensuales.

> 💡 Con la capa gratuita, BigQuery te da **1 TB de consultas al mes** y **10 GB de almacenamiento** sin costo.

## 📤 Los 3 tipos de exportación

| Tipo | Qué exporta | Frecuencia | Para qué |
|---|---|---|---|
| **Costo de uso estándar** | **Resumen** de costos **por SKU** | Diaria | Vista general del costo por producto (el elegido en la clase) |
| **Costo de uso detallado** | Detalle **a nivel de cada recurso** | Diaria | Análisis profundo y granular |
| **Precios** | Los **precios de los SKU** que usas | Cada vez que Google **cambia precios** | Seguir la evolución de tarifas |

> 📝 **SKU** = identificador único de cada artículo facturable, por ejemplo "hora de vCPU N1 en Iowa".

## 🪜 Configurarla

1. Ve a la página de **administración de costos** (Billing) → **Exportación de facturación**.
2. En el tipo deseado → **Editar configuración**.
3. Elige el **proyecto** donde vivirán los datos.
4. Elige o **crea un conjunto de datos** (*dataset*) de BigQuery:

| Opción del dataset | Detalle |
|---|---|
| **Nombre** | ej. `GCP` |
| **Tipo de ubicación** | **Región** o **multirregión** (ej. **Estados Unidos**, la elegida en la clase) |
| **Vínculo a dataset externo** | Consultar datos externos, ej. **Cloud Spanner**, como si estuvieran en BigQuery |
| **Vencimiento de tabla** | Sin marcar → los datos **no se borran automáticamente** |
| **Cifrado** | **Administrado por Google** (predeterminado) o **clave propia con Cloud KMS** |

5. **Crear dataset** → **Guardar**. BigQuery empieza a recibir datos.

> 📌 *Extra (no lo dijo la clase):* la exportación **no es retroactiva**: solo incluye datos **desde que la activas**. Conviene activarla **lo antes posible**.

## 🎯 Tips para el examen

- ¿Analizar costos con **SQL** o crear **reportes personalizados**? → **Exportación de facturación a BigQuery**.
- **Estándar** = resumen por SKU. **Detallado** = por recurso. **Precios** = tarifas de los SKU.
- El destino es un **dataset de BigQuery** dentro de un proyecto.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿A qué servicio se envían las exportaciones de facturación?</b></summary>
<p>A <b>BigQuery</b>, dentro de un conjunto de datos (dataset).</p>
</details>

<details>
<summary><b>2. ¿Cuáles son los 3 tipos de exportación?</b></summary>
<p><b>Costo de uso estándar</b>, <b>costo de uso detallado</b> y <b>precios</b>.</p>
</details>

<details>
<summary><b>3. ¿Qué diferencia hay entre la exportación estándar y la detallada?</b></summary>
<p>La <b>estándar</b> es un resumen diario por SKU. La <b>detallada</b> llega al nivel de <b>cada recurso</b>.</p>
</details>

<details>
<summary><b>4. ¿Cuándo se actualiza la exportación de precios?</b></summary>
<p>Cada vez que <b>Google Cloud cambia los precios</b> de los productos.</p>
</details>

<details>
<summary><b>5. ¿Qué te da gratis BigQuery en la capa gratuita?</b></summary>
<p><b>1 TB de consultas al mes</b> y <b>10 GB de almacenamiento</b>.</p>
</details>

<details>
<summary><b>6. ¿Qué opciones de cifrado tiene el dataset?</b></summary>
<p><b>Clave administrada por Google</b> o <b>clave propia con Cloud KMS</b>.</p>
</details>

<details>
<summary><b>7. Escenario: finanzas quiere ver qué VM concreta generó más costo el mes pasado. ¿Qué exportación activas?</b></summary>
<p>El <b>costo de uso detallado</b>, que da información a nivel de recurso.</p>
</details>
