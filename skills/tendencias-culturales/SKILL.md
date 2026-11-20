---
name: "tendencias-culturales"
description: "Inteligencia cultural en español: detecta y mide tendencias culturales de un tema o marca, chat con prompts (STEEP, emergentes) y brief creativo. Úsala para tendencias culturales, insights culturales o briefs."
---

# Skill Tendencias Culturales v1.1

Creada por **Alexis Cirano Briones**, Docente de IA & Martech · www.cirano.cl · alexis@cirano.cl ·
https://www.linkedin.com/in/alexis-cirano/

Detecta, mide y explica tendencias culturales alrededor de un tema, categoría o marca, con señales
públicas citadas, un índice de energía propio y salidas accionables (informe, deck y brief creativo).
No menciones en los entregables otras herramientas o plataformas usadas como referencia.

## Fuentes permitidas (solo públicas y gratuitas)

Esta skill trabaja SOLO con tres fuentes:

1. **Conocimiento del modelo:** para contexto, definiciones, historia de la categoría y para proponer
   hipótesis. Nunca cuenta como señal ni sostiene una cifra; si lo usas en el informe, márcalo como
   "contexto general, sin fuente".
2. **Búsqueda web pública:** `WebSearch` y `WebFetch` sobre sitios de acceso libre (prensa, estudios
   publicados, organismos públicos, blogs, redes y foros abiertos, repositorios académicos, patentes).
3. **Deep Research:** la skill `deep-research` (cuando esté disponible y la sesión permita agentes) para
   la recolección amplia de señales del Flujo A y para preguntas profundas del Flujo B.

No uses APIs, conectores ni herramientas pagadas (por ejemplo DataForSEO, Semrush, Supermetrics,
Windsor u otras de pago), aunque estén conectados en la sesión. Si el usuario adjunta por su cuenta un
archivo público y gratuito (por ejemplo una exportación CSV de Google Trends), puedes usarlo como anexo
ilustrativo, pero el IEC se calcula igual solo con señales.

Tiene tres flujos. Si el usuario no dice cuál, infiérelo: "tendencias de X" → A; una pregunta o un
análisis puntual → B; "brief", "campaña", "idea creativa" → C.

---

## Taxonomía propia: Mapa Cultural (v1.0)

Usa SOLO esta taxonomía para etiquetar señales. Cada tendencia tiene un código, una definición y términos
de búsqueda para el índice. Revisa la taxonomía una vez al año.

### Megatendencias (fuerzas lentas, de impacto transversal)

| Código | Megatendencia | Definición |
|---|---|---|
| M1 | Vida algorítmica | La IA y los algoritmos median decisiones cotidianas: qué vemos, compramos y aprendemos. |
| M2 | Economía de la cautela | Costo de vida e incertidumbre empujan a gastar con más cálculo y menos impulso. |
| M3 | Nueva longevidad | Vivimos más años y redefinimos trabajo, salud y consumo en la segunda mitad de la vida. |
| M4 | Clima cotidiano | La crisis climática deja de ser abstracta y entra en decisiones diarias. |
| M5 | Desconfianza institucional | Baja la confianza en instituciones, medios y marcas; sube la verificación entre pares. |
| M6 | Identidades a la carta | Las personas componen identidades propias, cambiantes y en comunidad. |
| M7 | Fatiga digital | Hiperconexión que produce cansancio, búsqueda de desconexión y de lo presencial. |
| M8 | Vuelta a lo cercano | Revalorización de lo local, lo barrial y lo hecho cerca. |

### Macrotendencias por dimensión

