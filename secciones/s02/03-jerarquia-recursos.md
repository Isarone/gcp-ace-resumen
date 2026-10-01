---
title: Jerarquía de recursos en Google Cloud
seccion: 2
clase: 3
---

## 🧠 Idea clave

Google Cloud organiza todo en una **jerarquía de 4 niveles**. Esta jerarquía determina **cómo se gestionan y aplican las políticas**, y las políticas **se heredan hacia abajo**.

## 🌳 Los 4 niveles

```
🏢 Nodo de organización     ← nivel 4 (la cima): ej. empresa.com
 ├── 📁 Carpeta: Finanzas    ← nivel 3 (pueden anidarse subcarpetas)
 │    ├── 📦 Proyecto: app-movil      ← nivel 2
 │    │     ├── 🖥️ VM                 ← nivel 1: recursos
 │    │     └── 🪣 Bucket
 │    └── 📦 Proyecto: web
 │          └── 📊 Tabla BigQuery
 └── 📁 Carpeta: TI
      └── 📁 Subcarpeta: Dev
           └── 📦 Proyecto: pruebas
```

| Nivel | Elemento | Qué es |
|---|---|---|
| 1 | **Recursos** | VMs, buckets de Cloud Storage, tablas de BigQuery… **Siempre pertenecen a un proyecto.** |
| 2 | **Proyectos** | Base para habilitar y usar servicios. Contienen los recursos. |
| 3 | **Carpetas** | Agrupan proyectos y otras carpetas. Organizan políticas con más detalle. |
| 4 | **Nodo de organización** | La cima. Agrupa todas las carpetas, proyectos y recursos de la organización. |

## ⬇️ Herencia de políticas

- Las políticas se pueden definir a nivel de **organización, carpeta o proyecto**. Algunos servicios permiten aplicarlas también **sobre recursos específicos**.
- Las políticas **se heredan hacia abajo**: una política en una carpeta se aplica a **todos sus proyectos y recursos**.

> 📌 *Dato extra frecuente en el examen (no lo dijo la clase):* en IAM, la política efectiva es la **unión** de la del recurso y las heredadas. Un permiso otorgado en un nivel superior **no se puede quitar** en un nivel inferior.

## 📦 Proyectos (nivel 2)

**Qué se hace en un proyecto:** administrar **APIs**, habilitar **facturación**, agregar o quitar **colaboradores** y activar servicios.

- Cada proyecto es una **entidad independiente**, con sus propios propietarios y usuarios, y se **factura por separado**.
- Ejemplo: un proyecto para una **app móvil** y otro para una **plataforma web**. Cada uno tiene su equipo, sus recursos y su factura, y lo que hagas en uno **no afecta** al otro.

### 🏷️ Los 3 identificadores de un proyecto

| Atributo | ¿Único? | ¿Se puede cambiar? | ¿Quién lo define? |
|---|---|---|---|
| **ID del proyecto** | ✅ Único a nivel global | ❌ **Inmutable** | Se fija al crear el proyecto |
| **Nombre del proyecto** | ❌ No necesariamente | ✅ **Sí, cuando quieras** | Tú |
| **Número del proyecto** | ✅ Único | ❌ No | **Google**, uso interno |

> ⚠️ **Corrección:** la transcripción dice que Google asigna el **ID**. En realidad, el ID lo **eliges tú al crear el proyecto** (la consola te sugiere uno) y después **ya no se puede cambiar**. El que asigna Google es el **número**. El ID es el que usas en comandos, por ejemplo `gcloud config set project mi-proyecto-123`.

### 🛠️ Resource Manager

Herramienta para **gestionar proyectos de forma programática** (API **RPC** o **REST**):
- **Listar** los proyectos de una cuenta.
- **Crear**, **actualizar** y **eliminar** proyectos.
- **Recuperar** proyectos eliminados.

## 📁 Carpetas (nivel 3)

- Agrupan **proyectos**, **otras carpetas** o ambos.
- Sirven para estructurar la organización, por ejemplo **por departamentos**.
- Los recursos **heredan las políticas y permisos** de la carpeta.
- Ventajas:
  - Permiten **delegar derechos administrativos** y dar más autonomía a los equipos.
  - Evitan **duplicar configuraciones**: si dos proyectos son del mismo equipo, los pones en una carpeta y les aplicas la política una sola vez.
