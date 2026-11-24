# DOCUMENTO TÉCNICO DE ARQUITECTURA DE PROCESOS Y CICLO DE VIDA DEL SOFTWARE

**PROYECTO:** InSport - Plataforma de gestión de actividades deportivas e intercursos  
**PROGRAMA:** Análisis y Desarrollo de Software (ADSO)  
**EQUIPO EVALUADOR:** [Completar nombres de los integrantes]  
**FECHA DE REVISIÓN:** 24 de noviembre de 2026  
**VERSIÓN DEL DOCUMENTO:** 1.0.0  

---

# 1. RESUMEN EJECUTIVO Y CONTEXTO DEL PROYECTO

## 1.1. Descripción general del problema y dominio del negocio

En las instituciones educativas, la organización de actividades deportivas puede requerir recopilar inscripciones, identificar cursos y disciplinas, conformar grupos, programar encuentros y registrar resultados. Cuando la información se administra de forma dispersa mediante hojas de cálculo, formularios independientes o mensajes, pueden presentarse duplicidad de datos, errores de programación, demoras para consultar participantes y dificultad para mantener un historial confiable.

InSport se plantea como una aplicación web que centraliza estos procesos. Los estudiantes podrán registrarse y seleccionar una disciplina deportiva disponible. Los perfiles autorizados de profesor o administración podrán consultar inscripciones, organizar participantes, gestionar programación y registrar resultados.

El sistema se considera un proyecto formativo ADSO. El alcance descrito es una propuesta académica inicial y debe confirmarse con el instructor y los usuarios institucionales. No se asume que ya exista una integración con sistemas oficiales, pagos, reconocimiento biométrico o infraestructura productiva.

## 1.2. Alcance técnico del sistema

**Incluido en el alcance propuesto:**
- Registro e inicio de sesión de usuarios.
- Identificación de perfiles: estudiante, profesor y administrador.
- Registro de datos básicos del estudiante y curso.
- Selección de disciplina deportiva disponible.
- Consulta y administración de inscripciones.
- Organización de participantes/equipos según reglas definidas por la institución.
- Programación y consulta de encuentros.
- Registro y consulta de resultados por perfiles autorizados.
- Validación de datos, control de acceso y trazabilidad de operaciones relevantes.
- Interfaz web adaptable a computador y dispositivos móviles.

**Fuera del alcance inicial, salvo aprobación posterior:**
- Reconocimiento facial o biométrico.
- Pagos en línea.
- Aplicación móvil nativa.
- Integración automática con plataformas externas institucionales.
- Analítica predictiva o inteligencia artificial.
- Despliegue de alta disponibilidad empresarial.

## 1.3. Matriz de requerimientos funcionales (RF) críticos

| ID | Requerimiento funcional propuesto | Prioridad | Criterio de aceptación |
|---|---|---|---|
| RF-01 | El sistema permitirá registrar una cuenta de estudiante con los datos definidos por la institución. | Alta | Un registro válido queda almacenado y el sistema confirma el resultado. |
| RF-02 | El sistema permitirá iniciar sesión y cerrar sesión. | Alta | Credenciales válidas permiten entrar; inválidas no conceden acceso. |
| RF-03 | El sistema diferenciará los perfiles estudiante, profesor y administrador. | Alta | Cada perfil solo visualiza y ejecuta las funciones autorizadas. |
| RF-04 | El estudiante podrá consultar y seleccionar una disciplina disponible. | Alta | La inscripción queda asociada al estudiante y a una disciplina existente. |
| RF-05 | El profesor/admin podrá consultar la lista de inscritos. | Alta | La lista presenta datos consistentes y filtros acordados. |
| RF-06 | El perfil autorizado podrá organizar participantes o equipos. | Media | El sistema guarda la conformación y evita asignaciones incompatibles definidas por la institución. |
| RF-07 | El perfil autorizado podrá programar encuentros. | Alta | El encuentro guarda equipos/participantes, fecha, hora y lugar; valida conflictos acordados. |
| RF-08 | El perfil autorizado podrá registrar resultados. | Alta | El resultado se guarda y queda asociado al encuentro. |
| RF-09 | Los usuarios podrán consultar información publicada según su rol. | Media | La consulta no expone funciones ni datos restringidos. |
| RF-10 | El sistema conservará un historial de cambios relevantes. | Media | Se registra quién realizó la operación, cuándo y qué dato fue modificado, según el diseño aprobado. |