| Código | Dimensión | Macrotendencia | Definición breve | Términos de búsqueda (es) |
|---|---|---|---|---|
| B1 | Personas y bienestar | Salud mental a la vista | Hablar de salud mental se normaliza en trabajo, escuela y redes | salud mental, ansiedad, terapia |
| B2 | Personas y bienestar | Bienestar preventivo | Cuidarse antes de enfermar: chequeos, wearables, hábitos | wearable salud, chequeo preventivo |
| B3 | Personas y bienestar | Soledad no deseada | La soledad como problema social y oportunidad de comunidad | soledad, aislamiento social |
| B4 | Personas y bienestar | Alimentación funcional | Comer para un fin: proteína, energía, digestión | alimentos con proteína, suplementos |
| B5 | Personas y bienestar | El sueño como prioridad | Dormir bien como símbolo de bienestar | dormir mejor, insomnio |
| H1 | Hogar y ciudad | Vida compacta | Viviendas más chicas y multiuso | departamento pequeño, muebles multifuncionales |
| H2 | Hogar y ciudad | Movilidad alternativa | Eléctrica, compartida y micro | auto eléctrico, scooter eléctrico, bicicleta |
| H3 | Hogar y ciudad | Barrio de 15 minutos | Resolver la vida cerca de casa | comercio de barrio, delivery |
| H4 | Hogar y ciudad | Hogar multigeneracional | Varias generaciones bajo un mismo techo | vivir con los padres, allegados |
| H5 | Hogar y ciudad | Mascotas como familia | Las mascotas como miembros plenos del hogar | mascotas, veterinaria, comida para perros |
| C1 | Consumo y dinero | Segunda mano | Comprar y vender usado como opción inteligente | ropa usada, reacondicionado, autos usados |
| C2 | Consumo y dinero | Cuotas y crédito cotidiano | Financiar todo, de lo grande a lo pequeño | compra en cuotas, crédito de consumo |
| C3 | Consumo y dinero | Marcas propias y dupes | Alternativas baratas a marcas icónicas | marca propia, dupe |
| C4 | Consumo y dinero | Finanzas digitales cotidianas | Billeteras, inversión y pagos desde el celular | billetera digital, invertir app |
| C5 | Consumo y dinero | Experiencias antes que cosas | Gastar en vivir más que en tener | conciertos, viajes, experiencias |
| T1 | Tecnología | IA generativa personal | Asistentes de IA para tareas personales | chatgpt, inteligencia artificial |
| T2 | Tecnología | Búsqueda conversacional | Preguntar a una IA en lugar de buscar en Google | buscar con IA, asistente virtual |
| T3 | Tecnología | Ciberseguridad personal | Fraudes digitales y autoprotección | estafa digital, phishing |
| T4 | Tecnología | Trabajo automatizado | Automatización que cambia tareas y empleos | automatización, IA empleo |
| T5 | Tecnología | Conectividad total | Conexión en todas partes: 5G, satelital, fibra | 5G, internet satelital, fibra óptica |
| P1 | Planeta | Economía circular | Reparar, reciclar, reutilizar como norma | reciclaje, economía circular |
| P2 | Planeta | Escasez hídrica | El agua como recurso escaso | sequía, ahorro de agua |
| P3 | Planeta | Energía distribuida | Paneles solares y energía propia | paneles solares, energía solar |
| P4 | Planeta | Comida y clima | Dietas y alimentos con menor huella | plant based, huella de carbono |
| P5 | Planeta | Greenwashing bajo la lupa | Escepticismo frente a promesas verdes | greenwashing, sustentable |
| S1 | Sociedad y política | Seguridad ciudadana | La seguridad como preocupación central | delincuencia, seguridad |
| S2 | Sociedad y política | Trabajo independiente y flexible | Freelance, múltiples ingresos, híbrido | trabajo remoto, freelance |
| S3 | Sociedad y política | Diversidad y migración | Sociedades más diversas y sus tensiones | migración, inclusión |
| S4 | Sociedad y política | Choque generacional | Valores distintos entre Gen Z, millennials y boomers | generación z, millennials |
| S5 | Sociedad y política | Regulación tecnológica | Leyes para IA, datos y plataformas | ley de datos personales, regulación IA |
| K1 | Cultura y entretenimiento | Cultura de creadores | Creadores como medios y marcas | influencer, creador de contenido |
| K2 | Cultura y entretenimiento | Nostalgia y retro | Volver a estéticas y productos del pasado | retro, vintage, nostalgia |
| K3 | Cultura y entretenimiento | Gaming social | Los videojuegos como espacio de encuentro | videojuegos, gamer, fortnite |
| K4 | Cultura y entretenimiento | Música urbana latina | Reggaetón, trap y urbano como lengua común | reggaeton, música urbana |
| K5 | Cultura y entretenimiento | Deporte y comunidad | Deporte amateur como identidad social | running, pádel, gimnasio |
| K6 | Cultura y entretenimiento | Microcomunidades | Nichos de fanáticos con alta afinidad | fandom, comunidad |

Si un tema necesita una tendencia que no está, crea una provisional con código `X#`, márcala como
"provisional" y propónla para la próxima revisión de la taxonomía.

---

## Índice de Energía Cultural (IEC, 0–100) — metodología propia

Calcula el IEC solo para las 5–10 tendencias más presentes en el tema, usando únicamente las señales
públicas de `senales.csv` (sin datos de búsqueda ni fuentes pagadas). Para eso, las señales deben cubrir
12 meses: al menos el 40% de los últimos 90 días y el resto de los 9 meses anteriores.

1. **Alcance (A):** cantidad de fuentes distintas (medios, organismos, empresas, comunidades) con
   señales de la tendencia ÷ total de fuentes distintas del proyecto. Mide cuán transversal es.
