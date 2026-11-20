# Skills para Martech

Skills de Claude, en español, creadas por **Alexis Cirano Briones**, docente de IA y Martech, para usar en clases y proyectos:

| Skill | Para qué sirve | Entrega |
|---|---|---|
| **Brand Research** (`brand-research`) | Investigar una marca y su mercado: panorama, competencia, FODA, tendencias, con fuentes citadas y cifras verificadas | Informe + presentación |
| **Tendencias Culturales** (`tendencias-culturales`) | Detectar y medir las tendencias culturales de un tema o marca, conversar con prompts guiados (STEEP, emergentes) y generar un brief creativo | Informe + presentación, o brief |
| **Constructor CREDO** (`constructor-credo`) | Convertir una idea o un prompt vago en un prompt estructurado con la metodología CREDO (Contexto, Rol, Ejecución, Delimitación, Demostración, Output) | Prompt listo para copiar |

Brand Research y Tendencias Culturales usan solo fuentes públicas (búsqueda web y conocimiento del modelo), y cada entregable cierra con una lámina de **metodología y variables** y otra de **créditos**. Constructor CREDO entrega un prompt, no el resultado: lo copias y lo ejecutas después.

---

## Cómo instalarlas

### En Claude (web o app de escritorio)

1. Descarga el `.zip` de la skill desde la carpeta [`dist/`](dist/): `brand-research.zip`, `tendencias-culturales.zip` o `constructor-credo.zip`.
2. En Claude, abre la configuración y busca la sección de **Skills** (dentro de las capacidades).
3. Sube el `.zip` y activa la skill.

> Necesitas un plan que permita skills personalizadas y tener habilitada la ejecución de código. Si no ves la opción, revisa la [ayuda de Claude](https://support.claude.com).

### En Claude Code

Copia la carpeta de la skill en tu directorio de skills:

```bash
mkdir -p ~/.claude/skills
cp -r skills/brand-research skills/tendencias-culturales skills/constructor-credo ~/.claude/skills/
```

---

## Cómo usarlas

Escríbele a Claude con el nombre de la skill o simplemente pide la tarea:

**Brand Research**
- `/brand-research [nombre de la marca] Chile`
- «Haz un brand research de [marca] con sus principales competidores, foco en FODA y tendencias»

**Tendencias Culturales**
- `/tendencias-culturales autos usados en Chile` → informe y presentación de tendencias (Flujo A)
- «¿Qué microtendencias están naciendo en el café de especialidad en Chile?» → respuesta con fuentes (Flujo B)
- «Arma un brief creativo para una marca de zapatillas dirigida a Gen Z» → brief guiado (Flujo C)

**Constructor CREDO**
- `/constructor-credo prompt para un quiz de GEO para mis alumnos`
- «Mejora este prompt y pásalo a CREDO: [pega tu prompt]»

### Qué esperar

- **Informe:** un documento con todas las secciones, fuentes enlazadas y notas de método.
- **Presentación:** 11 a 16 láminas, con gráficos, una lámina de metodología y variables y los créditos al final.
- Si tu cuenta no tiene alguna herramienta (por ejemplo documentos, presentaciones o Deep Research), Claude usará el formato más parecido disponible.

---

## Buenas prácticas para estudiantes

- **Verifica antes de usar.** Revisa las fuentes enlazadas: la skill es una herramienta de apoyo, no reemplaza tu criterio.
- **Lee la lámina de metodología.** Explica qué se midió, cómo y con qué límites.
- **Separa datos de lectura estratégica.** Las implicancias y recomendaciones vienen marcadas como «lectura estratégica, no datos».
- **No borres los créditos** al presentar el trabajo.

---

## Estructura del repositorio

```
skills/
  brand-research/SKILL.md
  tendencias-culturales/SKILL.md
  constructor-credo/SKILL.md
dist/
  brand-research.zip
  tendencias-culturales.zip
  constructor-credo.zip
```

---

## Autor y licencia

**Alexis Cirano Briones**, docente de IA y Martech
Web: [www.cirano.cl](https://www.cirano.cl) · Mail: [alexis@cirano.cl](mailto:alexis@cirano.cl) · LinkedIn: [linkedin.com/in/alexis-cirano](https://www.linkedin.com/in/alexis-cirano/)

Licencia [Creative Commons Atribución 4.0 Internacional (CC BY 4.0)](LICENSE): puedes usar, compartir y adaptar estas skills citando al autor.

*Disclaimer: toda la información y las conclusiones obtenidas con estas skills son responsabilidad de quien elabora cada documento y no de las skills ni de su autor.*
