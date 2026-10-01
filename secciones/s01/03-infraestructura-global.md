---
title: Infraestructura global de Google Cloud
seccion: 1
clase: 3
---

## 🧠 Idea clave

Google Cloud corre sobre **la red privada más grande del mundo**, diseñada para dar **máximo ancho de banda y mínima latencia**. Sus recursos se organizan en **regiones** y **zonas** para lograr **alta disponibilidad y tolerancia a fallas**.

## 🌍 Cifras (a diciembre de 2024)

| Elemento | Cantidad |
|---|---|
| Regiones | **40** |
| Zonas | **121** |
| Ubicaciones de red perimetral (edge) | **187** |
| Nodos de caché de contenido | **+100** |
| Países y territorios | **+200** |

> ⚠️ Estas cifras crecen con el tiempo; para el examen importa más el **concepto** que el número exacto.

**Áreas geográficas:** América · Europa · Asia-Pacífico · Oriente Medio · África.

## 🧱 Jerarquía: área → región → zona

```
Área geográfica (ej. América)
 └── Región   us-central1      ← ubicación geográfica específica
      ├── Zona  us-central1-a  ← centro de datos aislado
      ├── Zona  us-central1-b
      └── Zona  us-central1-c   (mínimo 3 zonas por región)
```

| Concepto | Qué es | Ejemplo de nombre |
|---|---|---|
| **Región** | Ubicación geográfica donde se despliegan recursos. Contiene varias zonas. | `us-central1`, `asia-east1` |
| **Zona** | Centro de datos **aislado** dentro de una región, con **energía, refrigeración y red independientes**. | `us-central1-a`, `asia-east1-b` |
| **Multirregión** | Recursos replicados en varias zonas **y** regiones. | Ej.: Cloud Spanner multirregional |

📝 **Formato del nombre:** `región` = `<área>-<ubicación><número>` → la zona agrega `-<letra>`.

## 🔍 Por qué importa dónde despliegas

Elegir la ubicación afecta:
- **Disponibilidad**: si una zona cae, las demás de la región siguen operando.
- **Durabilidad** de los datos.
- **Latencia**: tiempo que tarda un paquete en viajar de origen a destino → despliega **cerca de tus usuarios**.

**Ejemplos de la clase:**
- **Compute Engine**: una VM corre en **la zona que tú especifiques** (recurso zonal). Para redundancia, despliega VMs en **varias zonas**.
- **Cloud Spanner** (base de datos relacional): permite configuración **multirregional** → replica datos en varias zonas y regiones, con baja latencia desde distintos lugares.

## 🎯 Tips para el examen

- **Región ⊃ zonas.** Una zona = un centro de datos aislado. Mínimo **3 zonas** por región.
- **Alta disponibilidad** → reparte recursos en **varias zonas** de la región.
- **Resistir la caída de una región completa** → usa **varias regiones** o servicios **multirregionales**.
- **Reducir latencia** → elige la región **más cercana a tus usuarios**.
- Reconoce los nombres: `us-central1` es una **región**; `us-central1-a` es una **zona** (termina en letra).

## ✅ Autoevaluación

<details>
<summary><b>1. ¿Qué es una zona en Google Cloud?</b></summary>
<p>Un <b>centro de datos aislado</b> dentro de una región, con energía, refrigeración y red independientes.</p>
</details>

<details>
<summary><b>2. ¿Cuántas zonas tiene como mínimo cada región?</b></summary>
<p><b>Tres.</b></p>
</details>

<details>
<summary><b>3. ¿<code>europe-west1-b</code> es una región o una zona?</b></summary>
<p>Una <b>zona</b> (termina en letra). Su región es <code>europe-west1</code>.</p>
</details>

<details>
<summary><b>4. ¿Por qué las zonas reducen el riesgo de fallas simultáneas?</b></summary>
<p>Porque están aisladas: cada una tiene su propia energía, refrigeración y red. Si una falla, las otras de la región siguen operando.</p>
</details>

<details>
<summary><b>5. ¿Qué tres factores afecta la elección de ubicación?</b></summary>
<p><b>Disponibilidad, durabilidad y latencia.</b></p>
</details>

<details>
<summary><b>6. ¿Qué es la latencia?</b></summary>
<p>El tiempo que tarda un paquete de información en viajar desde su origen hasta su destino.</p>
</details>

<details>
<summary><b>7. Escenario: tu app en Compute Engine no debe caerse si falla un centro de datos. ¿Qué haces?</b></summary>
<p>Desplegar VMs en <b>varias zonas</b> de la misma región, para que otra zona tome el control si una falla.</p>
</details>

<details>
<summary><b>8. ¿Qué servicio mencionado permite configuración multirregional y qué tipo de servicio es?</b></summary>
<p><b>Cloud Spanner</b>, base de datos relacional. Replica datos en múltiples zonas y regiones.</p>
</details>

<details>
<summary><b>9. Escenario: tus usuarios están en Asia oriental y notan lentitud. ¿Qué ajustas?</b></summary>
<p>Desplegar los recursos en una región cercana, por ejemplo <code>asia-east1</code>, para reducir la latencia.</p>
</details>

<details>
<summary><b>10. ¿Cuáles son las cinco áreas geográficas de Google Cloud?</b></summary>
<p>América, Europa, Asia-Pacífico, Oriente Medio y África.</p>
</details>