## 1.4. Matriz de requerimientos no funcionales (RNF) críticos

Los valores siguientes son objetivos iniciales sugeridos, no compromisos medidos. Deben validarse con el instructor y el entorno real.

| ID | Atributo | Requisito propuesto | Verificación |
|---|---|---|---|
| RNF-01 | Rendimiento | En el entorno de prueba, las consultas comunes deberán responder en un tiempo objetivo de hasta 3 segundos con una carga académica acordada. | Prueba de rendimiento con datos representativos. |
| RNF-02 | Seguridad | Las contraseñas no se almacenarán en texto plano; las operaciones protegidas exigirán autenticación y autorización en servidor. | Revisión de código y pruebas de acceso. |
| RNF-03 | Integridad | No se permitirán inscripciones duplicadas según la regla de unicidad aprobada. | Pruebas de duplicidad y restricciones de datos. |
| RNF-04 | Disponibilidad | El sistema deberá estar disponible durante las jornadas y horarios definidos para las actividades deportivas, sujeto a la infraestructura disponible. | Pruebas de operación y revisión de registros. |
| RNF-05 | Usabilidad | Los flujos principales deberán ser comprensibles para estudiantes y docentes, con mensajes claros y validaciones visibles. | Pruebas de tareas con usuarios. |
| RNF-06 | Compatibilidad | La interfaz deberá funcionar en versiones actuales de navegadores comunes y adaptarse a pantallas móviles. | Pruebas en navegadores y tamaños de pantalla. |
| RNF-07 | Mantenibilidad | El código se organizará por responsabilidades, con nombres claros, control de versiones y documentación mínima. | Revisión técnica y estructura del repositorio. |
| RNF-08 | Privacidad | Solo se recopilarán datos necesarios para la operación; el acceso a datos personales se limitará por rol. | Revisión de campos, permisos y pruebas. |
| RNF-09 | Recuperación | Se definirá un procedimiento de respaldo y restauración adecuado al entorno de despliegue. | Simulación documentada de restauración. |
| RNF-10 | Concurrencia | Las operaciones simultáneas no deberán generar registros duplicados ni sobrescribir cambios incompatibles. | Pruebas concurrentes sobre operaciones críticas. |

**Operación offline:** no se considera requisito confirmado. Si la institución necesita registrar información sin conexión, debe añadirse como requisito explícito y diseñarse una estrategia de sincronización y resolución de conflictos.

# 2. ANÁLISIS DE RIESGOS TÉCNICOS, OPERATIVOS Y REGULATORIOS

## 2.1. Identificación y categorización de riesgos

La matriz detallada se encuentra en `../01_Matriz/03_matriz_riesgos.md`. Se usa una escala de probabilidad e impacto de 1 a 5. Los principales riesgos iniciales son:

| Riesgo | Probabilidad | Impacto | Nivel | Tratamiento |
|---|---:|---:|---:|---|
| Requisitos incompletos o contradictorios | 4 | 4 | 16 Crítico | Entrevistas, historias de usuario y aceptación por incremento. |
| Alcance excesivo y retraso | 4 | 4 | 16 Crítico | MVP, priorización y control del backlog. |
| Acceso indebido a funciones administrativas | 3 | 5 | 15 Alto | Autorización en servidor y pruebas negativas. |
| Modificación no autorizada de resultados | 3 | 5 | 15 Alto | Roles, auditoría e historial de cambios. |
| Exposición de datos personales | 3 | 5 | 15 Alto | Minimización, controles de acceso y protección de comunicaciones. |
| Conflictos de programación | 3 | 4 | 12 Alto | Reglas explícitas y validación de horarios. |

