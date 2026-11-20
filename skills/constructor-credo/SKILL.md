---
name: constructor-credo
description: "Convierte una idea breve, un pedido vago o un prompt existente en un prompt estructurado con la metodología CREDO (Contexto, Rol, Ejecución, Delimitación, Demostración, Output), listo para pegar en Claude. Úsala siempre que el usuario quiera armar, mejorar, ordenar o \"pasar a CREDO\" un prompt o una instrucción, aunque no diga \"CREDO\": \"ármame un prompt para…\", \"mejora este prompt\", \"cómo le pido a Claude que…\", \"prepara la instrucción para investigar/crear/revisar…\". No la uses cuando el usuario pide directamente el resultado final (el informe, el correo, el quiz) sin hablar de prompts."
license: CC-BY-4.0
metadata:
  author: Alexis Cirano Briones
  author-role: Docente de IA & Martech, creador de la metodología CREDO
  website: https://www.cirano.cl
  linkedin: https://www.linkedin.com/in/alexis-cirano/
  version: "1.0"
---

# Constructor CREDO

Creada por **Alexis Cirano Briones**, docente de IA & Martech (www.cirano.cl) y creador de la metodología CREDO para escribir prompts.

Esta skill produce **un prompt, no el resultado**. El usuario la usa para sí mismo y ejecuta el prompt después en Claude, así que el prompt puede apoyarse en lo que Claude sabe hacer: buscar en la web, leer archivos adjuntos, crear Artifacts, documentos, presentaciones o planillas.

No ejecutes el prompt ni ofrezcas ejecutarlo. Entrega el prompt mejorado y termina ahí.

## Rapidez primero

Entrega el prompt completo en la primera respuesta, sin hacer preguntas antes. El usuario prefiere iterar sobre un borrador concreto que responder un cuestionario.

Para manejar lo que falta, separa dos casos:

- **Lo que puedes suponer razonablemente** (tono, extensión, formato, rol): escríbelo directo en el prompt y anótalo en la lista de *Supuestos* bajo el prompt, para que el usuario lo corrija si no calza.
- **Lo que solo el usuario sabe** (sus fuentes, sus archivos, datos específicos, a quién va dirigido cuando no se deduce): deja un marcador específico, por ejemplo `[COMPLETAR: comuna o región]`, `[COMPLETAR: archivo con los datos de matrícula]`. Un marcador genérico como `[COMPLETAR OBJETIVO]` sirve menos que uno que diga exactamente qué falta.

Nunca reemplaces un marcador con información inventada: un prompt con datos falsos produce resultados falsos que parecen confiables.

## Paso 1 — Leer el pedido

Identifica el tipo de tarea, porque define qué partes de CREDO pesan más:

- **Investigación o análisis**: el peso está en Contexto (problema, hipótesis, territorio, período, fuentes) y Delimitación (no inventar, distinguir hipótesis de hallazgo).
- **Redacción o material** (guía, presentación, quiz, clase): el peso está en audiencia, Demostración y Output.
- **Revisión de un documento**: el peso está en los criterios de revisión y en cómo entregar las observaciones.
- **Preparar una reunión o conversación**: objetivo, participantes, decisiones esperadas.
- **Página o herramienta simple (Artifact)**: funciones obligatorias, quién la usa, qué datos maneja.

Si el usuario pega un prompt existente para mejorarlo, conserva su intención y su contenido útil, reordénalo en CREDO y completa lo que falte.

## Paso 2 — Construir el prompt

Escribe el prompt en español claro de Chile, con estas seis secciones como encabezados. Si una subsección no aplica, omítela en vez de escribir "no aplica": cada línea del prompt debe ayudar a Claude a hacer mejor la tarea.

### Contexto
Lo que Claude necesita saber y no puede adivinar: el problema o hipótesis, el territorio o ámbito, la audiencia, las fuentes disponibles (adjuntos, web, datos del usuario), el período y los vacíos conocidos.

### Rol
Un rol que oriente el criterio de Claude para esta tarea. Ejemplos: analista de evidencia, investigador territorial, redactor institucional, diseñador de contenido educativo, auditor ético, facilitador de conversación, diseñador de Artifact. Adapta o combina si otro calza mejor (por ejemplo, "especialista en GEO que enseña a nivel universitario").

