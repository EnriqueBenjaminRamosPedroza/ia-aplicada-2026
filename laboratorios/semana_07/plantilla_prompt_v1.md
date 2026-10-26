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