## 2.2. Mapeo de riesgos derivados del incumplimiento de RNF

| RNF afectado | Riesgo | Consecuencia |
|---|---|---|
| Seguridad | Autorización incorrecta | Un estudiante podría modificar información reservada a docentes. |
| Integridad | Falta de restricciones y validaciones | Inscripciones duplicadas o resultados inconsistentes. |
| Rendimiento | Consultas sin optimización | Demoras en periodos de alta demanda. |
| Disponibilidad/recuperación | Falta de respaldos o procedimiento | Pérdida prolongada de información. |
| Privacidad | Recolección o exposición innecesaria | Afectación de datos personales de estudiantes. |
| Usabilidad | Formularios confusos | Errores de inscripción y abandono del proceso. |

## 2.3. Estrategias preventivas y contingencias técnicas

1. **Prevención de errores funcionales:** revisar historias de usuario, criterios de aceptación y prototipos antes de construir funciones complejas.
2. **Protección de acceso:** validar permisos en el servidor, no únicamente ocultar botones en la interfaz.
3. **Integridad de datos:** aplicar validaciones en interfaz y backend, restricciones de base de datos y transacciones cuando corresponda.
4. **Control de cambios:** usar Git, ramas o una estrategia de commits acordada, revisiones por pares y etiquetas de versiones estables.
5. **Pruebas:** automatizar pruebas unitarias y de integración para las reglas críticas; realizar pruebas de aceptación con usuarios.
6. **Respaldo:** establecer periodicidad, responsable, ubicación segura y prueba de restauración según la infraestructura real.
7. **Contingencia:** ante un error de despliegue, detener la publicación, regresar a la versión estable y registrar la causa.

# 3. ESTUDIO COMPARATIVO Y VALIDACIÓN DE MODELOS DE PROCESO

## 3.1. Matriz maestra de validación comparativa

La matriz completa se presenta en `../01_Matriz/01_matriz_maestra.md`. Se evaluaron modelos prescriptivos, evolutivos, especializados, ágiles y de entrega continua. La conclusión principal es:

- **Apto:** modelo incremental; Scrum como marco de organización; prototipos desechables para descubrir requisitos; prácticas de XP y FDD como apoyo.
- **Parcialmente apto:** Cascada, V, prototipos evolutivos, Espiral, concurrente, UP/RUP, ASD, DSDM, Crystal, DevOps, CBD y DSOA.
- **No apto como enfoque general:** métodos formales, por su costo y especialización desproporcionados para el alcance y criticidad conocidos de InSport.

Los veredictos no significan que un modelo sea universalmente bueno o malo; expresan su ajuste al contexto descrito.

## 3.2. Matriz de evaluación ponderada

La matriz numérica se encuentra en `../01_Matriz/02_evaluacion_ponderada.md`. Los pesos priorizan adaptación a cambios (20%), entrega temprana (20%), calidad (15%), riesgos (15%), participación (10%), viabilidad de recursos (10%) y trazabilidad (10%).

| Alternativa | Resultado |
|---|---:|
| Scrum | 86/100 |
| Incremental | 84/100 |
| DevOps | 83/100 |
| XP (prácticas) | 79/100 |
| Espiral / WINWIN | 76/100 |
| Prototipos desechables | 75/100 |

La puntuación de Scrum no significa que sustituya al modelo incremental. Scrum organiza el trabajo y el incremental describe la estrategia de entrega del producto.

## 3.3. Sustentación de modelos descartados

