---
title: Habilitación de APIs y servicios
seccion: 2
clase: 9
---

## 🧠 Idea clave

Para usar un servicio no basta con tener un proyecto: hay que **habilitar su API** en ese proyecto. Las APIs son la **puerta de entrada** entre tu proyecto y los servicios de Google Cloud.

```
Proyecto creado  +  API de Compute Engine habilitada  =  ✅ puedes crear VMs
Proyecto creado  +  API NO habilitada                 =  ❌ no puedes usar el servicio
```

## 🔑 Conceptos

- **Cada API se habilita POR PROYECTO.** Antes de habilitarla, verifica en el **selector** que estás en el proyecto correcto.
- Algunas APIs esenciales **vienen habilitadas por defecto**, como **Cloud Storage**, con la que puedes crear buckets sin pasos extra.
- Otras se habilitan **manualmente**, como **Compute Engine** o **BigQuery**.
- Al habilitar una API también se añaden **herramientas de supervisión** y **propiedades de facturación** del servicio. Esto te permite crear **presupuestos por servicio** (clase 2.6).

## ✅ 2 formas de habilitar una API

| Forma | Cómo |
|---|---|
| **Desde el servicio** | Entras por primera vez al servicio (ej. Compute Engine) → la consola te pide **habilitar la API** → un clic |
| **Desde la Biblioteca** | Busca **APIs y servicios** → **Biblioteca** → catálogo por categorías (Machine Learning, almacenamiento, análisis…) → buscas la API (ej. **Cloud Vision**) → **Habilitar** |

Antes de habilitarla, la Biblioteca muestra **costo, documentación, soporte y productos relacionados**.

**APIs y servicios** (página principal) = lista de las **APIs ya habilitadas** en el proyecto.

## ⛔ Inhabilitar una API

**APIs y servicios** → entras en la API (ej. Compute Engine) → **Inhabilitar**.

💡 **Buena práctica:** inhabilita las APIs que ya no usas para **mantener el proyecto limpio** y **evitar cargos inesperados**.

> 📌 *Extra, no visto en esta clase, útil para el examen:*
> ```bash
> gcloud services enable compute.googleapis.com    # habilitar
> gcloud services list --enabled                   # ver habilitadas
> gcloud services disable compute.googleapis.com   # inhabilitar
> ```

## 🎯 Tips para el examen

- **Error del tipo "API not enabled"** al usar un servicio → **habilita la API en ese proyecto**.
- Las APIs son **por proyecto**: habilitarla en un proyecto **no la habilita** en otro.
- Cloud Storage viene habilitada; Compute Engine y BigQuery suelen requerir habilitación.
- Catálogo completo → **APIs y servicios → Biblioteca**.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿Basta con crear un proyecto para lanzar VMs?</b></summary>
<p><b>No.</b> También debes <b>habilitar la API de Compute Engine</b> en ese proyecto.</p>
</details>

<details>
<summary><b>2. ¿Las APIs se habilitan para toda la cuenta o por proyecto?</b></summary>
<p><b>Por proyecto.</b></p>
</details>

<details>
<summary><b>3. ¿Qué API mencionada viene habilitada por defecto?</b></summary>
<p><b>Cloud Storage</b>.</p>
</details>

<details>
<summary><b>4. ¿Cuáles son las dos formas de habilitar una API desde la consola?</b></summary>
<p>1) Entrando al servicio, que te pide habilitarla. 2) Desde <b>APIs y servicios → Biblioteca</b>.</p>
</details>

<details>
<summary><b>5. ¿Qué información muestra la Biblioteca antes de habilitar una API?</b></summary>
<p>Costo, documentación, soporte y productos relacionados.</p>
</details>

<details>
<summary><b>6. ¿Qué se añade al habilitar una API, además del acceso al servicio?</b></summary>
<p><b>Herramientas de supervisión</b> y <b>propiedades de facturación</b> del servicio.</p>
</details>

<details>
<summary><b>7. Escenario: tu compañero habilitó BigQuery en el proyecto "dev", pero tú recibes "API not enabled" en "prod". ¿Por qué?</b></summary>
<p>Porque las APIs se habilitan <b>por proyecto</b>. Debes habilitarla también en "prod".</p>
</details>

<details>
<summary><b>8. ¿Por qué conviene inhabilitar las APIs que no usas?</b></summary>
<p>Para mantener el proyecto limpio y <b>evitar cargos inesperados</b>.</p>
</details>
