---
title: Resumen Google Cloud – Associate Cloud Engineer
---

> Apuntes del curso para repasar desde el celular.
> Abre el menú **☰** para navegar por secciones y clases. En cada clase, toca las preguntas de **autoevaluación** para ver la respuesta.

<ul class="cards">
{%- for s in site.data.curso %}
  {%- assign hechas = s.clases | where_exp: "c", "c.url" | size %}
  {%- assign total = s.clases | size %}
  <li>
    <h3>Sección {{ s.seccion }}: {{ s.titulo }}</h3>
    <small>{{ hechas }} de {{ total }} clases resumidas</small>
    <div class="progress"><span style="width: {{ hechas | times: 100 | divided_by: total }}%"></span></div>
    <ol>
      {%- for c in s.clases %}
      <li>{% if c.url %}<a href="{{ c.url | relative_url }}">{{ c.titulo }}</a>{% else %}<span class="pending">{{ c.titulo }}</span>{% endif %}</li>
      {%- endfor %}
    </ol>
  </li>
{%- endfor %}
</ul>