- **Cascada como modelo único:** no se selecciona porque los requisitos de inscripción, organización y programación pueden cambiar después de las primeras demostraciones. Se conservan sus actividades de documentación y aprobación cuando sean útiles.
- **Modelo en V completo:** no se selecciona como ciclo principal porque su estructura de verificación formal puede resultar pesada. Se adopta su principio de relacionar cada requisito con pruebas.
- **Espiral completo:** no se selecciona por la carga de análisis de riesgos y negociación que supone para un proyecto formativo de alcance moderado. Se conservan revisiones periódicas de riesgos.
- **RUP completo:** no se adopta por su complejidad y documentación potencialmente excesiva; se aprovechan casos de uso y arquitectura inicial.
- **Métodos formales:** no se justifican para el nivel de criticidad conocido. Las reglas de negocio sí se expresarán con precisión y se probarán.
- **DevOps como metodología única:** DevOps complementa desarrollo y operación; no reemplaza el proceso de análisis, diseño y construcción.
- **Prototipo evolutivo sin controles:** se evita convertir una maqueta rápida en producto final sin refactorización, pruebas y revisión de seguridad.

# 4. PROPUESTA METODOLÓGICA SELECCIONADA O DISEÑADA

## 4.1. Justificación técnica de la elección

Se selecciona una **arquitectura de proceso híbrida: desarrollo incremental + Scrum + prácticas técnicas de XP + controles DevOps básicos**.

- El enfoque incremental permite entregar el sistema por módulos funcionales.
- Scrum proporciona planificación, revisión y retrospectiva por Sprint.
- XP aporta pruebas, integración frecuente, refactorización y diseño simple.
- DevOps aporta control de versiones, automatización de pruebas y preparación de despliegues reproducibles.
- El prototipado desechable se usa al comienzo para validar pantallas y flujos con estudiantes y docentes.

La selección se ajusta al equipo formativo: permite demostrar avances, aprender de la retroalimentación y limitar el riesgo de desarrollar todo el sistema antes de validarlo.

## 4.2. Diagrama de flujo del ciclo de vida adoptado

El diagrama Mermaid está en `../03_Diagramas/01_ciclo_de_vida.md`. El ciclo propuesto es:

1. Diagnóstico y levantamiento de requisitos.
2. Priorización del Product Backlog y definición del MVP.
3. Diseño de arquitectura y prototipos.
4. Planificación del Sprint.
5. Construcción incremental.
6. Pruebas y revisión técnica.
7. Sprint Review con usuarios.
8. Retrospectiva y actualización de riesgos.
9. Integración y despliegue a ambiente de prueba.
10. Aceptación y liberación, si existe autorización.

**Puertas de control (stage-gates):**
- **G1 - Alcance aprobado:** problema, usuarios, RF/RNF y límites definidos.
- **G2 - Arquitectura validada:** componentes, datos, seguridad y riesgos principales revisados.
- **G3 - Incremento aceptado:** criterios de aceptación cumplidos y pruebas aprobadas.
- **G4 - Liberación autorizada:** respaldo, configuración, seguridad y plan de reversa revisados.

## 4.3. Definición de hitos de control

Los hitos LHO, LCA e IOC se incluyen como referencias de control inspiradas en los hitos de fijación de objetivos del modelo Espiral; no se afirma que el proyecto adopte el modelo Espiral completo.

| Hito | Aplicación en InSport | Evidencia |
|---|---|---|
| LHO - Life Cycle Objectives | Acordar propósito, alcance, usuarios, restricciones y viabilidad. | Acta de alcance, RF/RNF iniciales y riesgos principales. |
| LCA - Life Cycle Architecture | Confirmar que la arquitectura propuesta soporta los casos críticos y mitiga riesgos principales. | Diagrama de arquitectura, modelo de datos, decisiones técnicas y pruebas de concepto si son necesarias. |
| IOC - Initial Operational Capability | Demostrar una versión con capacidad operativa inicial en ambiente autorizado. | Incremento integrado, pruebas, manual breve y aceptación. |
| Sprint Review | Inspeccionar el incremento con usuarios o representante. | Acta de revisión y backlog actualizado. |
| Definition of Done | Establecer condiciones mínimas para considerar terminada una funcionalidad. | Código revisado, pruebas aprobadas, documentación y criterios satisfechos. |

## 4.4. Estructura de roles y responsabilidades

