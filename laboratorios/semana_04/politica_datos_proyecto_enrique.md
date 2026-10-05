# Política de datos del proyecto IA para detectar el cáncer

## 1\. Alcance

Esta política cubre los datos de pacientes que usa el proyecto:

- D1 Nombre: personal  
- D2 Teléfono: personal  
- D3 Edad: personal  
- D4 Tipo de sangre: sensible (dato de mayor riesgo)  
- D5 Fecha de la consulta o toma de muestra: personal

## 2\. Ciclo de vida

Referencia: diagrama `ciclo_vida_dato_proyecto.drawio` y `.png` en `laboratorios/semana04`.

- Captura: Recepcionista  
- Almacenamiento: Administrador del sistema  
- Uso: Analista de datos y Responsable clínico  
- Compartición: Líder del proyecto  
- Retención: Administrador del sistema  
- Eliminación: Administrador del sistema

## 3\. Normativa aplicable

- LFPDPPP (DOF, 20 de marzo de 2025): obligatoria en México; regula los datos personales y el dato sensible D4.  
- Ley de IA de la UE (Reglamento 2024/1689): no obligatoria en México; se usa como referencia y aplicaría si el sistema se usara en la UE, según su clasificación de riesgo (Art. 6).  
- NIST AI RMF 1.0: marco voluntario que guía la gestión de riesgos, sesgos y supervisión humana.  
- Se evaluaron 12 requisitos en `matriz_cumplimiento_proyecto.xlsx`, y el cruce con el diagrama agregó 8 controles.

## 4\. Controles comprometidos

- Consentimiento firmado y aviso de privacidad integral y simplificado. Responsable: Recepcionista.  
- Captura limitada a D1 a D5 y disociación de D1 y D2 antes del análisis. Responsable: Analista de datos.  
- Registro de riesgos antes de producción y revisión de representatividad por grupo de edad. Responsables: Líder del proyecto y Analista de datos.  
- Validación de cada resultado y canal para pedir revisión humana. Responsable: Responsable clínico.  
- Plazo de retención, bloqueo al vencer y borrado seguro con acta. Responsable: Administrador del sistema.  
- Cifrado en reposo, acceso por rol con doble factor y registro de accesos. Responsable: Administrador del sistema.  
- Contratos con los proveedores de nube y de IA, y anonimización antes de enviar datos. Responsable: Líder del proyecto.  
- Plan de respuesta a incidentes con aviso a pacientes. Responsable: Líder del proyecto.

## 5\. Manejo de datos con herramientas de IA

Aplica a ChatGPT, Gemini, Deepseek, Dify y cualquier otra herramienta externa.

- Prohibido ingresar D1, D2 y D4 reales, o cualquier dato real que permita identificar a un paciente.  
- Permitido: datos ficticios o sintéticos con la misma estructura (por ejemplo, un CSV de prueba).  
- Datos reales sólo si están disociados: sin D1 y D2, con edades en rangos y fechas por mes, tras revisar el riesgo de reidentificación.  
- Aun disociados, solo se usan en herramientas aprobadas por el Líder del proyecto con contrato vigente.  
- Nunca se pegan consentimientos, expedientes ni capturas de pantalla con datos de pacientes.  
- Cada uso de una herramienta externa se anota con fecha, herramienta y datos usados.  
- Todo artículo de ley o dato que entregue un modelo se verifica contra la fuente oficial antes de usarlo.

## 6\. Revisión

- Esta política se revisa cada seis meses y ante cambios: nueva herramienta de IA, nuevo tercero, nuevo dato o cambio de ley.  
- La aprueba el Líder del proyecto.  
- El Responsable de datos personales atiende las solicitudes de derechos ARCO (Art. 29 de la LFPDPPP).  
- Cada cambio se registra con un commit en el repositorio.