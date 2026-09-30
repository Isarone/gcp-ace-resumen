---
title: Resumen GCP – Associate Cloud Engineer
---

# ☁️ Resumen: Google Cloud Associate Cloud Engineer

> Apuntes del curso en Udemy, pensados para repasar desde el celular.
> Toca cada **▶ pregunta** para ver la respuesta.

## 📚 Índice {#indice}

1. [Sección 1 – Introducción: modelos de servicio en la nube](#seccion-1)

---

## Sección 1 – Introducción: modelos de servicio en la nube {#seccion-1}

### 🧠 Idea clave

**"Como servicio" (as a Service)** = un tercero te ofrece el modelo en la nube. **No compras ni administras** hardware, software ni centro de datos: pagas una **suscripción** o **por consumo**, *on demand*, vía internet.

### 🧱 Los modelos (de más control a menos control)

| Modelo | ¿Qué te dan? | Tú te encargas de… | Cómo pagas | Ejemplo en GCP |
|---|---|---|---|---|
| **IaaS** – Infraestructura | Cómputo, almacenamiento y redes virtuales (como un data center físico) | SO, runtime, app, datos | Por recursos **asignados** (por adelantado) | **Compute Engine** |
| **CaaS** – Contenedores | Plataforma para correr contenedores / microservicios | Contenedores y app | Según uso de la plataforma | (GKE, Cloud Run) |
| **PaaS** – Plataforma | Tu código se vincula a librerías que resuelven la infraestructura | Solo el código / lógica de la app | Por recursos **realmente usados** | **App Engine** |
| **Serverless** | Ejecutas código sin configurar servidores | Solo el código | Pago por uso | **Cloud Functions**, **Cloud Run** |
| **SaaS** – Software | La aplicación completa, lista para usar | Nada técnico; solo la usas | Suscripción | **Gmail, Docs, Drive** (Google Workspace) |

### 🔍 Detalle de cada uno

- **IaaS**: recursos de infraestructura bajo demanda (VMs, discos, redes). Máximo control, máxima responsabilidad.
- **PaaS**: te enfocas en la **lógica de la aplicación**; la plataforma provee lo que la app necesita.
- **CaaS**: surge por la adopción de **contenedores y microservicios**.
- **Serverless**: el siguiente paso de la evolución. **Cero gestión de infraestructura**.
  - **Cloud Functions** → código **basado en eventos**, pago por uso.
  - **Cloud Run** → **microservicios en contenedores** en un entorno totalmente gestionado.
- **SaaS**: toda la pila de aplicación. **No se instala** en tu equipo; se consume por internet.

### 📈 Tendencia de la nube

```
On-premise → IaaS → PaaS → Servicios gestionados → Serverless
   (más control, más trabajo)      →      (menos gestión, más foco en el negocio)
```

Usar **servicios gestionados** = menos tiempo/dinero en infraestructura → productos más **rápidos y confiables**.

### 🎯 Tips para el examen

- **IaaS paga lo asignado**, **PaaS paga lo usado**. ¡Pregunta clásica!
- Compute Engine = IaaS · App Engine = PaaS · Cloud Functions / Cloud Run = Serverless · Workspace = SaaS.
- Si el enunciado dice *"sin gestionar servidores"* o *"basado en eventos"* → piensa en **Serverless**.
- Si dice *"control total del SO / VM"* → **Compute Engine**.

### ✅ Autoevaluación

<details>
<summary><b>1. ¿Qué significa "como servicio"?</b></summary>
<p>Que un tercero ofrece el modelo en la nube: no compras ni administras hardware/software; pagas suscripción o por consumo, bajo demanda vía internet.</p>
</details>

<details>
<summary><b>2. ¿Qué servicio de GCP es un ejemplo de IaaS?</b></summary>
<p><b>Compute Engine</b>.</p>
</details>

<details>
<summary><b>3. ¿Qué servicio de GCP es un ejemplo de PaaS?</b></summary>
<p><b>App Engine</b>.</p>
</details>

<details>
<summary><b>4. ¿En qué se diferencia el cobro de IaaS vs PaaS?</b></summary>
<p>IaaS: pagas los recursos que <b>asignas por adelantado</b>. PaaS: pagas los recursos que <b>realmente usas</b>.</p>
</details>

<details>
<summary><b>5. ¿Cuáles son las tecnologías serverless de Google mencionadas y para qué sirve cada una?</b></summary>
<p><b>Cloud Functions</b>: código basado en eventos, pago por uso.<br><b>Cloud Run</b>: microservicios en contenedores en un entorno totalmente gestionado.</p>
</details>

<details>
<summary><b>6. ¿Por qué apareció CaaS?</b></summary>
<p>Por la adopción creciente de arquitecturas de <b>contenedores y microservicios</b>.</p>
</details>

<details>
<summary><b>7. Da tres ejemplos de SaaS de Google.</b></summary>
<p>Gmail, Google Docs y Google Drive (parte de <b>Google Workspace</b>).</p>
</details>

<details>
<summary><b>8. ¿Qué ventaja da usar servicios gestionados?</b></summary>
<p>Menos tiempo y dinero manteniendo infraestructura → más foco en objetivos de negocio y entregas más rápidas y confiables.</p>
</details>

<details>
<summary><b>9. Escenario: quieres ejecutar código cuando se sube un archivo a un bucket, sin administrar servidores. ¿Qué usas?</b></summary>
<p><b>Cloud Functions</b> (serverless, basado en eventos).</p>
</details>

[⬆️ Volver al índice](#indice)

---