| Rol | Responsabilidades |
|---|---|
| Product Owner (representante de usuarios/instructor designado) | Prioriza necesidades, aclara requisitos y acepta o rechaza resultados según criterios acordados. |
| Scrum Master / facilitador | Facilita eventos, ayuda a resolver impedimentos y promueve el uso correcto del marco. |
| Developers / equipo de desarrollo | Analiza, diseña, programa, prueba, integra y documenta el incremento. |
| Usuario estudiante | Aporta necesidades y prueba flujos de inscripción y consulta. |
| Usuario docente | Valida listados, organización, programación y resultados. |
| Responsable de calidad (función del equipo) | Verifica criterios, registra defectos y revisa evidencias de pruebas. |
| Responsable de configuración/despliegue (función del equipo) | Administra repositorio, versiones, ambientes, respaldos y publicaciones autorizadas. |

En un equipo pequeño una persona puede asumir varias funciones, pero las responsabilidades deben quedar claras. Los roles de usuario no tienen que ser miembros del equipo de desarrollo.

## 4.5. Operacionalización de las actividades sombrilla

| Actividad sombrilla | Aplicación continua | Evidencia |
|---|---|---|
| Seguimiento y control | Revisar avance, bloqueos, alcance y cumplimiento del Sprint. | Tablero, actas y estado del backlog. |
| Gestión de riesgos | Revisar probabilidad, impacto y acciones al inicio/final de cada Sprint. | Matriz de riesgos actualizada. |
| SQA - Aseguramiento de calidad | Definir estándares, revisar código y verificar criterios de aceptación. | Lista de chequeo, revisión por pares y reportes de pruebas. |
| SCM - Gestión de configuración | Controlar versiones de código, documentación y configuración. | Repositorio Git, commits, ramas, etiquetas y registro de cambios. |
| Revisiones técnicas formalizadas | Revisar requisitos, diseño, código y casos de prueba con lista de chequeo. | Registro de hallazgos y correcciones. |
| Gestión de reusabilidad | Evaluar librerías y componentes antes de reutilizarlos; revisar licencia, versión, seguridad y compatibilidad. | Inventario de dependencias y decisiones de reutilización. |

Las actividades estructurales de comunicación, planeación, modelado, construcción y despliegue se ejecutan en cada incremento. Las actividades sombrilla se mantienen durante todo el ciclo, no solamente al final.

# 5. PLAN DE ARTEFACTOS, ENTREGABLES Y ESTRATEGIA DE VERIFICACIÓN / DESPLIEGUE

## 5.1. Matriz de artefactos por fase

| Fase | Artefactos/documentos | Producto técnico | Responsable |
|---|---|---|---|
| Diagnóstico | Acta de alcance, mapa de interesados, RF/RNF, riesgos iniciales | Backlog inicial y prototipo desechable | PO + analista |
| Arquitectura | Casos de uso, modelo de datos, diagrama de componentes, decisiones técnicas | Estructura inicial del proyecto | Equipo técnico |
| Planificación | Objetivo del Sprint, tareas, criterios de aceptación | Sprint Backlog | Developers |
| Construcción | Historias, diseño de interfaz, registro de cambios | Código fuente del incremento | Developers |
| Verificación | Casos de prueba, resultados, defectos | Suite de pruebas y versión corregida | Calidad + Developers |
| Revisión | Acta de revisión, comentarios de usuarios | Incremento aceptado o lista de ajustes | PO + usuarios |
| Despliegue | Checklist, configuración, respaldo y plan de reversa | Versión en ambiente autorizado | Responsable de despliegue |
| Mantenimiento | Incidentes, cambios y retrospectivas | Correcciones y nuevas versiones | Equipo |

## 5.2. Estrategia de verificación y validación

**Verificación:** comprobar que el producto se construye correctamente respecto a especificaciones.  
**Validación:** comprobar que el producto resuelve las necesidades reales de estudiantes y docentes.

