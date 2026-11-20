---
name: "brand-research"
description: "Investigación de marca en español: lente, temas, búsqueda web con fuentes, cifras verificadas, informe Doc y deck con créditos. Úsala para brand research, análisis competitivo, FODA o tendencias de una marca."
---

# Skill Brand Research v1.0

Creada por **Alexis Cirano Briones**, Docente de IA & Martech · www.cirano.cl · alexis@cirano.cl ·
https://www.linkedin.com/in/alexis-cirano/

Produce un informe de investigación de marca con fuentes citadas, en español, y un deck ejecutivo.
Sus estándares: una sola cifra por métrica en todo el informe, cada cifra con periodo y fuente,
ninguna sección incompleta y un deck con gráficos y diseño.

No menciones en los entregables otras herramientas o plataformas de investigación usadas como referencia.

## 1. Lente de investigación

Pide (o toma del mensaje) estos campos. Marca o industria es obligatorio; el resto es opcional.

| Campo | Ejemplo | Regla |
|---|---|---|
| Nombre de la investigación | "Entel Chile – Nov 2026" | Si falta, usa "<Marca> <Mercado> – <mes año>" |
| Marca | Entel | |
| Industria | Telecomunicaciones | Si falta y hay marca, dedúcela y dila |
| Mercado | Chile | Si falta, usa el mercado principal de la marca y dilo |
| Competidores | Movistar, Claro, WOM | Máx. 15. Si faltan, sugiere 3–6 con una búsqueda y muéstralos |

Si nadie está para responder, decide con la regla de cada campo y anota la decisión al inicio del informe.

## 2. Temas

Ofrece los 12 temas (por defecto: Panorama de marca, Competitivo, FODA, Tendencias de la industria):

1. Panorama de marca
2. Consumidor
3. Precio y costo
4. Conveniencia y canales
5. Comunicación y mensajes
6. Competitivo
7. Medios
8. Producto y portafolio
9. Industria
10. Tecnología
11. FODA
12. Tendencias recientes de la industria

Si solo hay industria (sin marca), omite Panorama de marca y FODA de marca; FODA pasa a ser de la industria.

## 3. Investigación

Por cada tema elegido:

- 3–6 búsquedas web (`WebSearch`, modo standard; extended si los resultados son pobres o viejos),
  con consultas en español e inglés y con el año actual. Abre con `WebFetch` las 2–3 fuentes clave.
- Prioridad de fuentes: regulador o estadística oficial (p. ej. Subtel, CMF, INE) > reportes de la empresa
  (memoria, presentaciones a inversionistas, transcripciones de resultados) > medidores independientes
  (Opensignal, Ookla, Kantar, GfK, Cadem) > prensa de negocios (DF, BNamericas, La Tercera Pulso) > el resto.
- Guarda cada dato en `cifras.csv` con columnas:
  `tema, metrica, valor, unidad, periodo, entidad, fuente, url`.
- Nunca inventes una cifra ni una fuente. Si no encuentras un dato, dilo en el informe.
- Busca siempre noticias de las últimas 2–4 semanas (hechos esenciales a la CMF, M&A, cambios de dueño):
  un hecho reciente puede cambiar la lectura de todo el informe.
- Si el usuario trae un informe previo de otra fuente, cruza sus cifras: las que no aparecen en fuentes
  públicas se excluyen y se listan en *Notas de verificación* ("circulan en otros reportes"), sin nombrar la herramienta.

## 4. Verificación

Antes de redactar:

1. **Una sola cifra por métrica.** Agrupa `cifras.csv` por `metrica + entidad` y revisa los valores distintos.
   Casi siempre son periodos distintos de la misma serie (p. ej. 34,2% a mar-26 y 34,3% a jun-26), así que
   usa el más reciente en todo el informe y, si la serie cuenta algo, muéstrala como evolución
   (10,2% → 10,7% → 11,0%). Si dos fuentes serias discrepan en el mismo periodo, muestra ambas y explica
   la diferencia de definición (abonados vs conexiones vs tráfico vs ingresos).
2. **Periodo explícito.** Toda cifra lleva su periodo ("jun-2026", "T2 2026").
3. **Afirmaciones contradictorias.** Si una fuente dice "líder en 5G" y otra dice lo contrario,
   precisa en qué métrica es líder cada uno (disponibilidad, velocidad, suscriptores).
4. **Completitud.** Cada tema elegido debe tener todas sus secciones.
5. Corre un script que recalcule sumas, diferencias en puntos y variaciones citadas.

