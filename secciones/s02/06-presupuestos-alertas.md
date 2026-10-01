---
title: Configuración de presupuestos y alertas de facturación
seccion: 2
clase: 6
---

## 🧠 Idea clave

Un **presupuesto** (*budget*) compara los **cargos reales** con lo que **planificaste gastar**. Además configuras **alertas** que avisan cuando el gasto supera ciertos porcentajes, por ejemplo 50 %, 90 % o 100 %.

> ⚠️ *Dato clave para el examen (no lo dijo la clase de forma explícita):* **un presupuesto NO detiene ni limita el gasto**, solo **notifica**. Para frenar costos de forma automática necesitas **automatizar una acción** con Pub/Sub, por ejemplo apagar VMs o desactivar la facturación.

## 🎯 ¿A qué se puede aplicar un presupuesto?

| Alcance | Ejemplo de la clase |
|---|---|
| **Cuenta de facturación completa** | Presupuesto general de la cuenta |
| **Proyectos específicos** | USD 500 para el proyecto de BigQuery y otro aparte para el de App Engine |
| **Servicios concretos** | Solo **Compute Engine** |
| **Recursos con etiquetas** | USD 1 000 solo para los recursos etiquetados como **producción**, sin incluir **desarrollo** |

## 🪜 Crear un presupuesto (3 pasos)

**Dónde:** busca **Billing** → *Billing accounts* → menú lateral → **Presupuestos y alertas** → **Crear presupuesto**.

### Paso 1 · Alcance

- **Nombre** (ej. `Budget GCP`).
- **Intervalo de tiempo:**

| Intervalo | Cuándo usarlo |
|---|---|
| **Mensual** | Proyecto de varios meses que quieres controlar mes a mes (el elegido en la clase) |
| **Trimestral** | Proyecto por fases a lo largo del año: planificación, desarrollo, lanzamiento |
| **Anual** | Uso constante todo el año |
| **Rango personalizado** | Proyecto con fechas fijas, ej. **1 de octubre al 31 de diciembre** |

- **Proyectos** y **servicios** a los que aplica: todos o algunos específicos.
- **Créditos:** incluir créditos promocionales y descuentos en el cálculo.

### Paso 2 · Importe

| Tipo | Qué hace |
|---|---|
| **Importe especificado** | Monto **fijo** por periodo (ej. **USD 50 al mes**) |
| **Gasto del último periodo** | Se **adapta a tus gastos reales** según tu consumo reciente |

### Paso 3 · Acciones (alertas)

- Umbrales **predeterminados: 50 %, 90 % y 100 %**. Puedes modificarlos, agregar otros o quitarlos.
- **¿Cuándo se activa?**

| Tipo | Se dispara cuando… | Ejemplo con presupuesto de USD 50 |
|---|---|---|
| **Real** | El **costo acumulado** del periodo supera el umbral | Alerta del 50 % → avisa al gastar **USD 25** |
| **Previsto** | Se **pronostica** que al final del periodo superarás el umbral | Alerta del 110 % → avisa si se prevé gastar **más de USD 55** |

- **Notificaciones:**
  - 📧 Correo a **administradores de facturación** y **usuarios** de la cuenta (el elegido en la clase).
  - 📟 **Canales de notificación de Cloud Monitoring.**
  - 📨 **Pub/Sub**, para **automatizar respuestas**.

## 🤖 Automatizar con Pub/Sub

**Pub/Sub** es un servicio de **mensajería asíncrona** entre sistemas. Lo verás más adelante en el curso. (La transcripción lo escribe "Potshot" o "podcast".)

```
Gasto llega al 90 %
   → el presupuesto publica un mensaje en un tema de Pub/Sub
      → un proceso suscrito APAGA las VMs no críticas
         → evitas pasarte del presupuesto SIN intervención manual
```

## 🎯 Tips para el examen

- **Presupuesto = monitoreo y alertas. NO es un tope de gasto.**
- Umbrales por defecto: **50 %, 90 % y 100 %**.
- **Real** = lo ya gastado. **Previsto** = proyección al final del periodo.
- ¿Respuesta **automática** al alcanzar un umbral? → **Pub/Sub** + una acción programada.
- Alcance flexible: cuenta, **proyectos**, **servicios** o **etiquetas**.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿Qué hace un presupuesto de facturación?</b></summary>
<p>Compara los cargos reales con lo planificado y envía <b>alertas</b> al superar umbrales. <b>No detiene el gasto</b> por sí solo.</p>
</details>

<details>
<summary><b>2. ¿A qué niveles se puede aplicar un presupuesto?</b></summary>
<p>A la <b>cuenta de facturación</b> completa, a <b>proyectos</b>, a <b>servicios</b> específicos o a recursos con <b>etiquetas</b>.</p>
</details>

<details>
<summary><b>3. ¿Cuáles son los umbrales de alerta predeterminados?</b></summary>
<p><b>50 %, 90 % y 100 %</b> del importe del presupuesto.</p>
</details>

<details>
<summary><b>4. Presupuesto de USD 50 y alerta real del 50 %. ¿Cuándo llega la alerta?</b></summary>
<p>Cuando el gasto acumulado llega a <b>USD 25</b>.</p>
</details>

<details>
<summary><b>5. ¿Qué diferencia hay entre una alerta "real" y una "prevista"?</b></summary>
<p><b>Real</b>: se dispara con el costo ya acumulado. <b>Prevista</b>: se dispara cuando se <b>pronostica</b> que al final del periodo superarás el umbral.</p>
</details>

<details>
<summary><b>6. ¿Qué intervalo eliges para un proyecto que dura del 1 de octubre al 31 de diciembre?</b></summary>
<p><b>Rango personalizado</b> con esas fechas.</p>
</details>

<details>
<summary><b>7. ¿Qué diferencia hay entre "importe especificado" y "gasto del último periodo"?</b></summary>
<p>El primero es un monto <b>fijo</b>. El segundo se <b>adapta</b> a lo que gastaste recientemente.</p>
</details>

<details>
<summary><b>8. Escenario: al llegar al 90 % del presupuesto quieres apagar automáticamente las VMs no críticas. ¿Qué usas?</b></summary>
<p>Conectar el presupuesto a <b>Pub/Sub</b> y que un proceso suscrito apague las VMs.</p>
</details>

<details>
<summary><b>9. Escenario: quieres controlar solo el gasto de producción, sin incluir desarrollo. ¿Cómo lo haces?</b></summary>
<p>Con un presupuesto filtrado por la <b>etiqueta</b> de producción.</p>
</details>