| Nivel | Qué se prueba en InSport | Ejemplo de criterio de aceptación |
|---|---|---|
| Revisión de requisitos | Claridad, consistencia, trazabilidad y testabilidad de RF/RNF. | Cada RF tiene criterio de aceptación verificable. |
| Pruebas unitarias | Validadores, reglas de inscripción, cálculo/validación de resultados si aplica. | Entradas válidas e inválidas producen el comportamiento esperado. |
| Pruebas de integración | Comunicación entre interfaz, backend y base de datos. | Un registro válido puede consultarse posteriormente con el rol autorizado. |
| Pruebas de sistema | Flujos completos por rol. | Estudiante se inscribe; docente consulta; usuario autorizado registra resultado. |
| Pruebas de seguridad | Autenticación, autorización, validación de entradas y exposición de datos. | Un estudiante no puede ejecutar operaciones administrativas ni consultar datos restringidos. |
| Pruebas de rendimiento | Consultas comunes con volumen de datos acordado. | Se cumple el objetivo inicial de respuesta bajo el escenario de prueba documentado. |
| Pruebas de aceptación | Usuarios revisan tareas reales y criterios acordados. | Docente y estudiante completan sus tareas principales sin defectos bloqueantes. |
| Regresión | Funciones anteriores tras cada cambio. | Las pruebas críticas siguen aprobadas después de integrar cambios. |

**Criterios mínimos para aceptar un incremento:**
- Los criterios de aceptación de la historia están cumplidos.
- No existen defectos críticos o altos sin tratamiento acordado.
- Las pruebas unitarias e integración definidas para el incremento pasan.
- Los permisos se verifican en servidor.
- El cambio está integrado en el repositorio y revisado.
- La documentación afectada se actualiza.
- El Product Owner o representante designado revisa el resultado.

## 5.3. Estrategia DevOps y pipeline CI/CD

La estrategia se implementará de manera gradual y según las herramientas e infraestructura disponibles. No se presupone que InSport ya tenga un servidor productivo.

**Flujo propuesto:**
1. El desarrollador realiza cambios en una rama o flujo de trabajo acordado.
2. Se crea un commit con mensaje descriptivo.
3. Se solicita revisión por pares cuando sea posible.
4. La integración ejecuta análisis estático y pruebas automatizadas disponibles.
5. Si las verificaciones pasan, se genera un artefacto o versión candidata.
6. Se publica en ambiente de prueba autorizado.
7. Los usuarios revisan y el equipo corrige observaciones.
8. La liberación a producción requiere autorización, respaldo y plan de reversa.

**Ambientes:**
- Desarrollo: trabajo diario del equipo.
- Pruebas/staging: validación integrada con datos de prueba.
- Producción: únicamente si la institución autoriza infraestructura, responsables y manejo de datos.

**Controles DevSecOps:**
- No almacenar contraseñas, tokens ni claves en el repositorio.
- Usar variables de entorno o gestor de secretos disponible.
- Mantener dependencias actualizadas y revisar vulnerabilidades.
- Validar entradas y permisos en backend.
- Usar HTTPS en ambientes publicados.
- Limitar privilegios de cuentas y servicios.
- Registrar errores y operaciones sensibles sin almacenar contraseñas ni datos innecesarios.
- Proteger respaldos y comprobar su restauración.

**Indicadores iniciales:**
- Frecuencia de integración: al menos una integración validada por Sprint.
- Porcentaje de pruebas automatizadas aprobadas: registrar resultado por ejecución.
- Defectos críticos abiertos: objetivo cero al aceptar un incremento.
- Tiempo de corrección de defectos: medir desde el registro hasta la solución.
- Éxito de despliegue: registrar despliegues exitosos y fallidos, sin fijar una meta irreal antes de tener datos.

# 6. DECLARACIÓN DE USO ÉTICO DE HERRAMIENTAS Y REFERENCIAS BIBLIOGRÁFICAS

## 6.1. Declaración de transparencia y uso ético de IA generativa / herramientas de apoyo