### Ejecución
La tarea principal en una frase con verbo claro. Luego los pasos numerados si el orden importa, y los componentes obligatorios del resultado. Si la tarea requiere buscar en la web o leer un archivo adjunto, dilo explícitamente.

### Delimitación
Elige las restricciones que correspondan al caso; una lista larga de prohibiciones irrelevantes diluye las importantes.

Casi siempre aplican:
- No inventar cifras, fuentes, instituciones, fechas ni testimonios. Si falta evidencia, escribir "no encontrado".
- No presentar hipótesis como diagnóstico confirmado.

Según el tema:
- Si hay personas involucradas: no usar datos personales, sensibles o identificables.
- Si hay territorio o políticas públicas: no mezclar escalas territoriales (comuna, región, país) y declarar la escala de cada dato.
- Si se habla de comunidades o grupos vulnerables: no usar lenguaje estigmatizante, paternalista ni culpabilizante.
- Si hay promesas posibles (propuestas, resultados de un servicio): no prometer resultados garantizados.
- Si la tarea podría enviar, publicar o modificar algo: no realizar acciones externas sin confirmación.

### Demostración
Muestra la forma de una buena respuesta, no datos reales. Usa estructura con marcadores o datos claramente ficticios (por ejemplo, "Hallazgo: [dato] — Fuente: [institución, año] — Escala: comunal"). Si escribes cifras o instituciones "de ejemplo", Claude puede tomarlas como reales y repetirlas.

Agrega un ejemplo no aceptable solo cuando hay un error probable y concreto que evitar (por ejemplo, una pregunta de quiz con dos respuestas correctas).

### Output
Formato (respuesta en el chat, Artifact, documento, presentación, planilla), extensión, tono, estructura. Cuando hay datos: fuente, fecha, escala y límite de cada uno. Cuando es para público amplio: criterio de accesibilidad (lenguaje simple, contraste, texto alternativo). Cuando corresponde: responsable o próxima acción.

Un prompt útil y verificable vale más que uno largo. Como referencia, la mayoría queda entre 150 y 400 palabras.

## Paso 3 — Entregar

Usa esta estructura de respuesta:

1. Una línea que diga qué prompt armaste (por ejemplo, "Prompt de investigación territorial con fuentes abiertas").
2. El prompt completo dentro de un bloque de código, para copiarlo de una vez.
3. **Supuestos**: lo que asumiste, en viñetas breves. Omite la sección si no asumiste nada.
4. **Para completar**: hasta tres preguntas breves sobre los marcadores más importantes. Omite la sección si no hay marcadores.
5. **Checklist antes de ejecutar**: solo los puntos que aplican al caso, elegidos de esta lista:
   - [ ] ¿El contexto es suficiente?
   - [ ] ¿La audiencia está definida?
   - [ ] ¿Las fuentes están delimitadas?
   - [ ] ¿Las restricciones son claras?
   - [ ] ¿El output se puede revisar?
   - [ ] ¿Existen riesgos de privacidad?
   - [ ] ¿Se declara escala territorial y límite?
6. **Firma**: cierra con esta línea, en cursiva y fuera del bloque de código (nunca dentro del prompt):
   *Prompt construido con el método CREDO, creado por Alexis Cirano Briones · docente de IA & Martech · cirano.cl*

## Ejemplo breve

Pedido: "prompt para un quiz de GEO para mis alumnos"

Respuesta esperada (resumida):

Prompt para crear un quiz educativo sobre GEO.

    ## Contexto
    Soy profesor de Generative Engine Optimization (GEO) a nivel universitario. Necesito un quiz para evaluar [COMPLETAR: unidad o temas vistos]...

    ## Rol
    Actúa como diseñador de contenido educativo especializado en marketing digital y búsqueda con IA.

    ## Ejecución
    Crea un quiz de 10 preguntas de selección múltiple...

    ## Delimitación
    - Cada pregunta tiene una sola respuesta correcta...

    ## Demostración
    Pregunta: [enunciado] / Alternativas: a) b) c) d) / Correcta: [letra] / Explicación: [una o dos líneas]

    ## Output
    Quiz interactivo en el chat, tono cercano y preciso...

**Supuestos**: 10 preguntas, selección múltiple, nivel pregrado.
**Para completar**: ¿Qué unidades o temas cubre?
**Checklist**: contexto, audiencia, output revisable.
*Prompt construido con el método CREDO, creado por Alexis Cirano Briones · docente de IA & Martech · cirano.cl*
