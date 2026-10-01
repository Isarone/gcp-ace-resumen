---
title: Explorando la consola de GCP
seccion: 2
clase: 2
---

## 🧠 Idea clave

La **consola de Google Cloud** es la interfaz web para **gestionar, monitorear y agregar** recursos. Su punto de partida es el **Dashboard**: una vista general del estado de tus proyectos y de los recursos activados.

## 📊 Dashboard (panel principal)

- Está formado por **tarjetas** (*cards*), cada una con una vista rápida de un aspecto del proyecto.
- **Personalizable**: puedes **mover**, **ocultar** o **modificar** tarjetas y luego **Guardar**.
  - Ejemplo de la clase: ocultar "Primeros pasos", "Recursos", "Noticias" y "Documentación", y dejar "**Instancias de cómputo**".
- Junto al Dashboard hay dos pestañas:

| Pestaña | Qué muestra |
|---|---|
| **Actividad** | Historial del proyecto: cambios recientes, despliegues, etc. (se relaciona con **observabilidad**) |
| **Recomendaciones** | Sugerencias según tu uso: **optimización de costos**, **seguridad** y **rendimiento** |

## 🔝 Barra superior

| Ubicación | Elemento | Para qué sirve |
|---|---|---|
| Izquierda | **☰ Menú de navegación** | Acceso a todos los productos |
| Izquierda | **Selector de proyecto** | Elegir el proyecto donde trabajas y despliegas recursos |
| Centro | **🔍 Barra de búsqueda** | Buscar **recursos, servicios o documentación** (ej. una VM o una API) y llegar directo |
| Derecha | **Cuenta de Google** | La cuenta con sesión iniciada |
| Derecha | **⚙️ Configuración** | Preferencias de cuenta o proyecto, notificaciones, **idioma, región y formato de fecha y hora** |
| Derecha | **❓ Soporte** | Ayuda del equipo de Google Cloud |
| Derecha | **🔔 Notificaciones** | Eventos importantes: problemas con servicios, despliegues, etc. |
| Derecha | **>_ Cloud Shell** | Terminal interactiva **en el navegador** (`gcloud`, `kubectl`…) |
| Derecha | **🎁 Capa gratuita** | Resumen de recursos que **aún te quedan** en el nivel gratuito |
| Derecha | **✨ Gemini** | Capacidades de **IA**: modelos preentrenados y herramientas para crear modelos (requiere habilitar su API) |

## 📌 Menú lateral personalizable

```
☰ Menú → "Ver todos los productos"
   → servicios organizados por categorías
   → fija (📌) los que más usas: IAM, Compute Engine, Cloud Storage…
   → aparecen como favoritos en el menú lateral
```

## 🎯 Tips para el examen

- **Selector de proyecto** = en qué proyecto estás trabajando. Revísalo siempre antes de crear recursos.
- **Recomendaciones** = sugerencias de costo, seguridad y rendimiento.
- **Actividad** = historial de cambios del proyecto.
- **Cloud Shell** se abre desde la consola, sin instalar nada.
- **Icono de capa gratuita** = ver cuánto te queda del nivel gratuito y evitar costos inesperados.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿Qué es el Dashboard de la consola?</b></summary>
<p>El panel principal: una vista general del estado de tus proyectos y recursos, organizada en <b>tarjetas personalizables</b>.</p>
</details>

<details>
<summary><b>2. ¿Qué puedes hacer con las tarjetas del Dashboard?</b></summary>
<p>Moverlas, ocultarlas o modificarlas, y luego guardar los cambios.</p>
</details>

<details>
<summary><b>3. ¿Qué diferencia hay entre las pestañas Actividad y Recomendaciones?</b></summary>
<p><b>Actividad</b>: historial de cambios y despliegues. <b>Recomendaciones</b>: sugerencias de costo, seguridad y rendimiento.</p>
</details>

<details>
<summary><b>4. ¿Qué puedes buscar con la barra de búsqueda?</b></summary>
<p>Cualquier <b>recurso, servicio o documentación</b>, por ejemplo una VM o una API.</p>
</details>

<details>
<summary><b>5. ¿Dónde cambias el idioma y el formato de fecha y hora?</b></summary>
<p>En el icono de <b>⚙️ Configuración</b>.</p>
</details>

<details>
<summary><b>6. ¿Para qué sirve el icono de la capa gratuita?</b></summary>
<p>Para ver un resumen de los recursos que <b>aún tienes disponibles</b> en el nivel gratuito y evitar costos inesperados.</p>
</details>

<details>
<summary><b>7. ¿Cómo fijas servicios en el menú lateral?</b></summary>
<p>☰ → <b>Ver todos los productos</b> → marcas (📌) los servicios que quieres como favoritos.</p>
</details>

<details>
<summary><b>8. Escenario: creaste una VM y no la encuentras. ¿Qué revisas primero?</b></summary>
<p>El <b>selector de proyecto</b>: probablemente estás viendo otro proyecto. También puedes usar la <b>barra de búsqueda</b>.</p>
</details>
