# Iteración 3: Rol + Contexto + Formato

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

Clasifica este reporte de incidente: [entrada]

## Respuesta a Entrada 1
Campo	Valor
Tipo de incidente	pérdida de dispositivo
Severidad	alta
Activo afectado	Laptop de trabajo extraviada en un camión de la ruta 12; contiene una sesión abierta del correo institucional y acceso a la VPN corporativa. Estado del cifrado del disco desconocido.
Primera acción recomendada	Revocar o suspender inmediatamente las sesiones y credenciales del correo institucional y el acceso a la VPN; bloquear o borrar remotamente la laptop si es posible. Escalar al equipo de seguridad para evaluar el riesgo de exposición de datos.
Información faltante	Número de serie o identificador del equipo, última ubicación conocida, existencia de herramientas de administración y borrado remoto, estado del cifrado del disco, presencia de datos sensibles almacenados localmente y confirmación de revocación de sesiones y credenciales.

## Respuesta a Entrada 2
Campo	Valor
Tipo de incidente	Acceso no autorizado (sospecha; no confirmado)
Severidad	Media (provisional; requiere validación)
Activo afectado	Cuenta de correo electrónico
Primera acción recomendada	Verificar la actividad reciente y las sesiones activas de la cuenta; cerrar todas las sesiones desconocidas, habilitar MFA y revisar los métodos de recuperación y las reglas de reenvío del correo.
Información faltante	Fecha y hora del aviso, proveedor de correo, detalles del acceso sospechoso, ubicación o dispositivo desconocido, confirmación de acceso no autorizado y estado de MFA.

## Respuesta a Entrada 3
Campo	Valor
Tipo de incidente	Malware (posible adware asociado al programa descargado).
Severidad	MEDIA (comportamiento anómalo posterior a una descarga; requiere investigación para confirmar el alcance).
Activo afectado	Computadora del usuario; sistema operativo y nombre del equipo NO ESPECIFICADO.
Primera acción recomendada	Aislar el equipo de la red desconectando Wi-Fi y cable Ethernet, sin apagarlo por el momento, y notificar al SOC para preservar evidencia y realizar un análisis antimalware. No eliminar archivos ni desinstalar programas hasta recibir instrucciones técnicas.
Información faltante	Nombre y origen del programa para editar PDF; fecha y hora de descarga; sistema operativo; URL de descarga; presencia de alertas del antivirus; alcance de las ventanas emergentes; posible ejecución del programa; detalles y remitente real del correo del proveedor. No hay evidencia suficiente para confirmar si el correo fue phishing o si existe relación con los síntomas.