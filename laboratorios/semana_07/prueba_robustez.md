**Prompt:** 
Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es un técnico que atenderá el incidente y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: acceso no autorizado, phishing, malware, pérdida de dispositivo, otro. Las severidades posibles son: baja, media, alta.

Antes de la tabla, escribe una sección titulada "Análisis" con tres viñetas: qué información explícita hay en el texto, qué se puede inferir con seguridad y qué no se puede determinar. Después escribe únicamente esta tabla en Markdown, sin más texto adicional:

| Campo | Valor |
|---|---|
| Tipo de incidente | |
| Severidad | |
| Activo afectado | |
| Primera acción recomendada | |
| Información faltante | |

Si un campo no puede determinarse a partir del texto, escribe "NO ESPECIFICADO" en Valor y explica qué falta en la fila "Información faltante".

Ejemplo de entrada:
"Recibí un correo del banco pidiendo que confirme mi tarjeta en un enlace. Di clic y puse mis datos. Fue hoy a las 10 am desde la laptop de la oficina."

Ejemplo de salida:
| Campo | Valor |
|---|---|
| Tipo de incidente | phishing |
| Severidad | alta |
| Activo afectado | credenciales bancarias del usuario; laptop de oficina |
| Primera acción recomendada | contactar al banco para bloquear la tarjeta y reportar al área de seguridad |
| Información faltante | ninguna |

Clasifica este reporte de incidente:

Me llegó un mensaje de texto de un número desconocido que decía ser de
paquetería, con un enlace para reprogramar una entrega. No hice clic, pero
mi hermano dice que a él le llegó el mismo y sí entró. No sé a qué hora
llegó.

**Resultado**

| Campo                      | Valor                                                                                                                                                                                                                              |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Tipo de incidente          | phishing                                                                                                                                                                                                                           |
| Severidad                  | media                                                                                                                                                                                                                              |
| Activo afectado            | NO ESPECIFICADO; posible exposición del dispositivo o de la información del hermano del usuario                                                                                                                                    |
| Primera acción recomendada | Solicitar al hermano que informe al área de seguridad y confirme si ingresó datos personales, credenciales o descargó archivos. Si proporcionó credenciales, cambiarlas desde un dispositivo seguro y cerrar las sesiones activas. |
| Información faltante       | Hora de recepción del mensaje; confirmación de si el hermano ingresó datos personales o credenciales, descargó archivos o concedió permisos; dispositivo utilizado y posible afectación.                                           |