2. **Momentum (M):** (señales de los últimos 90 días ÷ 3) ÷ (señales de los 9 meses anteriores ÷ 9) − 1,
   es decir, ritmo mensual reciente contra el anterior. Si no hay señales anteriores y sí recientes, M = +100%;
   limita M entre −100% y +200%.
3. **Evidencia (E):** suma ponderada de las señales de la tendencia ÷ suma ponderada de todas. Pesos:
   estudio, encuesta o dato oficial 3 · startup, inversión, paper o patente 2 · prensa o blog 1 ·
   redes y foros 0,5.
4. **IEC** = 100 × (0,40 · rango_percentil(A) + 0,35 · rango_percentil(M) + 0,25 · rango_percentil(E)),
   donde el rango percentil es entre las tendencias del proyecto. Redondea a entero.
5. **Bandas:** 0–30 baja (nicho o emergente) · 31–69 media (masiva y fluctuante) · 70–100 alta (gran relevancia).
6. **Matriz alcance–momentum** (reemplaza la proyección): ubica cada tendencia por A (eje x) y M (eje y),
   con las medianas como cortes. Clasifica:
   - **Más relevantes:** mayor E
   - **Apuesta grande:** A sobre la mediana y M positivo
   - **Emergentes:** A bajo la mediana y M más alto
   - **Declinantes:** M negativo
   Es una lectura indicativa, no un pronóstico.

Corre el cálculo con un script en Python y guarda `iec.csv`. Con pocas señales por tendencia (menos de 3),
marca su IEC como "evidencia débil". En el informe explica siempre:
"El IEC es un índice relativo dentro de este proyecto, basado solo en señales públicas (cobertura,
ritmo y tipo de evidencia); no mide impresiones, búsquedas ni audiencia, y no es comparable entre
proyectos distintos".

---

## Flujo A — Identificar tendencias

Entrada: tema o categoría (y marca opcional), mercado (por defecto Chile), periodo (por defecto 90 días).

1. **Búsqueda:** escribe una consulta booleana a partir del tema (sinónimos con OR, exclusiones con NOT)
   y muéstrala en el informe.
2. **Señales (30–50):** recolecta con Deep Research (skill `deep-research`, si está disponible; pásale el
   tema, el mercado, la consulta booleana, los canales de abajo y la regla de 12 meses del IEC) y completa o
   verifica con `WebSearch`/`WebFetch`. Si Deep Research no está disponible, hazlo tú con `WebSearch`.
   Registra cada señal en `senales.csv`
   (`id, tipo, titulo, fuente, url, fecha, pais, resumen, tendencias`):
   - **Rápidas:** prensa y blogs, Reddit (`site:reddit.com`), YouTube (`site:youtube.com`),
     TikTok (`site:tiktok.com`)
   - **Lentas:** estudios y encuestas (Cadem, Criteria, INE, universidades), startups y rondas de
     inversión, papers (`site:scielo.cl`, Google Scholar), patentes (INAPI, Google Patents)
   Prioriza señales de los últimos 90 días y del mercado pedido. Nunca inventes una señal.
3. **Etiquetado:** asigna a cada señal 1–3 códigos de la taxonomía, con una línea de porqué.
4. **Mapa de tendencias:** prevalencia = % de señales etiquetadas con cada tendencia. Muestra el top 10–15
   como un mapa de panal (hexágonos) o barras, con los 3 primeros destacados.
5. **IEC y proyección** (sección anterior).
6. **Por cada tendencia del top 5:** definición, por qué aparece en este tema, 2–3 señales citadas, IEC,
   banda y qué hacer.
7. **Comparar** (opcional): si piden dos temas o mercados, corre ambos y pon los mapas lado a lado.

## Flujo B — Asistente cultural (biblioteca de prompts)

Responde en la conversación con fuentes. Ofrece estos modos cuando el usuario no sepa qué preguntar:

1. **Tendencias emergentes y micro:** "¿Qué microtendencias están naciendo en [tema] en [mercado]?"
2. **Señales marginales:** "Muéstrame señales raras o de nicho que anticipen cambios en [tema]."
3. **Tendencias del mapa:** "¿Qué tendencias del Mapa Cultural mueven hoy [tema]?"
4. **STEEP cultural:** Social, Tecnológico, Económico, Ecológico, Político, para [tema] en [mercado].
5. **Vientos a favor y en contra:** fuerzas culturales que impulsan o frenan [tema/marca].

Cada respuesta: 3–6 hallazgos con fuentes enlazadas y su vínculo con códigos de la taxonomía.
Si piden exportar la conversación, entrégala como Doc.

