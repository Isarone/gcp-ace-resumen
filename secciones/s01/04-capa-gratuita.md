---
title: Capa gratuita de Google Cloud
seccion: 1
clase: 4
---

## 🧠 Idea clave

Google Cloud ofrece **dos tipos de recursos gratuitos** para explorar, aprender o desarrollar sin preocuparte por los costos al inicio.

## 🎁 Los 2 tipos de recursos gratuitos

| | **Prueba gratuita** (*Free Trial*) | **Nivel gratuito** (*Free Tier*) |
|---|---|---|
| **Qué es** | **USD 300 en créditos** | Productos con **cuotas mensuales limitadas** |
| **Para quién** | Solo **usuarios nuevos** | **Cualquier usuario** |
| **Duración** | **90 días** (o hasta agotar el crédito) | **Sin fecha de expiración** (permanente) |
| **Qué cubre** | Casi cualquier servicio: VMs, almacenamiento, bases de datos, incluso modelos de IA | Solo ciertos productos, con límites |

> 💡 Durante la prueba **no te cobran** ni te obligan a un plan de pago. Google **te avisa antes** de hacer cualquier cobro.

## 🧾 Ejemplos del nivel gratuito permanente

- **Compute Engine**: VMs gratis **solo** con un **tipo de instancia**, una **configuración** y unas **regiones específicas**.
  - ❌ No puedes agregar **GPU**.
  - ❌ No puedes usar **Windows Server**.
- **Cloud Storage**: hasta **5 GB al mes** en la clase **Standard**.
- Y otros servicios listados en la documentación de Google Cloud.

> 📌 *Dato de la documentación oficial (no lo dijo la clase):* la VM gratuita es una **e2-micro** en `us-west1`, `us-central1` o `us-east1`. Los límites pueden cambiar, así que revisa la página oficial del Free Tier.

## ⏳ ¿Qué pasa al terminar los 90 días o el crédito?

```
Crédito agotado o pasan 90 días
   → tu cuenta NO se desactiva automáticamente
   → decides si la ACTUALIZAS a cuenta paga
        ├── Sí: sigues usando todos los servicios (pagando)
        └── No: los productos del nivel gratuito siguen disponibles sin costo
```

## 🎯 Tips para el examen

- **USD 300 · 90 días · solo usuarios nuevos** = prueba gratuita.
- **Nivel gratuito** = permanente, para todos, con cuotas mensuales.
- La VM gratuita tiene restricciones: tipo de instancia, región, sin GPU, sin Windows.
- Al terminar la prueba **no hay cobro automático**: tú decides si pasas a cuenta paga.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿Cuáles son los dos tipos de recursos gratuitos de Google Cloud?</b></summary>
<p>1) <b>Crédito de USD 300 por 90 días</b> para usuarios nuevos. 2) <b>Productos del nivel gratuito</b> con cuotas mensuales, sin expiración.</p>
</details>

<details>
<summary><b>2. ¿Cuánto dura el crédito inicial y cuánto es?</b></summary>
<p><b>USD 300</b> durante <b>90 días</b>.</p>
</details>

<details>
<summary><b>3. ¿El nivel gratuito tiene fecha de expiración?</b></summary>
<p><b>No.</b> Está disponible para cualquier usuario, con cuotas mensuales limitadas.</p>
</details>

<details>
<summary><b>4. ¿Qué pasa con tu cuenta cuando se acaba el crédito?</b></summary>
<p><b>No se desactiva automáticamente.</b> Decides si la actualizas a cuenta paga; si no lo haces, los productos del nivel gratuito siguen disponibles sin costo.</p>
</details>

<details>
<summary><b>5. ¿Google te cobra automáticamente al terminar la prueba?</b></summary>
<p><b>No.</b> Te avisa antes de cualquier cobro y no te obliga a comprometerte con un plan de pago.</p>
</details>

<details>
<summary><b>6. Menciona dos limitaciones de la VM gratuita de Compute Engine.</b></summary>
<p>Solo un tipo de instancia y configuración en regiones específicas; <b>sin GPU</b>; <b>sin Windows Server</b>.</p>
</details>

<details>
<summary><b>7. ¿Cuánto almacenamiento gratuito mensual da Cloud Storage y en qué clase?</b></summary>
<p>Hasta <b>5 GB</b> al mes en la clase <b>Standard</b>.</p>
</details>

<details>
<summary><b>8. Escenario: quieres una VM gratis con Windows Server y una GPU para entrenar un modelo. ¿Entra en el nivel gratuito?</b></summary>
<p><b>No.</b> El nivel gratuito no permite GPU ni Windows Server. Podrías usar los <b>USD 300 de crédito</b> de la prueba.</p>
</details>
