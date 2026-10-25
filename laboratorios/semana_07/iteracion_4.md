# Iteración 4: Rol + contexto + formato + ejemplo (Few-Shot) 

**Modelo:** ChatGPT ver. GPT-6
**Fecha:** 24 de octubre del 2026

**Prompt usado:**
Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es un técnico que atenderá el incidente y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: acceso no autorizado, phishing, malware, pérdida de dispositivo, otro. Las severidades posibles son: baja, media, alta.

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
"Recibí un correo del banco pidiendo que confirme mi tarjeta en un enlace. Di clic y puse mis datos. Fue hoy a las 10 am desde la laptop de la oficina."

Ejemplo de salida:
| Campo | Valor |
|---|---|
| Tipo de incidente | phishing |
| Severidad | alta |
| Activo afectado | credenciales bancarias del usuario; laptop de oficina |
| Primera acción recomendada | contactar al banco para bloquear la tarjeta y reportar al área de seguridad |
| Información faltante | ninguna |

Clasifica este reporte de incidente: [entrada]

## Respuesta a Entrada 1
| Campo                      | Valor                                                                                                                                                                                                                                               |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Tipo de incidente          | pérdida de dispositivo                                                                                                                                                                                                                              |
| Severidad                  | alta                                                                                                                                                                                                                                                |
| Activo afectado            | laptop de trabajo; correo institucional con sesión abierta; acceso a la VPN corporativa                                                                                                                                                             |
| Primera acción recomendada | reportar inmediatamente al equipo de seguridad informática para revocar sesiones y credenciales, deshabilitar temporalmente el acceso a la VPN y activar el bloqueo o borrado remoto del equipo si está disponible. Verificar el cifrado del disco. |
| Información faltante       | confirmar si el disco está cifrado, si la laptop tiene bloqueo remoto habilitado, el modelo y número de serie del equipo, y si existen mecanismos adicionales de autenticación para la VPN.                                                         |

## Respuesta a Entrada 2
| Campo                      | Valor                                                                                                                                                                                                                                                                       |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Tipo de incidente          | acceso no autorizado (sospecha)                                                                                                                                                                                                                                             |
| Severidad                  | media                                                                                                                                                                                                                                                                       |
| Activo afectado            | cuenta de correo electrónico del usuario                                                                                                                                                                                                                                    |
| Primera acción recomendada | verificar la actividad reciente y las sesiones activas; cerrar todas las sesiones desconocidas, activar la autenticación multifactor y reportar al equipo de seguridad para investigar posibles accesos no autorizados.                                                     |
| Información faltante       | fecha y hora del aviso; proveedor de correo; contenido del aviso; actividad sospechosa detectada; existencia de sesiones o mensajes desconocidos; confirmación de si la contraseña se cambió desde un dispositivo seguro y si la autenticación multifactor está habilitada. |

## Respuesta a Entrada 3
| Campo                      | Valor                                                                                                                                                                                                                                                                                                                                                         |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Tipo de incidente          | malware                                                                                                                                                                                                                                                                                                                                                       |
| Severidad                  | media                                                                                                                                                                                                                                                                                                                                                         |
| Activo afectado            | computadora del usuario; posible afectación del sistema operativo y del navegador por software malicioso o no deseado                                                                                                                                                                                                                                         |
| Primera acción recomendada | desconectar la computadora de la red (Wi-Fi y Ethernet), no ejecutar el programa descargado ni cerrar las ventanas mediante enlaces sospechosos y reportar el incidente al equipo de seguridad para su análisis. No apagarla ni reiniciarla sin seguir el protocolo de respuesta del centro de operaciones, especialmente si se requiere preservar evidencia. |
| Información faltante       | nombre y origen del programa PDF descargado; fecha y hora de los síntomas; sistema operativo; identidad y procedencia del correo del proveedor; presencia de alertas del antivirus; procesos o conexiones sospechosas; alcance de la afectación. No se ha confirmado malware ni se ha determinado si el correo está relacionado con los síntomas.             |