- ⚠️ **Para usar carpetas necesitas un nodo de organización.**

## 🏢 Nodo de organización (nivel 4)

- Es el recurso **más alto**. Las carpetas y los proyectos son sus **hijos**.
- **Roles especiales** a este nivel:

| Rol | Para qué |
|---|---|
| **Administrador de políticas de la organización** | Asegura que solo personas con privilegios modifiquen las políticas |
| **Creador de proyectos** | Controla **quién puede crear proyectos** y, por lo tanto, **gastar dinero** |

**¿Cómo se obtiene un nodo de organización?**

```
¿Tu empresa es cliente de Google Workspace?
 ├── Sí → los proyectos pertenecen AUTOMÁTICAMENTE al nodo de organización de tu dominio
 └── No → usa Cloud Identity (gestión de identidad y acceso de Google) para crearlo
```

Una vez creado, las personas del dominio siguen creando proyectos y cuentas de facturación como antes, y puedes ordenarlos en carpetas.

## 🎯 Tips para el examen

- Orden de arriba hacia abajo: **Organización → Carpetas → Proyectos → Recursos**.
- Las políticas **se heredan hacia abajo**. Para aplicar la misma política a varios proyectos, ponlos en una **carpeta**.
- **Sin nodo de organización no hay carpetas.**
- Para obtener el nodo de organización: **Google Workspace** o **Cloud Identity**.
- **ID del proyecto**: único global e inmutable. **Nombre**: editable. **Número**: lo asigna Google.
- Controlar quién crea proyectos → rol **Creador de proyectos** (*Project Creator*).
- Gestionar proyectos por API → **Resource Manager**.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿Cuáles son los 4 niveles de la jerarquía, de abajo hacia arriba?</b></summary>
<p>Recursos → Proyectos → Carpetas → Nodo de organización.</p>
</details>

<details>
<summary><b>2. ¿Puede existir un recurso (ej. una VM) fuera de un proyecto?</b></summary>
<p><b>No.</b> Todo recurso debe estar vinculado a un proyecto.</p>
</details>

<details>
<summary><b>3. Si aplicas una política a una carpeta, ¿a qué afecta?</b></summary>
<p>A <b>todos los proyectos, subcarpetas y recursos</b> dentro de ella, porque las políticas se heredan hacia abajo.</p>
</details>

<details>
<summary><b>4. ¿Cuáles son los 3 identificadores de un proyecto y cuál se puede cambiar?</b></summary>
<p>ID, nombre y número. Solo el <b>nombre</b> se puede cambiar. El ID es inmutable y único global; el número lo asigna Google.</p>
</details>

<details>
<summary><b>5. ¿Qué herramienta permite crear, listar, eliminar y recuperar proyectos de forma programática?</b></summary>
<p><b>Resource Manager</b>, mediante API RPC o REST.</p>
</details>

<details>
<summary><b>6. ¿Qué necesitas para poder usar carpetas?</b></summary>
<p>Un <b>nodo de organización</b>.</p>
</details>

<details>
<summary><b>7. ¿Cómo obtienes un nodo de organización si tu empresa no usa Google Workspace?</b></summary>
<p>Con <b>Cloud Identity</b>.</p>
</details>

<details>
<summary><b>8. Escenario: quieres evitar que cualquiera cree proyectos y gaste dinero. ¿Qué haces?</b></summary>
<p>Controlar quién tiene el rol de <b>Creador de proyectos</b> a nivel de organización.</p>
</details>

<details>
<summary><b>9. Escenario: dos proyectos del mismo equipo necesitan exactamente las mismas políticas. ¿Cómo evitas configurarlas dos veces?</b></summary>
<p>Ponlos en una <b>carpeta común</b> y aplica la política a la carpeta. Ambos la heredan.</p>
</details>

<details>
<summary><b>10. ¿Los proyectos de una app móvil y de una web en la misma organización comparten facturación y recursos?</b></summary>
<p><b>No.</b> Cada proyecto es independiente: tiene sus propios recursos y usuarios y se factura por separado.</p>
</details>
