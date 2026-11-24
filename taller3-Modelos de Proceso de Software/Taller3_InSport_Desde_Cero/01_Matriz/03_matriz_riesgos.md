# Matriz inicial de riesgos de InSport

Escala: Probabilidad (P) e Impacto (I) de 1 a 5. Nivel = P × I.  
1-4 Bajo; 5-9 Medio; 10-15 Alto; 16-25 Crítico.  
Los valores son estimaciones iniciales que deben validarse con el equipo y los usuarios.

| ID | Riesgo | Categoría | P | I | Nivel | Prevención | Contingencia | Responsable sugerido |
|---|---|---|---:|---:|---:|---|---|---|
| R01 | Requisitos incompletos o contradictorios sobre inscripción y disciplinas | Funcional | 4 | 4 | 16 Crítico | Entrevistas, historias de usuario y criterios de aceptación | Repriorizar backlog y ajustar incremento | Product Owner |
| R02 | Inscripciones duplicadas de un estudiante | Datos | 3 | 4 | 12 Alto | Restricción única, validación servidor y pruebas | Depurar duplicados con registro de auditoría | Desarrollo |
| R03 | Usuario accede a funciones de profesor/admin sin autorización | Seguridad | 3 | 5 | 15 Alto | Control de acceso por rol en servidor y pruebas negativas | Revocar sesión, corregir permisos y revisar registros | Desarrollo / Seguridad |
| R04 | Pérdida o corrupción de registros | Operativo | 2 | 5 | 10 Alto | Copias de seguridad, transacciones y control de cambios | Restaurar respaldo y reconciliar datos | Responsable de datos |
| R05 | Choque de horarios o asignación duplicada de equipos | Funcional | 3 | 4 | 12 Alto | Reglas de validación y pruebas de escenarios | Reprogramar y notificar a afectados | Analista |
| R06 | Resultados modificados por usuario no autorizado o sin trazabilidad | Integridad | 3 | 5 | 15 Alto | Permisos, historial de cambios y confirmación | Restaurar resultado válido y auditar | Profesor/admin |
| R07 | Baja disponibilidad de docentes para validar | Proyecto | 4 | 3 | 12 Alto | Agendar revisiones y definir representante | Validar con casos acordados y registrar supuestos | Product Owner |
| R08 | Errores de integración entre interfaz, backend y base de datos | Técnico | 3 | 4 | 12 Alto | Contratos, integración frecuente y pruebas | Volver a versión estable y corregir por módulo | Equipo técnico |
| R09 | Exposición de datos personales | Seguridad/privacidad | 3 | 5 | 15 Alto | Minimización de datos, permisos, HTTPS y secretos protegidos | Contener incidente, informar según protocolo institucional y corregir | Responsable de seguridad |
| R10 | Dependencia de servicio externo o librería vulnerable | Técnico | 3 | 3 | 9 Medio | Inventario, actualización y revisión de licencias | Sustituir dependencia o fijar versión segura | Desarrollo |
| R11 | Retraso por alcance excesivo | Gestión | 4 | 4 | 16 Crítico | MVP, priorización MoSCoW y límites de Sprint | Reducir alcance no esencial | Scrum Master / PO |
| R12 | Despliegue falla o deja la aplicación fuera de servicio | Operativo | 2 | 4 | 8 Medio | Ambiente de prueba, checklist y respaldo | Rollback a versión estable | Operaciones |

## Revisión

La matriz debe revisarse al inicio y final de cada Sprint, y cuando cambien los requisitos, la arquitectura o el entorno de despliegue. Los riesgos críticos R01 y R11 deben tratarse antes de ampliar el alcance. Los riesgos de seguridad y datos requieren pruebas específicas, no solo revisión visual.
