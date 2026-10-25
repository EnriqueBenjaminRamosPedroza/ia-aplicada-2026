# Iteración 1: Rol

**Modelo:** ChatGPT ver. GPT-6
**Fecha:** 24 de octubre del 2026

**Prompt usado:**
Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es un técnico que atenderá el incidente y necesita información precisa.

Clasifica este reporte de incidente:[entrada]

## Respuesta a Entrada 1
Severidad: ALTA

Campo	Clasificación
Tipo de incidente	Pérdida de activo corporativo
Categoría	Seguridad física y posible compromiso de información
Activo afectado	Laptop de trabajo extraviada
Riesgo principal	Acceso no autorizado al correo institucional y a la VPN
Confidencialidad	En riesgo
Integridad	Riesgo potencial
Disponibilidad	Posible afectación
Estado	Incidente activo; recuperación no confirmada
Cifrado del disco	Desconocido
Notificación	Jefa directa informada

Acciones inmediatas para el técnico del SOC
1. Revocar las sesiones activas del correo institucional y de otros servicios corporativos accesibles desde la laptop.
2. Deshabilitar temporalmente el acceso VPN asociado al dispositivo y revocar sus certificados o credenciales, según corresponda.
3. Bloquear o ejecutar el borrado remoto de la laptop mediante la herramienta de administración corporativa, si está disponible.
4. Cambiar las credenciales potencialmente expuestas e invalidar tokens de autenticación y sesiones persistentes.
5. Revisar los registros de acceso del correo, VPN e identidad corporativa para detectar actividad sospechosa desde la hora de la pérdida.
6. Verificar el cifrado del disco, las políticas de bloqueo y las capacidades de administración remota del equipo.
7. Documentar la cronología del incidente, identificar al responsable de su seguimiento y escalarlo al equipo de respuesta a incidentes.
Evaluación del riesgo
La pérdida física no confirma por sí sola una filtración de datos. Sin embargo, la sesión abierta y el acceso a la VPN representan un riesgo significativo, especialmente si el disco no está cifrado o existen credenciales y tokens reutilizables.

Prioridad operativa: contener los accesos de inmediato, preservar los registros de auditoría y determinar si hubo acceso no autorizado. No esperar a recuperar la laptop para aplicar las medidas de contención.

## Respuesta a Entrada 2
Clasificación del incidente de seguridad
- Categoría: Posible compromiso de cuenta (acceso no autorizado al correo electrónico).
- Severidad inicial: Media, pendiente de validación.
- Activo afectado: Cuenta de correo electrónico del usuario.
- Estado: Incidente potencialmente activo; contraseña cambiada, pero sin confirmar la contención.
- Prioridad: P2 – Atención prioritaria, sujeta a la matriz de severidad de la organización.
Descripción del incidente
El usuario reporta un aviso inusual que podría indicar un acceso no autorizado a su cuenta de correo. Se desconoce la fecha de inicio, el origen del acceso y si el atacante mantiene sesiones activas. El usuario indica que ya cambió su contraseña.
Acciones recomendadas para el técnico
1. Verificar la legitimidad del aviso y revisar los registros de inicio de sesión.
2. Revocar todas las sesiones activas y los tokens de acceso sospechosos.
3. Comprobar las reglas de reenvío, los filtros y los métodos de recuperación de la cuenta.
4. Habilitar o verificar la autenticación multifactor (MFA).
5. Revisar la actividad enviada y recibida para detectar posibles mensajes maliciosos.
6. Preservar los registros y documentar los hallazgos antes de cerrar el incidente.
Información pendiente
- Fecha y hora del aviso sospechoso.
- Ubicación, dirección IP y dispositivo asociados al inicio de sesión.
- Existencia de accesos exitosos desconocidos.
- Posible afectación de otras cuentas vinculadas.
Criterio de cierre: No cerrar el incidente hasta verificar que no existan accesos no autorizados activos y que la cuenta se encuentre protegida.

## Respuesta a Entrada 3
Categoría: Posible infección por malware o adware.

Prioridad: Media-alta (P2), provisional, pendiente de validación técnica.

Activo afectado: Computadora del usuario.

Estado: Incidente sospechoso en investigación.
1. Indicadores identificados
- Lentitud inusual del equipo: posible indicador de actividad maliciosa o consumo anormal de recursos.
- Ventanas emergentes con anuncios: posible presencia de adware o software potencialmente no deseado.
- Descarga reciente de un editor PDF: posible vector de infección, especialmente si se obtuvo de una fuente no confiable.
- Correo sobre una factura vencida: posible intento de phishing. Leer el mensaje sin abrir el adjunto reduce algunos riesgos, pero no descarta otros mecanismos de ataque.
2. Acciones recomendadas para el técnico
1. Aislar el equipo de la red: desconectar Wi-Fi y cable Ethernet para limitar posibles comunicaciones maliciosas. No conectarlo a otras redes.
2. No apagar ni reiniciar inmediatamente: mantenerlo aislado mientras se determina si es necesario preservar evidencia volátil. Si existe actividad destructiva o riesgo de propagación, seguir el protocolo de contención de la organización.
3. Registrar evidencias: hora de detección, nombre y origen del programa PDF, capturas de las ventanas emergentes y detalles del correo sospechoso.
4. Investigar el equipo: revisar procesos, programas instalados recientemente, extensiones del navegador, registros de seguridad y alertas del antivirus o EDR.
5. Ejecutar análisis antimalware siguiendo el procedimiento corporativo, preferentemente con herramientas autorizadas.
6. Escalar al equipo de respuesta a incidentes si se confirma malware, aparecen indicadores de compromiso o se detecta actividad sospechosa adicional.
3. Información pendiente
- ¿De qué sitio se descargó el editor PDF?
- ¿Se instaló y ejecutó el programa?
- ¿El antivirus detectó alguna amenaza?
- ¿Las ventanas emergentes aparecen incluso cuando el navegador está cerrado?
- ¿Se observaron accesos desconocidos, cambios en archivos o conexiones sospechosas?
Conclusión para el registro SOC: Reporte compatible con una posible infección por adware o malware posterior a la instalación de software. El correo podría ser un evento independiente de phishing; no hay evidencia suficiente para atribuirle la infección. Se recomienda contención preventiva, análisis técnico y escalamiento según los resultados.
