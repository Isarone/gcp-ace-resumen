---
title: Calculadora de precios de Google Cloud
seccion: 1
clase: 5
---

## 🧠 Idea clave

La **calculadora de precios** (*Google Cloud Pricing Calculator*) permite **estimar costos antes de desplegar** cualquier recurso. Sirve para planificar presupuestos y tomar decisiones inteligentes.

🔗 [cloud.google.com/products/calculator](https://cloud.google.com/products/calculator)

## 🧮 Ejemplo de la clase: estimar una VM de Compute Engine

| Opción | Qué eliges | Nota |
|---|---|---|
| **Nº de instancias** | Cuántas VMs | — |
| **Tiempo de uso** | Horas al mes | Por defecto **730 h/mes** = mes completo, 24/7 |
| **Sistema operativo** | Gratis (Debian, CentOS, Ubuntu), licencia propia o de pago | Un SO de pago **suma al costo** |
| **Modelo de aprovisionamiento** | **Regular** o **Spot** | Spot es **más barato**, pero Google puede **interrumpirla en cualquier momento** |
| **Tipo de máquina** | Familia y serie (ej. propósito general, **serie N1**), vCPU y RAM | Ajustable a tus necesidades |
| **Memoria extendida** | Más RAM que la estándar | Para apps que **consumen mucha memoria** |
| **Disco de arranque** | **Estándar**, **Balanceado** o **SSD** | Balanceado = equilibrio entre **rendimiento y costo** |
| **Descuento por uso sostenido** | Activar/desactivar | Descuento si la VM corre **por un período prolongado** |
| **GPU** | Agregar o no | **Encarece mucho** el precio |
| **Región** | Ubicación | **El precio varía por región** |
| **Descuento por compromiso** | **1 año** o **3 años** | **Reduce significativamente** el costo |

**Resultado del ejemplo:** ≈ **USD 109.60/mes** (cómputo + disco de arranque).

## 🌍 La región cambia el precio

| Región | Costo de la misma VM |
|---|---|
| **Iowa** (`us-central1`) | ≈ USD 109/mes |
| **Taiwán** (`asia-east1`) | ≈ USD 126/mes |

## 💰 Formas de ahorrar que aparecen en la calculadora

```
Spot              → mucho más barata, pero puede ser interrumpida
Uso sostenido     → descuento si la VM corre mucho tiempo
Compromiso 1 o 3 años → gran descuento a cambio de comprometerte
Región más barata → mismo recurso, menor precio
SO gratuito       → evita costo de licencia
```

> 📌 Spot, los tipos de disco y las familias de máquinas se verán en detalle en el **módulo de recursos de procesamiento**.

## 🛠️ Otras funciones de la calculadora

- **Cambiar la moneda.**
- **Agregar más productos** a la misma estimación.
- **Compartir la estimación**, por ejemplo con ventas o con otras personas interesadas.

Complementa la calculadora con la **página de precios de Google Cloud**, que muestra los precios por región y otras opciones de ahorro.

## 🎯 Tips para el examen

- "¿Cuánto costará antes de desplegar?" → **Pricing Calculator**.
- **730 horas** = un mes completo 24/7.
- **Spot** = barata pero **interrumpible**. No sirve para cargas que no toleran interrupciones.
- **Compromiso (1 o 3 años)** = mayor descuento para cargas **estables y predecibles**.
- **Uso sostenido** = descuento por mantener la VM encendida mucho tiempo.
- El precio **depende de la región**.

## ✅ Autoevaluación

<details>
<summary><b>1. ¿Para qué sirve la calculadora de precios?</b></summary>
<p>Para <b>estimar los costos</b> de los servicios de Google Cloud <b>antes de desplegar</b> recursos.</p>
</details>

<details>
<summary><b>2. ¿Cuántas horas al mes usa por defecto la calculadora y qué representan?</b></summary>
<p><b>730 horas</b>, un mes completo funcionando 24/7.</p>
</details>

<details>
<summary><b>3. ¿Qué diferencia hay entre una VM regular y una Spot?</b></summary>
<p>La <b>Spot</b> es más económica, pero Google Cloud puede <b>interrumpirla en cualquier momento</b>. La regular no se interrumpe así.</p>
</details>

<details>
<summary><b>4. ¿Qué tipo de disco de arranque equilibra rendimiento y costo?</b></summary>
<p>El <b>disco persistente balanceado</b>.</p>
</details>

<details>
<summary><b>5. ¿Para qué sirve la memoria extendida?</b></summary>
<p>Para tener <b>más RAM que la estándar</b> del tipo de máquina, útil en apps que consumen mucha memoria o guardan muchos datos en memoria.</p>
</details>

<details>
<summary><b>6. ¿Por qué la misma VM cuesta distinto en Iowa y en Taiwán?</b></summary>
<p>Porque <b>las tarifas varían según la región</b>. En el ejemplo: ≈ USD 109 en Iowa y ≈ USD 126 en Taiwán.</p>
</details>

<details>
<summary><b>7. ¿Qué plazos tiene el descuento por compromiso?</b></summary>
<p><b>1 año o 3 años.</b></p>
</details>

<details>
<summary><b>8. Escenario: tienes un servidor web que debe estar encendido 24/7 durante los próximos 3 años. ¿Qué opción reduce más el costo?</b></summary>
<p>El <b>descuento por compromiso de 3 años</b>. Spot no sirve porque puede interrumpirse.</p>
</details>

<details>
<summary><b>9. Escenario: procesas lotes de datos que pueden reintentarse si se cortan, y quieres el menor precio. ¿Qué eliges?</b></summary>
<p><b>VMs Spot</b>: son más baratas y la carga tolera interrupciones.</p>
</details>

<details>
<summary><b>10. Además de calcular, ¿qué más permite hacer la calculadora?</b></summary>
<p>Cambiar la moneda, agregar varios productos a la estimación y <b>compartirla</b> con otras personas.</p>
</details>
