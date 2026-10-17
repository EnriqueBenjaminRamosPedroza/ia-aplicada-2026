# P02 — Propuesta de IA para detectar cáncer (prompt de la semana 1)

> **Nota:** la clasificación de la verificación es **preliminar y con fines ilustrativos**. Se basó en el resumen del artículo en PubMed y en la página de la FDA, sin revisar el texto completo de cada fuente.

## Objetivo
Repetir hoy, con el modelo elegido en la semana 5, el prompt con el que exploré el problema del proyecto en la semana 1, para obtener una propuesta general de IA que analice información médica y ayude a detectar cáncer, y medir qué tan verificable es.

## Modelo y configuración
- Modelo: ChatGPT (GPT-6)
- Temperatura: 0.7 (según la ficha de la semana 5)
- Fecha de ejecución: 2026-10-17

## Prompt (versión v1)
```text
Desarrolla una propuesta de IA capaz de analizar información medica para identificar patrones que ayuden a detectar cáncer.
```

## Resultado obtenido
```text
Propuesta: OncoIA, inteligencia artificial para la detección temprana del cáncer
Objetivo: Desarrollar un sistema de inteligencia artificial capaz de analizar información médica para identificar patrones asociados con distintos tipos de cáncer y apoyar su detección temprana.
Funcionamiento: OncoIA analizará expedientes clínicos, resultados de laboratorio, antecedentes familiares e imágenes médicas mediante algoritmos de aprendizaje automático. Con esta información, identificará anomalías y patrones sospechosos para generar alertas que ayuden a los médicos a determinar si se requieren estudios adicionales.
Implementación: El proyecto comenzará con un programa piloto enfocado en un tipo de cáncer, utilizando datos médicos autorizados y modelos entrenados con diagnósticos previamente confirmados. Posteriormente, se evaluará su precisión mediante pruebas clínicas y la supervisión de especialistas.
Beneficios esperados: Facilitar la identificación de casos sospechosos, priorizar pacientes que requieren atención especializada y contribuir a reducir retrasos en la evaluación médica.
Seguridad y ética: Se protegerá la privacidad de los pacientes y se cumplirán las disposiciones legales aplicables. La IA funcionará como herramienta de apoyo, sin sustituir el diagnóstico ni las decisiones del personal médico.
Resultado esperado: Contar con una herramienta tecnológica confiable que contribuya a mejorar la detección oportuna del cáncer y favorezca una atención médica más eficiente.
```

## Verificación
La respuesta no incluye cifras, fechas, normas con clave ni referencias bibliográficas, solo afirmaciones generales. Se verifican tres de ellas.

| Afirmación verificable | Fuente primaria | Clasificación |
|---|---|---|
| "Algoritmos de aprendizaje automático pueden analizar imágenes médicas y datos clínicos para identificar patrones sospechosos y generar alertas de apoyo" | Lång et al. (2023), *Lancet Oncology* 24(8), 936-944, resumen en https://pubmed.ncbi.nlm.nih.gov/37541274/ ; FDA, https://www.fda.gov/medical-devices/digital-health-center-excellence/artificial-intelligence-enabled-medical-devices | Parcialmente correcta: el ensayo y la FDA respaldan el análisis de imágenes (mamografías), pero no se encontró respaldo para expedientes clínicos y antecedentes familiares |
| "La IA puede priorizar pacientes y contribuir a reducir retrasos en la evaluación médica" | Mismo artículo MASAI (PubMed 37541274): reportó 44.3 % menos carga de lectura y una tasa de detección similar | Parcialmente correcta: respalda menor carga de trabajo y mejor identificación de casos de riesgo, pero el resumen no mide tiempos de espera |
| "La IA funciona como herramienta de apoyo, sin sustituir el diagnóstico ni las decisiones del personal médico" | FDA, https://www.fda.gov/medical-devices/digital-health-center-excellence/artificial-intelligence-enabled-medical-devices (describe estos dispositivos como apoyo a la detección, no como sustitutos) | Correcta |

Tasa de error de esta respuesta: 66.7 % (2 parcialmente correctas de 3 afirmaciones verificadas).

## Evaluación
- Qué funcionó: la respuesta es clara y está bien estructurada (objetivo, funcionamiento, implementación, beneficios, ética). Propone un piloto de un solo tipo de cáncer, supervisión de especialistas y a la IA como apoyo, no como sustituto del médico. La afirmación sobre el papel de apoyo coincide con la FDA.
- Qué falló: es muy general y no da datos concretos: no nombra tipos de cáncer ni conjuntos de datos, no da métricas de desempeño, no cita normas aplicables en México ni referencias. Generaliza más de lo que respalda la evidencia: la evidencia clínica fuerte es sobre imágenes (mamografías), no sobre expedientes ni antecedentes familiares, y no se encontró evidencia directa sobre reducción de retrasos. Dice que "se cumplirán las disposiciones legales aplicables" sin nombrar ninguna, así que esa parte no se puede verificar.
- Qué cambiaré en la siguiente versión: pedir un tipo de cáncer específico, conjuntos de datos públicos con su fuente, las métricas con que se evaluaría (sensibilidad y especificidad), las normas mexicanas de datos de salud aplicables y referencias con enlace directo.

## Historial de versiones
| Versión | Fecha | Cambio realizado | Resultado del cambio |
|---|---|---|---|
| v1 | 2026-10-17 | Versión inicial (prompt de la semana 1, sin modificar) | Respuesta general; tasa de error preliminar de 66.7 % |

## Datos usados
Confirmo que este prompt cumple la sección 5 de la política de datos del proyecto: sí. El prompt no contiene datos de pacientes ni información clínica real.
