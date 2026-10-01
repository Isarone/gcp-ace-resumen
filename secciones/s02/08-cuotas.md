---
title: Evaluación de cuotas y solicitud de aumentos
seccion: 2
clase: 8
---

## 🧠 Idea clave

Las **cuotas** son **límites en la cantidad de recursos** que puedes usar. Protegen **a los usuarios y a la infraestructura** de Google Cloud, y existen para la mayoría de los servicios. Si necesitas más, **solicitas un aumento** y Google lo evalúa.

> Ejemplo: con una cuota de **5 VMs** no puedes lanzar una sexta hasta que te aprueben un aumento.

## 🔍 Ver tus cuotas

**Dónde:** **IAM y administración** → **Cuotas y límites del sistema** (*Quotas & System Limits*).

- **Filtra** por **servicio** (ej. `Compute`) o por **región**, por ejemplo con la dimensión `us-central1` (Iowa).
- Ej.: filtra por `instances` para ver cuántas VMs puedes lanzar en cada región.

Para cada cuota verás:

| Dato | Qué indica |
|---|---|
| **Valor / límite** | Cuánto puedes usar |
| **Uso actual y % de uso** | Cuánto llevas consumido |
| **¿Ajustable?** | Si **se puede pedir un aumento** o no |
| **Gráfico de uso** | Evolución del consumo |
| **Alertas de uso** | Notificación al superar un **umbral** que tú defines |

## ⬆️ Solicitar un aumento

```
Filtra la cuota (ej. instancias en us-central1)
  → selecciónala → "Editar"
  → nuevo valor + breve JUSTIFICACIÓN
  → acepta → enviar solicitud
  → Google la evalúa y responde al CORREO de tu cuenta
     (suele ser rápido si justificas bien la necesidad)
```

## 🎯 Tips para el examen

- **Error al crear un recurso por falta de cuota** → revisa *Cuotas* y **solicita un aumento**.
- Las cuotas pueden ser **por región**: la cuota de `us-central1` es distinta de la de `europe-west1`.
- No todas las cuotas son **ajustables**.
- Configura **alertas de uso de cuota** para anticiparte.
- (Clase 2.4) El **número de proyectos** que puedes crear también es una **cuota**.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿Qué es una cuota en Google Cloud?</b></summary>
<p>Un <b>límite en la cantidad de recursos</b> que puedes usar. Protege a los usuarios y a la infraestructura.</p>
</details>

<details>
<summary><b>2. ¿Dónde ves tus cuotas en la consola?</b></summary>
<p>En <b>IAM y administración → Cuotas y límites del sistema</b>.</p>
</details>

<details>
<summary><b>3. ¿Cómo filtras las cuotas?</b></summary>
<p>Por <b>servicio</b> (ej. Compute) o por <b>región</b> (ej. <code>us-central1</code>).</p>
</details>

<details>
<summary><b>4. ¿Qué incluyes al pedir un aumento?</b></summary>
<p>El <b>nuevo valor</b> y una <b>justificación</b> de por qué lo necesitas.</p>
</details>

<details>
<summary><b>5. ¿Cómo te enteras de la respuesta de Google?</b></summary>
<p>Por <b>correo electrónico</b>, al email registrado en tu cuenta.</p>
</details>

<details>
<summary><b>6. Escenario: necesitas lanzar 20 VMs en <code>us-central1</code> y solo te deja crear 8. ¿Qué haces?</b></summary>
<p>Ve a <b>Cuotas</b>, filtra la cuota de instancias en <code>us-central1</code>, haz clic en <b>Editar</b> y <b>solicita el aumento</b> con justificación.</p>
</details>

<details>
<summary><b>7. ¿Cómo te anticipas a quedarte sin cuota?</b></summary>
<p>Configurando <b>alertas de uso</b> para que te notifiquen al llegar a un umbral.</p>
</details>
