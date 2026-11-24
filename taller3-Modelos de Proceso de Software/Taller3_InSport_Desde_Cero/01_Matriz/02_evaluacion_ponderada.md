# Matriz de evaluación ponderada de modelos

## Método

Se califican los modelos de 1 a 5, donde 1 = muy bajo y 5 = muy alto. En el criterio de costo/recursos, una puntuación alta significa que el modelo es viable con recursos limitados. La calificación es una valoración académica razonada para el caso InSport, no un resultado de medición experimental.

**Fórmula:** resultado = suma de (peso del criterio × calificación / 5).  
Los pesos suman 100%.

| Criterio | Peso | Razón para InSport |
|---|---:|---|
| Adaptación a cambios de requisitos | 20% | Los formularios, roles y reglas deportivas deben validarse con usuarios. |
| Entrega temprana de funcionalidad | 20% | Conviene demostrar módulos antes de terminar el sistema completo. |
| Calidad y facilidad de prueba | 15% | Se deben proteger registros, permisos, programación y resultados. |
| Gestión de riesgos | 15% | Deben controlarse pérdida/alteración de datos, accesos y errores de programación. |
| Participación de usuarios | 10% | Docentes y estudiantes deben revisar el funcionamiento. |
| Viabilidad con recursos del equipo | 10% | Es un proyecto formativo con tiempo y capacidad limitados. |
| Trazabilidad y documentación | 10% | Se necesita evidencia para evaluación y mantenimiento. |

## Calificaciones

| Modelo | Cambios 20 | Entrega 20 | Calidad 15 | Riesgos 15 | Usuarios 10 | Recursos 10 | Trazabilidad 10 | Total /100 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Cascada | 2 | 1 | 3 | 2 | 2 | 4 | 5 | 49 |
| Modelo en V | 2 | 1 | 5 | 4 | 3 | 3 | 5 | 61 |
| Incremental | 4 | 5 | 4 | 4 | 4 | 4 | 4 | **84** |
| Prototipos desechables | 5 | 3 | 3 | 3 | 5 | 4 | 3 | 75 |
| Espiral / WINWIN | 4 | 3 | 5 | 5 | 4 | 1 | 4 | 76 |
| Concurrente | 3 | 4 | 3 | 3 | 3 | 3 | 3 | 64 |
| UP/RUP | 3 | 3 | 4 | 4 | 3 | 2 | 5 | 68 |
| Scrum | 5 | 5 | 4 | 3 | 5 | 4 | 3 | **86** |
| XP (prácticas) | 4 | 4 | 5 | 4 | 4 | 3 | 3 | 79 |
| DevOps | 4 | 5 | 5 | 4 | 3 | 3 | 4 | 83 |

## Interpretación y selección

Scrum obtiene 86/100 e incremental 84/100. No son alternativas incompatibles: Scrum es un marco de organización del trabajo y el desarrollo incremental es una estrategia de construcción y entrega. Por eso se propone un ciclo de vida incremental gestionado con Scrum, complementado con prácticas de XP y controles DevOps proporcionales.

DevOps obtiene una puntuación alta como conjunto de prácticas de entrega y operación, pero no reemplaza por sí solo el modelo de desarrollo ni se recomienda prometer despliegue productivo continuo sin infraestructura aprobada.

## Sensibilidad y límites

- Las calificaciones pueden cambiar si el instructor exige un modelo específico o si se confirma un requisito crítico nuevo.
- La evaluación es cualitativa; no representa estadísticas de proyectos reales.
- Si la disponibilidad de usuarios para revisar cada Sprint es baja, Scrum pierde parte de su ventaja.
- Si el sistema debe cumplir regulación o criticidad elevada, el Modelo en V y una gestión de riesgos más formal podrían ganar peso.
