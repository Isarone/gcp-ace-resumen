---
title: Creación y gestión de proyectos
seccion: 2
clase: 4
---

## 🧠 Idea clave

El **proyecto** es donde habilitas y usas los servicios: APIs, facturación, colaboradores… Al crearlo eliges **nombre, ID y ubicación**. **El ID es permanente.** Si lo eliminas, tienes **30 días para recuperarlo**.

## 🪪 Tarjeta del proyecto (Dashboard)

Muestra los 3 atributos clave: **nombre**, **número** e **ID**. Desde ahí también puedes **agregar personas** al proyecto con distintos **roles y permisos**, por ejemplo para ver datos, gestionar recursos o administrar configuraciones. Esto se verá en la clase de IAM.

## ➕ Crear un proyecto

**Dónde:** el **selector de proyecto** (arriba) → *Nuevo proyecto*, o ☰ → **IAM y administración** → *Crear proyecto*.

| Campo | Detalle |
|---|---|
| **Aviso de cuota** | Indica **cuántos proyectos puedes crear**. Si necesitas más: **pide un aumento de cuota** o **elimina proyectos** que no uses. |
| **Nombre** | Lo eliges tú (ej. `GCP Lab`). **Puede repetirse** y **cambiarse** cuando quieras. |
| **ID del proyecto** | **Único en todo Google Cloud.** Si el nombre es genérico, se sugiere uno con letras, números y guiones (ej. `gcp-lab-437512`). Puedes **editarlo** o **generar otro** con el ícono 🔄, pero **solo antes de crear**: luego es **permanente**. |
| **Ubicación** | No es física: es el **lugar lógico** en la jerarquía (organización o carpeta). |

```
Ubicación del proyecto
 ├── Con organización → se crea DENTRO de ella
 │                      y hereda sus políticas y permisos
 └── Sin organización → queda bajo tu cuenta personal de Google
                        (tú eres el único responsable)
```

Una vez creado, lo eliges en el **selector de proyecto** y ya puedes habilitar servicios, administrar APIs, activar facturación y gestionar colaboradores.

## 🗑️ Eliminar (cerrar) un proyecto

**Cómo:** *Configuración del proyecto* → **Cerrar** → escribes el **ID del proyecto** → **Cerrar**.

```
Cierras el proyecto
   → queda MARCADO para eliminación durante 30 DÍAS
       • no se puede usar
       • sus recursos (VMs, BD…) siguen existiendo y CUENTAN EN TU CUOTA
       • con facturación asociada, puede esperar al fin del ciclo de facturación
       • ✅ puedes RESTAURARLO
   → después de 30 días: se elimina PARA SIEMPRE
```

## ♻️ Restaurar un proyecto (dentro de los 30 días)

**Recursos pendientes de eliminación** → seleccionas el proyecto o proyectos → **Restablecer** → confirmas.

> 📌 *Extra, no visto en esta clase:* los equivalentes en la línea de comandos, útiles para el examen:
> ```bash
> gcloud projects create gcp-lab-437512 --name="GCP Lab"
> gcloud projects delete gcp-lab-437512     # lo marca para eliminación (30 días)
> gcloud projects undelete gcp-lab-437512   # lo restaura
> ```

## 🎯 Tips para el examen

- **ID del proyecto: único global y permanente.** Elígelo bien al crear el proyecto.
- **Nombre:** se puede repetir y cambiar.
- **Límite de proyectos** = cuota. Pide un aumento o elimina proyectos.
- Eliminar = **30 días** de periodo de recuperación. Durante ese tiempo los recursos **siguen contando en la cuota**.
- Proyecto creado **dentro de la organización** → hereda sus políticas.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿Desde dónde puedes crear un proyecto en la consola?</b></summary>
<p>Desde el <b>selector de proyecto</b> o desde <b>IAM y administración → Crear proyecto</b>.</p>
</details>

<details>
<summary><b>2. ¿Qué haces si llegaste al límite de proyectos que puedes crear?</b></summary>
<p>Solicitar un <b>aumento de cuota</b> o <b>eliminar proyectos</b> que ya no necesites.</p>
</details>

<details>
<summary><b>3. ¿Pueden dos proyectos tener el mismo nombre? ¿Y el mismo ID?</b></summary>
<p>El <b>nombre sí</b> se puede repetir. El <b>ID no</b>: es único en todo Google Cloud.</p>
</details>

<details>
<summary><b>4. ¿Cuándo puedes editar el ID del proyecto?</b></summary>
<p><b>Solo durante la creación.</b> Una vez creado, es permanente.</p>
</details>

<details>
<summary><b>5. ¿Qué significa la "ubicación" al crear un proyecto?</b></summary>
<p>El <b>lugar lógico</b> en la jerarquía (organización o carpeta) donde vivirá el proyecto. No es una ubicación física.</p>
</details>

<details>
<summary><b>6. ¿Qué pasa inmediatamente al eliminar un proyecto?</b></summary>
<p>Se <b>marca para eliminación durante 30 días</b>: no se puede usar, pero sus recursos siguen existiendo y cuentan en tu cuota. Se puede restaurar en ese plazo.</p>
</details>

<details>
<summary><b>7. ¿Qué dato debes escribir para confirmar el cierre de un proyecto?</b></summary>
<p>El <b>ID del proyecto</b>.</p>
</details>

<details>
<summary><b>8. Escenario: borraste un proyecto por error hace 10 días. ¿Puedes recuperarlo? ¿Cómo?</b></summary>
<p><b>Sí.</b> Ve a <b>Recursos pendientes de eliminación</b>, selecciona el proyecto y haz clic en <b>Restablecer</b>. Por CLI: <code>gcloud projects undelete</code>.</p>
</details>

<details>
<summary><b>9. Escenario: eliminaste proyectos para liberar cuota, pero aún no puedes crear nuevos. ¿Por qué?</b></summary>
<p>Porque durante los <b>30 días</b> de eliminación pendiente, sus recursos <b>siguen contando en la cuota</b>.</p>
</details>
