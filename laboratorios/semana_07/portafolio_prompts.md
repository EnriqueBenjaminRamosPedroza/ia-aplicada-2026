---

## Semana 7: Clasificación de incidentes con mejora iterativa

**Fecha:** 25 de octubre de 2026
**Modelo:** ChatGPT (GPT-6)
**Tarea:** clasificar reportes de incidente (tipo, severidad, activo afectado, primera acción, información faltante) a partir de texto libre de usuarios.
**Evaluación:** 3 criterios (completitud, formato, manejo de incertidumbre), escala 0 a 2, 3 entradas por iteración (máximo 18).

### Resumen de iteraciones

| Iteración | Técnica aplicada | C1 | C2 | C3 | Total |
|---|---|---|---|---|---|
| 0 | Línea base (zero-shot) | 5 | 1 | 5 | 11 |
| 1 | Rol | 5 | 1 | 6 | 12 |
| 2 | Rol + contexto | 6 | 0 | 6 | 12 |
| 3 | Rol + contexto + formato | 6 | 4 | 6 | 16 |
| 4 | Anterior + ejemplo (few-shot) | 6 | 5 | 6 | 17 |
| 5 | Anterior + cadena de razonamiento | 6 | 6 | 6 | 18 |

**Prompt adoptado:** iteración 4 (17/18, salida solo en tabla, lista para copiar). Prueba de robustez con una cuarta entrada: 6/6.

### Lecciones
- El mayor salto fue el formato exacto (+4, todo en C2).
- El ejemplo few-shot eliminó los calificativos entre paréntesis en tipo y severidad.
- La cadena de razonamiento sumó 1 punto, pero agrega texto que hay que recortar antes de copiar la salida.
- C3 estaba casi al máximo desde la línea base: mis entradas fueron poco exigentes para medir invenciones.

### Plantilla

# Plantilla: clasificación de incidente v1
# Variables: {ROL_LECTOR}, {CATEGORIAS}, {SEVERIDADES}, {EJEMPLO_ENTRADA}, {EJEMPLO_SALIDA}, {ENTRADA}

Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es {ROL_LECTOR}.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: {CATEGORIAS}. Las severidades posibles son: {SEVERIDADES}.

Responde únicamente con esta tabla en Markdown, sin texto adicional:

| Campo | Valor |
|---|---|
| Tipo de incidente | |
| Severidad | |
| Activo afectado | |
| Primera acción recomendada | |
| Información faltante | |

Si un campo no puede determinarse a partir del texto, escribe "NO ESPECIFICADO" en Valor y explica qué falta en la fila "Información faltante".

Ejemplo de entrada:
"{EJEMPLO_ENTRADA}"

Ejemplo de salida:
{EJEMPLO_SALIDA}

Clasifica este reporte de incidente:

{ENTRADA}

---

## Instrucciones de uso

**Qué poner en cada variable**
- `{ROL_LECTOR}`: quién leerá la respuesta (por ejemplo, "un técnico que atenderá el incidente y necesita información precisa").
- `{CATEGORIAS}`: lista cerrada de tipos de incidente separados por comas (por ejemplo, "acceso no autorizado, phishing, malware, pérdida de dispositivo, otro").
- `{SEVERIDADES}`: lista cerrada de niveles (por ejemplo, "baja, media, alta").
- `{EJEMPLO_ENTRADA}`: un reporte de ejemplo escrito por ti, no generado por el modelo.
- `{EJEMPLO_SALIDA}`: la tabla correcta de ese ejemplo, con las 5 filas.
- `{ENTRADA}`: el reporte real a clasificar, pegado completo.

**Modelo probado:** ChatGPT (GPT-6), 24 de octubre de 2026.

**Puntaje obtenido:** 17/18 en las tres entradas originales (línea base: 11/18). En la prueba de robustez con una cuarta entrada obtuvo 6/6.

**Limitaciones conocidas**
- Probado con un solo modelo y cuatro entradas.
- La cuarta entrada era del mismo tipo que el ejemplo (phishing), así que no descarta del todo el sesgo hacia ese tipo.
- Si el ejemplo es muy parecido a la entrada real, el modelo puede copiarlo.
- Puede agregar calificativos entre paréntesis en tipo o severidad (pasó una vez en la iteración 4).
- Las puntuaciones las asigné yo, con una rúbrica propia.

### Limitaciones
- Un solo modelo, cuatro entradas y calificación hecha por mí.
- La cuarta entrada era phishing, igual que el ejemplo, así que no descarta del todo el sesgo hacia ese tipo.
