# Iteración 0: Línea base (zero-shot)

**Modelo:** ChatGPT - versión GPT-6
**Fecha:** 24 DE OCTUBRE DEL 2026

**Prompt usado:**
"Clasifica este reporte de incidente:"


## Respuesta a Entrada 1
Análisis del incidente
Criterio	Clasificación
Categoría	Pérdida de activo informático
Confidencialidad	Riesgo alto: exposición potencial del correo institucional y los datos almacenados
Integridad	Riesgo potencial de modificación de información o uso indebido de la cuenta
Disponibilidad	Posible afectación por pérdida del equipo y bloqueo de accesos
Acceso remoto	Riesgo por la sesión abierta y el acceso a la VPN
Cifrado del disco	Desconocido; debe verificarse

Acciones inmediatas recomendadas
1. Revocar las sesiones activas del correo institucional y cerrar las sesiones de autenticación.
2. Deshabilitar temporalmente el acceso VPN asociado al equipo y revocar sus credenciales o certificados, según corresponda.
3. Reportar el incidente a TI y al equipo de seguridad informática, además de la jefa directa.
4. Intentar localizar y bloquear o borrar remotamente la laptop, si la organización dispone de esa capacidad.
5. Verificar el cifrado del disco y revisar los registros de acceso para detectar actividad sospechosa desde la pérdida.
6. Documentar la hora, la ruta del camión, las medidas adoptadas y los responsables de seguimiento.
Conclusión
El incidente debe registrarse como una pérdida de equipo corporativo con riesgo de compromiso de credenciales y exposición de información. La severidad alta es provisional: no hay evidencia confirmada de acceso malicioso, pero la sesión abierta y el acceso a la VPN justifican una respuesta urgente.

## Respuesta a Entrada 2
Clasificación del incidente
- Tipo de incidente: Posible acceso no autorizado a una cuenta de correo electrónico.
- Categoría: Ciberseguridad – Compromiso de credenciales.
- Severidad: Media (provisional), debido a que no se conoce el alcance ni el origen del acceso.
- Prioridad: Alta, hasta verificar si el acceso no autorizado continúa.
- Estado: En investigación; contraseña cambiada por el usuario.
- Impacto potencial: Exposición de información confidencial, suplantación de identidad o uso de la cuenta para atacar otros servicios.
Acciones recomendadas
1. Cerrar todas las sesiones activas desde la configuración de seguridad del correo.
2. Revisar los inicios de sesión recientes y los dispositivos conectados.
3. Activar la autenticación multifactor (MFA).
4. Verificar que no existan reglas de reenvío, filtros o métodos de recuperación desconocidos.
5. Si es una cuenta institucional, notificar al área de TI o seguridad informática para que investigue el incidente.
6. Conservar el aviso sospechoso como evidencia y no abrir enlaces ni archivos adjuntos desconocidos.
Conclusión: Se clasifica como un posible compromiso de cuenta por actividad sospechosa. Cambiar la contraseña fue una medida adecuada, pero no garantiza por sí solo que se haya bloqueado el acceso.

## Respuesta a Entrada 3
Tipo de incidente: Posible infección por malware o adware.
Justificación:
- La computadora se volvió lenta y muestra anuncios emergentes después de instalar un programa para editar PDF, lo que sugiere una posible infección por adware o malware.
- El correo sobre una factura vencida podría ser un intento de phishing, aunque leerlo sin abrir el adjunto no demuestra que el equipo esté infectado.
- La antigüedad de la computadora podría explicar la lentitud, pero no basta para justificar la aparición repentina de anuncios.
Impacto potencial: Afectación del rendimiento, exposición de información y posible compromiso de la seguridad del equipo.

Acciones recomendadas
1. Desconectar el equipo de la red: desactivar el Wi-Fi y desconectar el cable Ethernet para limitar posibles comunicaciones maliciosas.
2. No apagarlo ni seguir utilizándolo sin consultar al equipo de TI: si es un equipo institucional, seguir el protocolo interno de respuesta a incidentes. TI debe decidir si conviene preservar el estado del equipo para su análisis.
3. Notificar al área de TI o seguridad informática y reportar el programa instalado, el momento en que comenzaron los síntomas y el correo sospechoso.
4. No eliminar archivos ni instalar herramientas adicionales hasta recibir instrucciones del personal responsable.
Conclusión: El reporte debe registrarse como un posible incidente de malware con síntomas compatibles con adware y posible exposición a phishing. No se puede confirmar una infección sin un análisis técnico.