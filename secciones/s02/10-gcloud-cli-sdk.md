---
title: Instalación y configuración de Google Cloud CLI y SDK de Cloud
seccion: 2
clase: 10
---

## 🧠 Idea clave

El **SDK de Cloud**, hoy llamado **Google Cloud CLI**, permite manejar GCP **desde la terminal** con `gcloud`. Es ideal para **automatizar tareas** y desplegar rápido. Funciona en **Linux, macOS y Windows**. Con las **configuraciones** puedes cambiar de un proyecto a otro sin mezclar ajustes.

## 📥 Instalación

**Requisitos según la clase:**
- **Python** instalado.
- **Java** solo si vas a usar **App Engine con Java**.

> ⚠️ *Dato desactualizado en la clase:* menciona Python 3.5–3.7 o 2.7. Las versiones actuales de gcloud requieren **Python 3 reciente**, y los instaladores de Windows y macOS ya **incluyen Python**. Revisa los requisitos vigentes en la documentación oficial.

**Pasos en Windows:**
1. Ve a **cloud.google.com/sdk** → **Instalar Google Cloud CLI**.
2. **Descargar el instalador** → ejecútalo → acepta los términos → *Solo para mí* → **Instalar**.
3. Al terminar, deja marcado **"Iniciar Google Cloud SDK y ejecutar `gcloud init`"**.

## ⚙️ `gcloud init`: configuración inicial

A partir de aquí el proceso es **igual en todos los sistemas operativos**:

```
gcloud init
  1. ¿Iniciar sesión con tu cuenta de Google? → Y
     → se abre el navegador → inicias sesión → "Permitir"
  2. Eliges el PROYECTO con el que vas a trabajar
  3. (Opcional) región y zona predeterminadas para Compute → puedes decir que no
  ✅ SDK listo
```

## ⌨️ Comandos básicos

| Comando | Qué hace |
|---|---|
| `gcloud --help` | Lista de comandos y opciones |
| `gcloud auth list` | **Cuentas** con credenciales guardadas en el equipo (la transcripción dice "gcloud list") |
| `gcloud info` | Información de la **instalación** y de la **configuración activa** |
| `gcloud projects list` | Lista tus proyectos con su **nombre e ID** |

## 🧩 Componentes

| Acción | Comando |
|---|---|
| Ver instalados y disponibles | `gcloud components list` |
| Instalar uno (ej. App Engine Java) | `gcloud components install app-engine-java` |
| Actualizar todos | `gcloud components update` |
| Eliminar uno | `gcloud components remove app-engine-java` |

Al instalar uno, se muestran también sus **dependencias**, que se instalan junto con él.

## 🔀 Configuraciones (*configurations*)

Una **configuración** es un conjunto de ajustes con nombre: **proyecto**, **cuenta**, región y zona… Sirve para trabajar con **varios proyectos** desde la misma máquina.

```bash
# Crear (y ACTIVAR automáticamente) una configuración
gcloud config configurations create gcp-lab-025
gcloud config configurations create gcp-lab-europe   # ahora la activa es esta

# Cambiar a otra configuración
gcloud config configurations activate gcp-lab-025

# Ver todas (la columna IS_ACTIVE marca la actual)
gcloud config configurations list
```

**Ejemplo de la clase:** con `gcp-lab-europe` activa, una VM creada por comando (`gcloud compute instances create …`) se crea **solo en ese proyecto**. Al activar `gcp-lab-025`, los comandos siguientes afectan **solo a ese otro proyecto**. Los proyectos **no comparten recursos automáticamente**.

> 📌 *Extra (no lo dijo la clase):* una configuración recién creada está **vacía**. Asígnale proyecto, cuenta, etc. con `gcloud config set`:
> ```bash
> gcloud config set project gcp-lab-025
> gcloud config set account tu-correo@gmail.com
> gcloud config set compute/region us-central1
> gcloud config set compute/zone us-central1-a
> gcloud config list          # ver los ajustes de la configuración activa
> ```

## 🎯 Tips para el examen

- **`gcloud init`** = asistente inicial: login, proyecto y región/zona por defecto.
- **`gcloud auth list`** = qué cuentas están autenticadas.
- **`gcloud config configurations create | activate | list`** = manejar varios proyectos o entornos.
- **`gcloud config set project ID`** = cambiar el proyecto de la configuración activa. Se usa el **ID**, no el nombre.
- **`gcloud components install | update | remove`** = gestionar componentes del SDK.
- Al **crear** una configuración, esta **queda activa** automáticamente.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿En qué sistemas operativos funciona el SDK de Cloud?</b></summary>
<p><b>Linux, macOS y Windows.</b></p>
</details>

<details>
<summary><b>2. ¿Qué hace <code>gcloud init</code>?</b></summary>
<p>Inicia sesión con tu cuenta de Google, te deja <b>elegir el proyecto</b> y, opcionalmente, la <b>región y zona</b> predeterminadas.</p>
</details>

<details>
<summary><b>3. ¿Qué comando muestra las cuentas autenticadas en tu equipo?</b></summary>
<p><code>gcloud auth list</code></p>
</details>

<details>
<summary><b>4. ¿Qué comando muestra información de la instalación y de la configuración activa?</b></summary>
<p><code>gcloud info</code></p>
</details>

<details>
<summary><b>5. ¿Cómo instalas, actualizas y eliminas componentes?</b></summary>
<p><code>gcloud components install NOMBRE</code>, <code>gcloud components update</code> y <code>gcloud components remove NOMBRE</code>.</p>
</details>

<details>
<summary><b>6. ¿Para qué sirven las configuraciones de gcloud?</b></summary>
<p>Para guardar ajustes con nombre (proyecto, cuenta, región…) y <b>cambiar rápido entre proyectos</b> sin mezclarlos.</p>
</details>

<details>
<summary><b>7. Creas la configuración "europe" justo después de "lab". ¿Cuál queda activa?</b></summary>
<p><b>"europe"</b>: al crear una configuración, esta se activa automáticamente.</p>
</details>

<details>
<summary><b>8. ¿Cómo sabes cuál es la configuración activa?</b></summary>
<p>Con <code>gcloud config configurations list</code>, en la columna <b>IS_ACTIVE</b>.</p>
</details>

<details>
<summary><b>9. Escenario: ejecutaste un comando y la VM se creó en el proyecto equivocado. ¿Qué revisas y cómo lo corriges?</b></summary>
<p>Revisa la <b>configuración activa</b> con <code>gcloud config configurations list</code> o <code>gcloud config list</code>. Cambia con <code>gcloud config configurations activate NOMBRE</code> o con <code>gcloud config set project ID</code>.</p>
</details>

<details>
<summary><b>10. Escenario: necesitas trabajar con App Engine en Java desde tu equipo. ¿Qué haces con el SDK?</b></summary>
<p>Tener <b>Java</b> instalado y ejecutar <code>gcloud components install app-engine-java</code>.</p>
</details>
