---
title: Cuentas de facturación
seccion: 2
clase: 5
---

## 🧠 Idea clave

Una **cuenta de facturación de Cloud** (*Cloud Billing account*) define **quién paga** por un conjunto de recursos. Es como **tu tarjeta de crédito** en la plataforma. Se vincula a **uno o más proyectos**, y los costos de cada proyecto se cargan a su cuenta de facturación.

> ⚠️ **Corrección (importante para el examen):** la clase dice que un proyecto puede vincularse a "una o varias" cuentas de facturación. En realidad, **un proyecto se vincula a UNA sola cuenta de facturación a la vez**. **Una cuenta de facturación sí puede pagar MUCHOS proyectos.**

```
💳 Cuenta de facturación A ──┬── 📦 Proyecto app-movil
                             ├── 📦 Proyecto web
                             └── 📦 Proyecto pruebas
💳 Cuenta de facturación B ──── 📦 Proyecto cliente-x
(1 cuenta → N proyectos   ·   1 proyecto → 1 cuenta)
```

## ❓ ¿Por qué necesitas una?

- **Sin cuenta de facturación vinculada, no puedes usar servicios de pago** (ej. lanzar VMs).
- Se necesita **incluso en la prueba gratuita**: los costos se registran en esa cuenta y se **cubren primero con los USD 300**.
- Cuando se acaba el crédito, o si usas algo fuera de la capa gratuita → se **cobra a la cuenta** según las tarifas de Google Cloud.
- El **perfil de pagos** que creaste al registrarte en la prueba **cuenta como tu cuenta de facturación**.

## ➕ Crear una cuenta de facturación

1. Busca **"Billing"** → **Billing accounts** (*Cuentas de facturación*).
2. **Administrar cuentas de facturación** → **Agregar / Crear cuenta de facturación**.
3. **Nombre** y **país** → Continuar.
4. **Perfil de pagos:** usa el existente o **Crea un perfil de pagos** nuevo, con tarjeta de crédito o débito.
5. **Activar facturación**.
6. **Verificación de la tarjeta:**
   - Google hace un **cargo temporal pequeño** (≈ USD 1). **No es un cobro real.**
   - **Obtener código** → buscas el cargo en tu banco → ingresas el **código de 6 dígitos** → **Verificar**.
7. Al hacer clic en la cuenta, se abre el **panel de administración de costos**.

## 🔗 Vincular un proyecto

**Administrar cuenta de facturación** → pestaña **Mis proyectos** → la columna *Billing account* dice "**Facturación inhabilitada**" (el proyecto no puede lanzar recursos) → **⋮** → **Cambiar facturación** → eliges la cuenta → **Establecer cuenta**.

Desde ese momento, todos los cargos del proyecto van a esa cuenta.

## ⛔ Inhabilitar la facturación de un proyecto

**⋮** → **Inhabilitar facturación** → confirmas.

| ✅ Qué logra | ⚠️ Qué NO evita |
|---|---|
| **Detiene los cargos futuros** del proyecto | **Sigues siendo responsable de los cargos pendientes** (lo que ya usaste antes de inhabilitarla) |
| Evita gastos inesperados en proyectos que ya no usas | |

## 🔒 Cerrar una cuenta de facturación

**Administrar cuentas de facturación** → **Cerrar cuenta de facturación** → escribes "**Cerrar**".

Cuándo hacerlo: terminaste todos sus proyectos y no la usarás más, para mantener tus finanzas ordenadas.

> 📌 *Extra, no visto en esta clase, frecuente en el examen:*
> - **Administrador de cuentas de facturación** (*Billing Account Administrator*): gestiona la cuenta.
> - **Usuario de cuentas de facturación** (*Billing Account User*): puede **vincular proyectos** a la cuenta.
> - Por CLI: `gcloud billing projects link ID_PROYECTO --billing-account=XXXXXX-XXXXXX-XXXXXX`

## 🎯 Tips para el examen

- **1 proyecto → 1 cuenta de facturación. 1 cuenta → N proyectos.**
- **Sin facturación vinculada, no hay recursos de pago** (ej. no puedes crear VMs).
- Inhabilitar la facturación **detiene los cargos futuros**, pero **no borra la deuda pendiente**.
- La verificación de tarjeta es un **cargo temporal** con un **código de 6 dígitos**.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿Para qué sirve una cuenta de facturación de Cloud?</b></summary>
<p>Define <b>quién paga</b> por los recursos. Los costos de los proyectos vinculados se cargan a ella.</p>
</details>

<details>
<summary><b>2. ¿A cuántas cuentas de facturación puede estar vinculado un proyecto a la vez?</b></summary>
<p>A <b>una sola</b>. En cambio, una cuenta de facturación puede pagar <b>muchos proyectos</b>.</p>
</details>

<details>
<summary><b>3. ¿Se necesita cuenta de facturación en la prueba gratuita?</b></summary>
<p><b>Sí.</b> Los costos se registran en ella y primero se cubren con los USD 300. El perfil de pagos creado al registrarte cuenta como cuenta de facturación.</p>
</details>

<details>
<summary><b>4. ¿Cómo verifica Google tu tarjeta?</b></summary>
<p>Hace un <b>cargo temporal pequeño</b> (≈ USD 1, no es un cobro real). Ingresas el <b>código de 6 dígitos</b> que aparece en tu banco.</p>
</details>

<details>
<summary><b>5. Escenario: intentas crear una VM y no te deja; el proyecto dice "Facturación inhabilitada". ¿Qué haces?</b></summary>
<p><b>Vincular una cuenta de facturación</b>: Mis proyectos → ⋮ → Cambiar facturación → elegir la cuenta → Establecer cuenta.</p>
</details>

<details>
<summary><b>6. Si inhabilitas la facturación de un proyecto, ¿te libras de pagar lo ya consumido?</b></summary>
<p><b>No.</b> Solo se detienen los cargos <b>futuros</b>; los cargos pendientes se siguen debiendo.</p>
</details>

<details>
<summary><b>7. ¿Cómo confirmas el cierre de una cuenta de facturación?</b></summary>
<p>Escribiendo <b>"Cerrar"</b> en la confirmación.</p>
</details>

<details>
<summary><b>8. Escenario: tu empresa quiere que todos los proyectos de un departamento se paguen con la misma tarjeta. ¿Es posible?</b></summary>
<p><b>Sí.</b> Vincula todos esos proyectos a la <b>misma cuenta de facturación</b>.</p>
</details>
