| Columna original | Qué le hiciste       | Técnica                                  | Por qué |
|---|---|---|---|
| `id` | Conservar | Ninguna | Es un identificador técnico de la fila, no de la persona; no aporta riesgo de privacidad. |
| `nombre` | Seudonimizar (reemplazar por `id_persona`) | Tabla de seudónimos (`P001`…`P040`) + `BUSCARV` | Identificador directo de máxima sensibilidad; debe desaparecer del archivo que toca el modelo. |
| `correo` | Eliminar | Ninguna (se probó enmascarar con `1***@correo.com` y se descartó) | Identificador directo; incluso enmascarado seguía exponiendo el dominio y la inicial del nombre sin aportar nada al análisis de patrones. |
| `telefono` | Eliminar | Ninguna | Identificador directo de contacto; no aporta al análisis de patrones de acceso. |
| `fecha_acceso` | Generalizar → `semana` | Número de semana del año (`WEEKNUM`) | Reduce la precisión temporal (ya no se sabe el día exacto) pero conserva la utilidad para detectar patrones por periodo. |
| `hora_entrada` | Generalizar → `franja` | Clasificación en Madrugada / Mañana / Tarde / Noche según el rango horario | Permite seguir detectando accesos fuera de horario sin exponer el minuto exacto de entrada. |
| `area` | Conservar tal cual | Ninguna | Es central para el análisis de patrones de acceso; el enunciado pide conservarla explícitamente. |
| `empresa` | Generalizar → `tipo_empresa` | Mapeo a categoría general (Constructora / Diseño / Soporte TI) | Identificador indirecto: en una empresa con pocos empleados, combinar empresa + área + hora puede bastar para identificar a alguien. |
| `motivo` | Conservar tal cual | Ninguna | Da contexto al patrón de acceso sin identificar directamente a la persona. |
