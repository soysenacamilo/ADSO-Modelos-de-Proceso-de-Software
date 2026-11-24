# Diagrama 3. Pipeline CI/CD propuesto

```mermaid
flowchart TD
    A[Commit en Git] --> B[Revisión por pares]
    B --> C[Integración continua]
    C --> D[Análisis estático y revisión de dependencias]
    D --> E[Pruebas unitarias]
    E --> F[Pruebas de integración]
    F --> G{¿Pasan los controles?}
    G -- No --> H[Registrar defecto y corregir]
    H --> A
    G -- Sí --> I[Crear versión candidata]
    I --> J[Desplegar a staging / pruebas]
    J --> K[Validación de usuarios]
    K --> L{¿Aprobado?}
    L -- No --> H
    L -- Sí --> M[Respaldo y checklist]
    M --> N{Autorización de liberación}
    N -- No --> J
    N -- Sí --> O[Despliegue autorizado]
    O --> P[Monitoreo y soporte]
```

La publicación en producción solo se realiza si existe autorización institucional y un ambiente real disponible. Para una entrega académica puede demostrarse hasta staging.
