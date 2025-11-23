# Matriz de Evaluación de Riesgos Arquitectónicos

**Proyecto:** CAF - Arquitectura TO-BE
**Versión:** 1.0

Esta matriz identifica los riesgos potenciales asociados a la implementación de la arquitectura propuesta y las estrategias de mitigación diseñadas.

| ID | Riesgo | Probabilidad | Impacto | Estrategia de Mitigación (Arquitectura) |
|:--:|:---|:---:|:---:|:---|
| **R01** | **Adopción del Usuario:** Resistencia al cambio para usar la App en lugar del registro verbal tradicional. | Media | Alto | **Diseño UX/UI:** Integración nativa en Microsoft Teams (herramienta familiar) y campaña de "Quick Wins" (cero filas) para incentivar el uso. |
| **R02** | **Límites de Almacenamiento:** Dataverse for Teams tiene un límite de 2GB por entorno. | Baja | Medio | **Ciclo de Vida del Dato:** Implementación de una política de archivado automático (Cold Storage) hacia SharePoint/Azure Blob para datos históricos > 2 años. |
| **R03** | **Dependencia de Conectividad:** Fallos de internet en el campus detienen el ingreso. | Baja | Alto | **Modo Offline:** La PWA (Power Apps) se configura con capacidades offline básicas para permitir el check-in local y sincronización posterior. |
| **R04** | **Vendor Lock-in:** Alta dependencia del ecosistema Microsoft. | Alta | Bajo | **Estandarización de Datos:** El modelo de datos está diseñado con estándares relacionales exportables, facilitando una eventual migración si la estrategia TI cambia. |
| **R05** | **Privacidad de Datos:** Exposición de datos médicos (tamizajes) de usuarios. | Baja | Crítico | **Seguridad por Diseño:** Uso de *Row-Level Security* en Dataverse y autenticación MFA de Azure AD. Los datos sensibles solo son visibles para el rol "Médico/Entrenador". |

**Conclusión del Análisis:**
Los riesgos identificados son manejables dentro de la arquitectura propuesta. La solución es viable técnica y operativamente, con planes de contingencia claros para los escenarios de fallo más probables.
