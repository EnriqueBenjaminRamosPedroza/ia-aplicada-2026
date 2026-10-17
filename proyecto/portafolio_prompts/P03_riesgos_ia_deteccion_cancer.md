# P03 — Riesgos y mitigaciones de la herramienta propuesta

> **Nota: ejemplo ilustrativo.** La respuesta de la sección "Resultado obtenido" fue redactada como ejemplo y **no se obtuvo ejecutando el prompt en un modelo**. Las tres afirmaciones de la verificación sí se contrastaron con las fuentes enlazadas.

## Objetivo
Obtener una lista de los principales riesgos de la herramienta de IA propuesta por el proyecto (apoyo a la detección temprana de cáncer para personal médico) con una medida de mitigación para cada uno, como base de la sección de riesgos del documento.

## Modelo y configuración
- Modelo: ChatGPT (GPT-6)
- Temperatura: 0.7 (según la ficha de la semana 5)
- Fecha de ejecución: 2026-10-17

## Prompt (versión v1)
```text
Enumera los cinco principales riesgos de una herramienta de IA de apoyo a la detección temprana de cáncer dirigida a médicos radiólogos de hospitales públicos en México. Para cada riesgo incluye una medida de mitigación y, cuando sea posible, un dato o fuente que respalde el riesgo.
```

## Resultado obtenido
```text
1. Sesgo por datos de entrenamiento poco representativos. Si el modelo se entrena con poblaciones distintas a la mexicana, su desempeño puede bajar. Mitigación: validar la herramienta con imágenes de pacientes del propio hospital antes de usarla.
2. Dependencia excesiva del médico en la herramienta. El personal podría aceptar las alertas sin revisarlas. Mitigación: la herramienta solo sugiere; la decisión final y el registro de cada caso siguen a cargo del radiólogo.
3. Falsos negativos y falsos positivos. Un error puede retrasar un diagnóstico o generar estudios innecesarios. Mitigación: fijar umbrales con especialistas y revisar periódicamente los casos fallidos. Dato de referencia: un ensayo aleatorizado en Suecia (MASAI) con más de 80,000 mujeres reportó una reducción de 44.3 % en la carga de lectura de mamografías con una tasa de detección similar.
4. Falta de autorización regulatoria. Usar una herramienta clínica sin la autorización correspondiente es un riesgo legal. Mitigación: clasificar la herramienta como dispositivo médico y tramitar la autorización ante la autoridad sanitaria. Dato de referencia: la FDA no regula la IA como tal, sino los dispositivos médicos que la incorporan, y ha autorizado más de 500 dispositivos con IA.
5. Protección de datos personales de salud. Las imágenes y los expedientes son información sensible. Mitigación: anonimizar los datos, limitar el acceso y cumplir la normativa mexicana de protección de datos personales.
```

## Verificación
| Afirmación verificable | Fuente primaria | Clasificación |
|---|---|---|
| Un ensayo aleatorizado (MASAI) con más de 80,000 mujeres reportó una reducción de 44.3 % en la carga de lectura con tasa de detección similar | Lång et al. (2023), *Lancet Oncology* 24(8), 936-944, resumen en https://pubmed.ncbi.nlm.nih.gov/37541274/ | Correcta |
| La FDA no regula la IA como tal, sino los dispositivos médicos que la incorporan | FDA, https://www.fda.gov/medical-devices/digital-health-center-excellence/artificial-intelligence-enabled-medical-devices | Correcta |
| La FDA ha autorizado más de 500 dispositivos con IA | FDA, misma página: indica más de 1,600 dispositivos autorizados a septiembre de 2026 | Parcialmente correcta (la cifra citada está desactualizada: es mucho mayor) |

Tasa de error de esta respuesta: 33.3 % (1 parcialmente correcta de 3 afirmaciones verificadas).

## Evaluación
- Qué funcionó: la lista cubre riesgos distintos (sesgo, dependencia, errores, regulación, privacidad), cada uno con una mitigación concreta y aplicable a un hospital público. Dos de los tres datos coinciden con las fuentes.
- Qué falló: la cifra de dispositivos autorizados por la FDA está desactualizada, un tipo de error difícil de notar sin abrir la fuente. La respuesta tampoco nombra normas mexicanas específicas (de datos de salud ni de dispositivos médicos) y habla de "la autoridad sanitaria" sin precisar cuál.
- Qué cambiaré en la siguiente versión: pedir que cada dato lleve su año y su fuente con enlace, y pedir que nombre las normas y las autoridades de México que aplican.

## Historial de versiones
| Versión | Fecha | Cambio realizado | Resultado del cambio |
|---|---|---|---|
| v1 | 2026-10-17 | Versión inicial | Tasa de error: 33.3 % |

## Datos usados
Confirmo que este prompt cumple la sección 5 de la política de datos del proyecto: sí. El prompt describe el proyecto en general y no contiene datos de pacientes ni información clínica real.
