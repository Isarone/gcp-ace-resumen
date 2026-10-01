---
title: Formas de interactuar con Google Cloud
seccion: 1
clase: 6
---

## 🧠 Idea clave

Hay **4 formas** de acceder a Google Cloud e interactuar con él:

![Las 4 formas de interactuar con Google Cloud: 01 Google Cloud console, 02 Cloud SDK and Cloud Shell, 03 APIs, 04 Google Cloud app]({{ '/assets/img/s01-06-formas-interactuar.png' | relative_url }})

| # | Forma | Tipo de interfaz | Ideal para… |
|---|---|---|---|
| 01 | **Consola de Google Cloud** | Gráfica (web) | Administrar visualmente, revisar estado, presupuestos |
| 02 | **Cloud SDK y Cloud Shell** | Línea de comandos | Automatizar y administrar con comandos (`gcloud`, `bq`) |
| 03 | **APIs** | Programática (código) | Que **tus aplicaciones** controlen los servicios |
| 04 | **App de Google Cloud** | App móvil | Tareas rápidas, facturación y alertas desde el celular |

## 01 · 🖥️ Consola de Google Cloud

**Interfaz gráfica de usuario (GUI)** web de Google Cloud. Permite:
- **Implementar, escalar y diagnosticar** problemas de producción.
- **Localizar recursos** y verificar su **estado**, con control total de su administración.
- **Establecer presupuestos** para controlar el gasto.
- **Buscar** recursos rápidamente.
- Conectarte a instancias por **SSH desde el navegador**.

## 02 · ⌨️ Cloud SDK y Cloud Shell

**Cloud SDK** = conjunto de herramientas para administrar recursos y aplicaciones en Google Cloud:

| Herramienta | Para qué |
|---|---|
| **`gcloud`** (CLI de Google Cloud) | **Interfaz principal de línea de comandos** para productos y servicios de Google Cloud |
| **`bq`** | Línea de comandos para **BigQuery** |

**Cloud Shell** = línea de comandos **en el navegador**:
- Es una **VM basada en Debian**.
- Tiene un **directorio de inicio persistente de 5 GB**.
- `gcloud` y otras utilidades **siempre están instalados, actualizados y autenticados**.

```bash
# Ejemplos (los verás más adelante en el curso)
gcloud compute instances list   # listar VMs
bq ls                           # listar datasets de BigQuery
```

## 03 · 🧩 APIs

- Cada servicio de Google Cloud ofrece **APIs** para que **tu código** lo controle.
- **Google APIs Explorer**, dentro de la consola, muestra **qué APIs hay y en qué versiones**. Puedes **probarlas de forma interactiva**, incluso las que requieren autenticación.
- **Bibliotecas cliente** (de Cloud y de las APIs de Google) para no programar desde cero:
  **Java · Python · PHP · C# · Go · Node.js · Ruby · C++**

## 04 · 📱 App de Google Cloud

| Servicio | Qué puedes hacer desde la app |
|---|---|
| **Compute Engine** | Iniciar, detener, conectarte por **SSH** y ver los **registros** de cada instancia |
| **Cloud SQL** | Detener e iniciar instancias |
| **App Engine** | Administrar apps, ver errores, **revertir implementaciones** y cambiar la **división de tráfico** |
| **Facturación** | Información actualizada y **alertas** de proyectos que exceden el presupuesto |
| **Monitoreo** | **Gráficos personalizables**: CPU, red, solicitudes por segundo y errores del servidor |
| **Incidentes** | Alertas y gestión de incidentes |

## 🎯 Tips para el examen

- **`gcloud`** = CLI principal de Google Cloud. **`bq`** = CLI de **BigQuery**.
- **Cloud Shell**: VM **Debian**, **5 GB** persistentes en `$HOME`, herramientas **preinstaladas y autenticadas**. No necesitas instalar nada en tu equipo.
- Explorar o probar APIs → **APIs Explorer**.
- Controlar servicios desde tu propio código → **bibliotecas cliente**.
- "Gestionar desde el celular, ver facturación o alertas" → **app de Google Cloud**.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿Cuáles son las 4 formas de interactuar con Google Cloud?</b></summary>
<p>Consola de Google Cloud · Cloud SDK y Cloud Shell · APIs · App de Google Cloud.</p>
</details>

<details>
<summary><b>2. ¿Qué es la consola de Google Cloud?</b></summary>
<p>La <b>interfaz gráfica web</b> para implementar, escalar y diagnosticar, localizar recursos, ver su estado, fijar presupuestos y conectarse por SSH desde el navegador.</p>
</details>

<details>
<summary><b>3. ¿Cuál es la CLI principal de Google Cloud y cuál se usa para BigQuery?</b></summary>
<p><b><code>gcloud</code></b> es la principal; <b><code>bq</code></b> es la de BigQuery.</p>
</details>

<details>
<summary><b>4. ¿En qué sistema operativo se basa Cloud Shell y cuánto almacenamiento persistente tiene?</b></summary>
<p>Es una VM basada en <b>Debian</b> con <b>5 GB</b> de directorio de inicio persistente.</p>
</details>

<details>
<summary><b>5. ¿Qué ventaja tiene Cloud Shell frente a instalar el SDK en tu equipo?</b></summary>
<p><code>gcloud</code> y las demás utilidades ya están <b>instaladas, actualizadas y autenticadas</b>, y lo usas desde el navegador.</p>
</details>

<details>
<summary><b>6. ¿Qué herramienta muestra las APIs disponibles y permite probarlas?</b></summary>
<p><b>Google APIs Explorer</b>, dentro de la consola.</p>
</details>

<details>
<summary><b>7. ¿Qué ofrece Google para no tener que programar las llamadas a las APIs desde cero?</b></summary>
<p><b>Bibliotecas cliente</b> en Java, Python, PHP, C#, Go, Node.js, Ruby y C++.</p>
</details>

<details>
<summary><b>8. Escenario: estás fuera de la oficina y debes reiniciar una VM y revisar si un proyecto excede el presupuesto. ¿Qué usas?</b></summary>
<p>La <b>app de Google Cloud</b> en el celular.</p>
</details>

<details>
<summary><b>9. ¿Qué puedes hacer con App Engine desde la app móvil?</b></summary>
<p>Administrar aplicaciones, ver errores, <b>revertir implementaciones</b> y <b>cambiar la división de tráfico</b>.</p>
</details>

<details>
<summary><b>10. Escenario: quieres ejecutar comandos <code>gcloud</code> sin instalar nada en una laptop prestada. ¿Qué usas?</b></summary>
<p><b>Cloud Shell</b>, desde el navegador.</p>
</details>
