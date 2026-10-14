# Selección de modelo para el proyecto

**Proyecto:** Sistema de inteligencia artificial para la detección temprana de cáncer (documento de planeación ficticio "Proyecto Centinela").
**Laboratorio:** Semana 5 — Tokens, temperatura y ventana de contexto.

---

## 1. Modelos evaluados

| Herramienta | Uso en el laboratorio | Observaciones |
|---|---|---|
| Gemma 4 26B A4B IT (Google AI Studio) | Pruebas de temperatura y de ventana de contexto | Ventana de contexto de 256K tokens (~262,144). Modelo de pesos abiertos. |
| Tokenizador web de OpenAI | Conteo de tokens (Parte 1) | Se usó solo para medir tokens, no para generar respuestas. |

**Nota sobre la elección del modelo:** no se usó un modelo Gemini porque su acceso requería un pago. Se utilizó Gemma 4 26B A4B IT, con autorización del profesor. Por lo tanto, no se comparó entre varios modelos de generación: las conclusiones aplican a este modelo.

---

## 2. Evidencia de tokens

| Texto | Idioma | Caracteres | Tokens | Caracteres/token |
|---|---|---|---|---|
| La inteligencia artificial aplicada resuelve problemas reales. | ES | 62 | 9 | 6.89 |
| Applied artificial intelligence solves real problems. | EN | 53 | 7 | 7.57 |
| Documento de prueba (Proyecto Centinela, ~4 páginas) | ES | 13,323 | 2,634 | 5.06 |

- **Documento de prueba:** 2,634 tokens (≈ 659 tokens por página).
- **Caracteres por token en español:** 6.89 en una frase sencilla y 5.06 en un texto técnico. Para estimar el tamaño de documentos del proyecto se usará **5.06**, porque se parece más a un texto real con vocabulario técnico.
- **Español vs. inglés:** la frase en español usó 9 tokens y la inglesa 7 (≈ 29% más). Es una muestra muy pequeña, pero coincide con lo esperado: los tokenizadores se entrenan con más texto en inglés, por lo que fragmentan más las palabras en español (por ejemplo, "resuelve" se partió en "res" y "uelve").
- **Implicación:** el mismo contenido en español consume más tokens que en inglés, así que llena antes la ventana de contexto y costaría más en servicios de pago por token.

---

## 3. Evidencia de temperatura

Prompt: "Escribe una sola frase, de máximo 20 palabras, que describa qué es un edificio inteligente." (3 ejecuciones por temperatura, historial borrado entre ejecuciones).

| Temperatura | Palabras distintas (3 respuestas) |
|---|---|
| 0 | 21 |
| 0.7 | 29 |
| 1.5 | 30 |

- A temperatura 0 las respuestas fueron casi idénticas (cambian sinónimos como "utiliza"/"emplea" o "confort"/"bienestar"), pero no exactamente iguales.
- A 0.7 y 1.5 el vocabulario fue más variado. La diferencia entre 0.7 y 1.5 fue mínima (29 vs. 30), y con solo 3 respuestas por temperatura la muestra es pequeña.
- Ninguna respuesta a 1.5 fue incorrecta o sin sentido para esta tarea simple.

**Configuración elegida:**
- **Tareas de precisión** (resumir protocolos clínicos, consultar guías, redactar informes): temperatura **baja, entre 0 y 0.3**. En las pruebas solo se midió 0, que fue el valor más consistente; el rango hasta 0.3 es una recomendación, no un valor probado.
- **Tareas creativas** (por ejemplo, explicaciones alternativas para pacientes): temperatura **de 0.7 a 1.0**, siempre con revisión humana. No se usará 1.5 porque, aunque no falló aquí, en contenido médico un modelo más "libre" aumenta el riesgo de cambiar datos sin que se note.

---

## 4. Evidencia de contexto

Se insertó la frase "El código de verificación interno de este documento es AZUL-7342." en el documento de prueba y se preguntó por ella.

| Intento | Copias | Tokens | Respuesta | ¿Correcta? |
|---|---|---|---|---|
| 1 | 1 | 2,631 | AZUL-7342 | Sí |
| 2 | 2 | 5,126 | AZUL-7342 | Sí |
| 3 | 4 | 10,446 | AZUL-7342 | Sí |
| 4 | 8 | 20,930 | AZUL-7342 | Sí |
| 5 | 16 | 41,089 | AZUL-7342 | Sí |
| 6 | 32 | 81,177 | AZUL-7342 | Sí |

| Posición de la aguja | Respuesta | ¿Correcta? |
|---|---|---|
| Inicio | AZUL-7342 | Sí |
| Mitad | AZUL-7342 | Sí |
| Final | AZUL-7342 | Sí |

- **Con cuántos tokens falló:** no falló en ninguna prueba. El máximo probado fue **81,177 tokens**, aproximadamente el 31% de la ventana de 262,144 tokens. El límite real del modelo no se alcanzó en el experimento.
- **Tamaño de los documentos:** el documento de prueba mide ~2,634 tokens (~659 por página). Con ese ritmo, 32,000 tokens equivalen a ~48 páginas y la ventana completa de 262,144 tokens a ~397 páginas.
- **¿Caben o hay que dividirlos?** Un documento como el de prueba cabe sin problema. Documentos largos del proyecto (guías clínicas completas, reglamentos, varios protocolos juntos) podrían acercarse al límite y, además, conviene dividirlos en fragmentos o usar recuperación de información (RAG), porque más texto aumenta el costo y el riesgo de error.
- **Limitaciones del experimento:** la frase se repitió en cada copia en las pruebas de saturación (lo cual facilita encontrarla), la prueba es de búsqueda literal y no de comprensión, y cada prueba se ejecutó una sola vez. Que el modelo encuentre un código no garantiza que interprete correctamente un texto complejo.

---

## 5. Decisión final

- **Modelo elegido:** Gemma 4 26B A4B IT.
- **Razones:**
  - No falló en la prueba de contexto hasta 81,177 tokens y su ventana de 256K es amplia para el tamaño de los documentos del proyecto.
  - Es de pesos abiertos, así que se podría ejecutar en infraestructura propia sin enviar datos a un servicio externo, lo cual es importante en un proyecto de salud. *(Esta ventaja no se probó en el laboratorio, que se hizo en AI Studio en línea.)*
  - Su acceso en AI Studio no requiere pago, lo que lo hace viable para el desarrollo académico.
- **Configuración:**
  - Precisión: temperatura 0 a 0.3.
  - Creatividad: temperatura 0.7 a 1.0.
  - Documentos largos: dividir en fragmentos o usar RAG; pedir siempre cita textual de la fuente.
- **Restricciones de datos:**
  - No introducir imágenes, expedientes ni datos de pacientes reales en AI Studio ni en ningún servicio en línea.
  - Usar solo datos anonimizados, públicos o ficticios durante el desarrollo y las pruebas.
  - Toda respuesta del modelo debe ser revisada por una persona calificada antes de usarse, y el modelo de lenguaje no toma decisiones diagnósticas.
- **Alcance:** el modelo de lenguaje apoyaría tareas de texto (informes, consulta de guías). La detección de cáncer en imágenes requiere un modelo de visión entrenado y validado para ese fin, que está fuera de este laboratorio.
