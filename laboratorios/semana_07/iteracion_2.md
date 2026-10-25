# Iteración 2: Rol + Contexto

**Modelo:** ChatGPT ver. GPT-6
**Fecha:** 24 de octubre del 2026

**Prompt usado:**
Eres analista de seguridad de primer nivel en un centro de operaciones. Tu lector es un técnico que atenderá el incidente y necesita información precisa.

Contexto: este texto proviene de un formulario que llenan usuarios sin conocimientos técnicos. Los tipos de incidente posibles son: acceso no autorizado, phishing, malware, pérdida de dispositivo, otro. Las severidades posibles son: baja, media, alta.

Clasifica este reporte de incidente: [entrada]

## Respuesta a Entrada 1
Clasificación del incidente
- Tipo de incidente: Pérdida de dispositivo.
- Severidad: Alta.
- Descripción: Laptop de trabajo extraviada en un camión de la ruta 12. El dispositivo contiene una sesión de correo institucional abierta y acceso a la VPN corporativa. Se desconoce si el disco está cifrado. La empresa de transporte confirmó que no tiene el equipo. La jefa directa ya fue notificada.
Acciones prioritarias para el técnico del SOC:
1. Revocar las sesiones activas del correo institucional e invalidar los tokens de autenticación.
2. Revocar o deshabilitar temporalmente las credenciales y el acceso VPN asociados al usuario.
3. Activar el bloqueo remoto y localizar el dispositivo, si las herramientas corporativas lo permiten.
4. Verificar el cifrado del disco y evaluar la exposición de información corporativa.
5. Revisar los registros de acceso para detectar actividad sospechosa posterior a la pérdida.
6. Documentar el incidente y escalarlo al equipo responsable de seguridad y protección de datos.
Justificación de severidad: Se clasifica como alta por el riesgo de acceso no autorizado a sistemas corporativos y correo institucional. El cifrado del disco es desconocido y las sesiones permanecen abiertas, por lo que debe tratarse como un posible compromiso hasta verificar los controles de seguridad.

## Respuesta a Entrada 2
Clasificación del incidente
- Tipo: Acceso no autorizado.
- Severidad: Media.
- Justificación: El usuario sospecha que alguien accedió a su correo electrónico tras recibir una notificación inusual. No se ha confirmado el acceso ni se conoce el alcance del incidente. El cambio de contraseña es una medida inicial, pero no garantiza que la cuenta esté protegida.
- Acciones recomendadas:
  1. Verificar la legitimidad de la notificación y revisar el historial de inicios de sesión.
  2. Cerrar todas las sesiones activas y revocar los dispositivos o aplicaciones desconocidos.
  3. Activar la autenticación multifactor (MFA).
  4. Revisar las reglas de reenvío, los métodos de recuperación y los cambios recientes en la cuenta.
  5. Escalar a severidad alta si se confirma el acceso malicioso, el robo de información o el compromiso de otras cuentas.
Estado: Pendiente de investigación y confirmación del acceso no autorizado.

## Respuesta a Entrada 3
Clasificación del incidente de seguridad
- Tipo de incidente: Malware.
- Severidad: Media.
- Justificación: La computadora presenta lentitud inusual y ventanas emergentes con anuncios después de instalar un programa para editar PDF. Estos síntomas son compatibles con una posible infección por adware o software potencialmente no deseado. El correo sobre la factura vencida podría ser un intento de phishing, aunque el usuario indica que no abrió el archivo adjunto. No hay evidencia suficiente para confirmar una infección o un acceso no autorizado.
- Acciones recomendadas:
  1. Aislar la computadora de la red desconectando el Wi-Fi o el cable Ethernet.
  2. No apagarla ni reiniciarla hasta que el equipo de respuesta determine si es necesario preservar evidencias.
  3. Informar al equipo de seguridad y registrar el programa descargado, su origen y la hora aproximada de instalación.
  4. Realizar un análisis antimalware y revisar los programas instalados recientemente.
  5. Conservar el correo sospechoso para su análisis y evitar interactuar con sus enlaces o archivos adjuntos.
Prioridad de atención: Investigar cuanto antes la posible infección y determinar si el programa descargado es malicioso.