## 5. Informe (Docs)

Crea un doc (tipo Docs de Artifact; contenido vía el conector Claude Docs) en español con:

- Encabezado: nombre, lente, fecha, decisiones tomadas por defecto.
- **Resumen ejecutivo** (5–7 viñetas) y **Cifras clave** (tabla única de la verificación).
- Una sección por tema con:
  - 3 hallazgos destacados (una línea cada uno, con cita)
  - análisis en prosa (3–4 párrafos)
  - 1 gráfico o tabla cuando haya datos comparables
  - "Qué significa para la marca"
- FODA en tabla 2×2. Tendencias: 3–5 tendencias con "qué pasa / por qué importa / implicancia".
- **Implicancias y recomendaciones** al final, marcadas como lectura estratégica y no como datos.
- **Notas de verificación**: qué cifras se resolvieron, cuáles se excluyeron y por qué.
- **Fuentes** numeradas con enlace; cada número citado [n] debe decir lo que se le atribuye.
  Cuando la fuente es prensa que reproduce a un regulador, avisa que conviene enlazar el PDF original.
- **Créditos y disclaimer** al cierre (texto exacto en la sección 7).

## 6. Deck (Slides)

Crea un deck (tipo Slides de Artifact) de 11–16 láminas. Diseño: si no hay design system por defecto, pregunta
entre los del usuario o un estilo propio sobrio. Estructura recomendada:
portada · resumen (4 ideas) · 6 KPIs · barras de share · tabla de ranking por métrica · ganadores/perdedores
(p. ej. portabilidad) · perfiles de competidores · FODA 2×2 · lámina destacada del hecho del momento ·
tendencias (4 tarjetas) · recomendaciones (5) · control de calidad (interna) · **metodología y variables** ·
fuentes · **créditos (siempre la última)**.

**Lámina "Metodología y variables" (obligatoria, antes de fuentes):** da contexto de cómo se llegó a los
resultados. Incluye:
- **Lente:** marca, industria, mercado, competidores y periodo analizado.
- **Temas** investigados y por qué se eligieron.
- **Cómo se investigó:** tipos de fuentes (reguladores, estudios, prensa, sitios de las marcas) y número de
  fuentes citadas.
- **Variables y métricas:** cada métrica que aparece en el deck (por ejemplo share, ingresos, portabilidad,
  satisfacción) con su definición, unidad y periodo, en una tabla de 3 columnas (variable · qué mide ·
  periodo/fuente).
- **Reglas de verificación** (cifras con periodo y fuente, series en vez de datos sueltos) y **límites** del
  análisis.
Si no cabe con ~40 palabras visibles, usa la tabla en la lámina y lleva el detalle a las notas, o divídela en dos
láminas. El informe Doc incluye la misma información en su sección de metodología.
Máximo ~40 palabras por lámina; lo denso va a notas. Revisa que nada pase del margen inferior.
Si pide PowerPoint, exporta desde Slides o usa la skill pptx.

## 7. Créditos y disclaimer (obligatorio en todo entregable)

Cierra el informe con una sección "Créditos" y el deck con una lámina final "Créditos", con este texto:

> Informe ejecutado con Skill Brand Research v1.0 creada por:
>
> **Alexis Cirano Briones**
> Docente de IA & Martech
> Web: www.cirano.cl (https://www.cirano.cl)
> Mail: alexis@cirano.cl
> LinkedIn: https://www.linkedin.com/in/alexis-cirano/
>
> *Disclaimer: toda la información y las conclusiones de este documento son responsabilidad de quien lo
> elabora y no de la Skill Brand Research ni de su autor. La skill es una herramienta de apoyo: las cifras,
> fuentes y recomendaciones deben ser revisadas y validadas antes de usarse o compartirse.*

## 8. Asistente

Después de entregar, ofrece responder preguntas sobre el informe en la conversación:
responde citando las fuentes del informe y busca de nuevo si la pregunta sale de lo investigado.

## Plantilla de consulta por tema (guía)

- Panorama: "<marca> participación de mercado <mercado> <año>", "<marca> resultados <trimestre> <año>", "<marca> ranking marca <año>"
- Competitivo: "<industria> <mercado> participación <año> <competidores>", "<regulador> informe sector <año>"
- FODA: resultados trimestrales, calificación de riesgo (Fitch/S&P/Feller), noticias de M&A y regulación
- Tendencias: informe del regulador, consultoras (Budde, GSMA, Deloitte), uso digital del consumidor