## Flujo C — Generador de brief creativo

1. **Resumen de campaña:** categoría, subcategoría, marca, objetivo de negocio ("Queremos que
   [audiencia] [haga algo] al [conectar con un mensaje]") y contexto. Pregunta lo que falte.
2. **Audiencia:** nombre y hasta 4 atributos (generación, ocupación, intereses, nivel socioeconómico...).
3. **Tendencias:** propone 5–8 tendencias del Mapa Cultural relevantes para la marca y la audiencia, cada
   una con 2 señales de respaldo. El usuario elige una o más.
4. **Sparks (6):** ideas detonantes que cruzan la tendencia con la marca, de una línea cada una con un
   ejemplo de activación. El usuario elige una.
5. **Brief creativo**, con estas secciones:
   - Spark elegido
   - Desafío
   - Personas (audiencia)
   - Contexto cultural (tendencias y señales)
   - Dato clave (una cifra con fuente)
   - Empatía (tensión humana)
   - Acción (qué queremos que hagan)
   - Historia de marca (el mensaje)
   - Mandatorios y KPIs sugeridos
   En "Dato", "Empatía", "Acción" e "Historia" ofrece 3 opciones y marca la recomendada.

---

## Salidas

- **Flujo A:** un Doc con lente, consulta booleana, resumen, mapa de tendencias, tabla del IEC, matriz
  alcance–momentum, fichas del top 5, señales citadas, notas metodológicas, fuentes y créditos. Además un deck
  (tipo Slides) de 11–15 láminas: portada · resumen · mapa · IEC · emergentes y declinantes · 5 fichas ·
  señales destacadas · implicancias · **metodología y variables** · fuentes · **créditos (última lámina)**.
- **Lámina "Metodología y variables" (obligatoria, antes de fuentes):** explica cómo se llegó al resultado.
  Incluye:
  - **Lente y alcance:** tema, mercado, periodo y la consulta booleana resumida.
  - **Señales:** cuántas, de qué periodo, de qué canales (rápidas y lentas) y con qué fuentes (búsqueda web
    pública, Deep Research, conocimiento del modelo solo como contexto).
  - **Dimensiones del Mapa Cultural:** qué es una megatendencia y una macrotendencia, y las dimensiones
    usadas para etiquetar (Personas y bienestar, Hogar y ciudad, Consumo y dinero, Tecnología, Planeta,
    Sociedad y política, Cultura y entretenimiento).
  - **Variables del IEC:** cada variable tal como la define la sección del IEC, con qué mide y su peso, la
    fórmula, las bandas (baja, media, alta) y cómo se clasifican emergentes, declinantes y apuesta grande.
  - **Límites:** la frase obligatoria del IEC y las advertencias del proyecto (evidencia débil, pocas señales).
  Usa una tabla de variables (variable · qué mide · peso) y tarjetas; si no cabe con ~40 palabras visibles,
  divide en dos láminas ("Cómo se investigó" y "Cómo se mide la energía") o lleva el detalle a las notas.
  El Doc incluye lo mismo en sus notas metodológicas.
- **Flujo B:** en la conversación; Doc si lo piden.
- **Flujo C:** el brief como Doc (exportable a PDF o Word).
- Diseño del deck: si no hay design system por defecto, pregunta entre los del usuario o un estilo propio
  sobrio. Máximo ~40 palabras por lámina; revisa que nada pase del margen inferior.

## Verificación

- Toda señal debe tener URL y fecha; sin URL no entra.
- Toda cifra lleva periodo y fuente. Si dos fuentes difieren, explica por qué (periodo o definición).
- El IEC se recalcula con el script; nunca se estima a mano.
- Ninguna cifra ni señal viene de una fuente pagada; el conocimiento del modelo nunca se presenta como
  dato ni como señal.
- Marca como "lectura estratégica, no datos" las implicancias, sparks y recomendaciones.

## Créditos y disclaimer (obligatorio en todo entregable)

Cierra el Doc con una sección "Créditos" y el deck con una lámina final "Créditos", con este texto:

> Informe ejecutado con Skill Tendencias Culturales v1.1 creada por:
>
> **Alexis Cirano Briones**
> Docente de IA & Martech
> Web: www.cirano.cl (https://www.cirano.cl)
> Mail: alexis@cirano.cl
> LinkedIn: https://www.linkedin.com/in/alexis-cirano/
>
> *Disclaimer: toda la información y las conclusiones de este documento son responsabilidad de quien lo
> elabora y no de la Skill Tendencias Culturales ni de su autor. La skill es una herramienta de apoyo: las
> señales, cifras, índices y recomendaciones deben ser revisadas y validadas antes de usarse o compartirse.*