Para la elaboración de este documento se pueden utilizar herramientas digitales y de inteligencia artificial generativa como apoyo para organizar ideas, revisar redacción, proponer estructuras y explicar conceptos. Su uso no reemplaza la lectura de las fuentes, el análisis del equipo ni la validación de requisitos con los usuarios.

El equipo debe revisar, corregir y comprender todo contenido asistido por IA antes de entregarlo. No se deben inventar entrevistas, pruebas ejecutadas, resultados medidos, aprobaciones institucionales ni referencias. Los datos de estudiantes deben manejarse con autorización y minimización. El equipo conserva la responsabilidad sobre la exactitud, originalidad, privacidad y cumplimiento de las normas académicas.

**Declaración para completar por el equipo:**  
“Declaramos que las herramientas de apoyo utilizadas fueron: [indicar herramientas]. Se utilizaron para: [describir tareas]. El equipo verificó y ajustó el contenido, y asume la responsabilidad del documento y de los resultados presentados.”

## 6.2. Referencias bibliográficas

[1] R. S. Pressman y B. R. Maxim, *Software Engineering: A Practitioner's Approach*, 8.ª ed. New York: McGraw-Hill Education, 2015. Consultar especialmente el capítulo 4, “Process Models”, y el capítulo 5, “Agile Development”, en esta edición. **Nota:** la guía del taller menciona capítulos 2 y 3; la numeración cambia entre ediciones. En la 9.ª edición, McGraw-Hill ubica “Process Models” en el capítulo 2 y “Agility and Process” en el capítulo 3. El equipo debe citar la edición que realmente consulte.

[2] R. S. Pressman y B. R. Maxim, *Software Engineering: A Practitioner's Approach*, 9.ª ed. McGraw-Hill, 2024. Capítulos 2, “Process Models”, y 3, “Agility and Process”.

[3] K. Schwaber y J. Sutherland, *The Scrum Guide: The Definitive Guide to Scrum: The Rules of the Game*, noviembre de 2020. Disponible en: https://scrumguides.org/

[4] Manifesto for Agile Software Development, “Manifesto for Agile Software Development”, 2001. Disponible en: https://agilemanifesto.org/

[5] Google Cloud, “DevOps capabilities”, documentación técnica. Disponible en: https://docs.cloud.google.com/architecture/devops

[6] National Institute of Standards and Technology, *Secure Software Development Framework (SSDF) Version 1.1: Recommendations for Mitigating the Risk of Software Vulnerabilities*, NIST SP 800-218, febrero de 2022. Disponible en: https://csrc.nist.gov/pubs/sp/800/218/final

[7] R. S. Pressman, *Ingeniería del software: un enfoque práctico*, 7.ª ed. McGraw-Hill, 2010. Usar esta referencia solo si esa es la edición consultada por el equipo.

---

## Control final de cumplimiento

| Elemento exigido por la guía | Ubicación |
|---|---|
| Investigación de modelos prescriptivos, evolutivos, especializados, UP, ágiles y DevOps | Matriz maestra + secciones 3 y 4 |
| Actividades estructurales y sombrilla | Sección 4.5 |
| Caso de estudio, RF y RNF | Sección 1 |
| Matriz inicial de riesgos | Sección 2 y archivo de riesgos |
| Matriz maestra comparativa | Archivo `01_matriz_maestra.md` |
| Evaluación ponderada | Archivo `02_evaluacion_ponderada.md` |
| Descarte de modelos | Sección 3.3 |
| Selección pura/híbrida/personalizada | Sección 4.1 |
| Diagrama de ciclo de vida y stage-gates | Carpeta de diagramas |
| Hitos de control | Sección 4.3 |
| Roles y responsabilidades | Sección 4.4 |
| SQA, SCM, riesgos, revisiones y reusabilidad | Sección 4.5 |
| Artefactos por fase | Sección 5.1 |
| Verificación, validación y aceptación | Sección 5.2 |
| DevOps, CI/CD, ambientes y DevSecOps | Sección 5.3 |
| Uso ético de IA | Sección 6.1 |
| Referencias y Pressman | Sección 6.2 |
