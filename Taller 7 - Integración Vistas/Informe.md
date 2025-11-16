# Informe Final de Arquitectura: Transformación Digital del CAF

**Equipo:** Domus (Axel Ariza, Andrés Felipe Camargo y Juan Pablo Corral)
**Fecha:** 14 de Noviembre de 2025
**Materia:** Arquitectura de Negocios

---

## Resumen Ejecutivo

Este documento presenta la propuesta de arquitectura TO-BE (futura) para el Centro de Acondicionamiento Físico (CAF) de la Universidad de La Sabana. El objetivo es resolver las ineficiencias operativas, la falta de datos fiables y la experiencia de usuario deficiente identificadas en el análisis AS-IS.

La solución propuesta migra al CAF de un sistema manual basado en Excel y papel a un ecosistema digital ágil, integrado en Microsoft Teams y soportado por Power Platform. Esta arquitectura no solo automatiza los procesos clave, sino que alinea la operación tecnológica directamente con los objetivos estratégicos del negocio, creando una base sólida para la medición y el crecimiento futuro.

---

## 1. Integración de Vistas Arquitectónicas

La arquitectura de una solución no es un solo diagrama, sino una narrativa coherente que conecta múltiples vistas. Para el CAF, hemos organizado esta narrativa en cuatro capas lógicas que fluyen desde el objetivo de negocio hasta el servicio en la nube que lo ejecuta, como se visualiza en nuestro tablero integrado.

### Capa 1: Negocio (El "Por Qué")
Todo el proyecto se fundamenta en tres objetivos estratégicos del cliente:
1.  **Mejorar la experiencia del usuario**.
2.  **Reducir riesgos operativos** (como la gestión de llaves y la falta de datos).
3.  **Automatizar la captura de datos** para la toma de decisiones.

### Capa 2: Procesos (El "Cómo" Operativo)
El "Por Qué" impulsa una transformación directa en el "Cómo".
* **Proceso AS-IS:** Manual, fragmentado y propenso a errores. El registro de usuarios dependía de copiar y pegar en Excel, y el seguimiento de rutinas era inexistente o se basaba en la memoria.
* **Proceso TO-BE:** Como muestra la flecha "Transformación", el nuevo proceso (BPMN) es automatizado, interactivo y centrado en el usuario. El check-in es instantáneo y las rutinas se gestionan digitalmente, permitiendo incluso un bucle de retroalimentación en tiempo real cuando el usuario tiene dudas y consulta al entrenador.

### Capa 3: Aplicaciones y Datos (El "Con Qué")
El nuevo proceso TO-BE solo es posible gracias a una nueva arquitectura de software, como lo indica la flecha "Sistema".
* **Aplicaciones (C2):** El diagrama de contenedores TO-BE muestra los bloques de software que ejecutan el proceso: una `Power App de Usuario (Canvas)` para el check-in y consulta, y una `Power App de Gestión (Model-Driven)` para los entrenadores. Ambas se conectan a un backend unificado.
* **Datos (ERD):** La base de datos `Dataverse for Teams` (definida en la capa de infraestructura) implementa un modelo de datos relacional (ERD). Este modelo elimina la redundancia del sistema AS-IS al centralizar entidades clave como `Usuario`, `Visita` y `Rutina`.

### Capa 4: Infraestructura (El "Dónde")
Finalmente, toda la solución "Corre Sobre" una arquitectura de infraestructura lógica 100% nativa de la nube.
* **Infraestructura (TO-BE):** La solución se despliega sobre el Tenant de Microsoft 365/Azure existente en la universidad. Utiliza `Azure Active Directory` para la identidad (cumpliendo la restricción de SSO), `Power Platform` para la lógica, y `Dataverse for Teams` como la capa de datos segura y sin costo de licenciamiento adicional.

---

## 2. Aplicación al Cliente Real y Decisiones Clave

La arquitectura está diseñada para ser una respuesta directa a las necesidades y limitaciones del cliente. Cada decisión tecnológica fue tomada para maximizar el valor entregado al CAF.

### Trazabilidad de Negocio (Ejemplo)

Podemos seguir un "hilo dorado" desde el negocio hasta la infraestructura para demostrar la coherencia:

1.  **El Negocio dice:** "Necesito automatizar la captura de datos para tomar decisiones".
2.  **El Proceso responde:** "Transformaremos el registro manual en un 'Check-in Automático' en el BPMN TO-BE".
3.  **La Aplicación responde:** "Ese check-in se ejecutará en la `Power App de Usuario` y será gestionado por la `App de Gestión`".
4.  **Los Datos responden:** "El registro se guardará en la entidad `Visita` de nuestro `ERD`, que está relacionada con un único `Usuario`".
5.  **La Infraestructura responde:** "La App y los datos se ejecutarán de forma segura en `Power Platform` y `Dataverse for Teams`, autenticados por `Azure AD`".

### Decisiones Clave de Arquitectura

1.  **Decisión:** Adoptar **Power Platform (Low-Code)** en lugar de Pro-Code (Java/React) para el MVP.
    * **Justificación:** Esta decisión responde a la necesidad de agilidad y al presupuesto indefinido. Permite aprovechar las licencias de M365 existentes (costo cero de despliegue), elimina la gestión de infraestructura y acelera radicalmente el tiempo de desarrollo.

2.  **Decisión:** Usar **Dataverse for Teams** como base de datos.
    * **Justificación:** El cliente prioriza el uso del ecosistema Microsoft. Sin embargo, Dataverse for Teams es una opción técnicamente superior a SharePoint para una aplicación transaccional, ya que ofrece un modelo de datos relacional, seguro y auditable. Sus límites (2GB/1M filas) son más que suficientes para las proyecciones de 150 usuarios/día del CAF, y cumple el requisito de costo cero.

3.  **Decisión:** Desplegar en **Microsoft Teams** en lugar de la App Unisabana para el MVP.
    * **Justificación:** La integración con la App Unisabana es una restricción clave, pero también una dependencia externa que añade riesgo a un MVP. Nuestra arquitectura *cumple* con la restricción de SSO al usar `Azure AD`, y el despliegue en Teams nos da control total sobre el ciclo de vida del desarrollo. La integración con la App Unisabana se planifica como una Fase 2.

---

## 3. Análisis y Narrativa de la Arquitectura

El "porqué" fundamental de esta arquitectura es la transformación de la experiencia humana.

**La Historia del "Antes" (AS-IS):**
Un usuario llegaba al CAF y su primera interacción era una fricción: esperar en una fila, buscar su nombre en un Excel, solicitar verbalmente un locker y recibir una llave física. Su entrenamiento era una "caja negra"; su progreso se perdía en la memoria del entrenador o en papel.

**La Historia del "Después" (TO-BE):**
El usuario llega al CAF y su experiencia es fluida. Abre Microsoft Teams, una herramienta que ya usa, y pulsa "Check-in" en la App "Mi CAF". El sistema lo registra instantáneamente. Consulta en la misma app la rutina que su entrenador le diseñó. Mientras entrena, si tiene una duda, se acerca al entrenador; este consulta el historial del usuario en su propia app y le da retroalimentación personalizada. Al salir, el usuario presiona "Check-out". El sistema registra su salida, y genera un dato valioso para la analítica de aforo.

Esta narrativa demuestra una arquitectura que no solo automatiza, sino que *habilita* interacciones humanas de mayor valor, liberando al personal de tareas manuales y permitiéndoles enfocarse en el asesoramiento.

---

## 4. Reflexión Crítica y Fundamentos Metodológicos

### Reflexión de Coherencia
La arquitectura propuesta es altamente coherente y robusta. Cada componente tecnológico (Capa 4) tiene una justificación directa en la capa de aplicaciones (Capa 3), que a su vez es necesaria para ejecutar un proceso de negocio (Capa 2) diseñado para cumplir un objetivo estratégico (Capa 1).

El principal riesgo identificado no es técnico, sino de **gestión del cambio**: la solución depende de la adopción de Microsoft Teams por parte de los usuarios. Este riesgo debe mitigarse con una campaña de comunicación y onboarding liderada por Bienestar Universitario, enfocándose en los beneficios directos para el usuario (cero filas, seguimiento personalizado).

### Fundamentos Metodológicos
Para garantizar una documentación clara y alineada con las buenas prácticas de la industria, se utilizaron los siguientes marcos de referencia:

* **BPMN (Business Process Model and Notation):** Se utilizó para modelar los flujos de trabajo AS-IS y TO-BE, identificando claramente las tareas manuales, automáticas (Service Task) y de usuario (User Task).
* **C4 Model (Nivel 2 - Contenedores):** Se adaptó el Diagrama de Contenedores para definir los bloques de software principales (las Power Apps, Dataverse) y sus interacciones, respondiendo a la pregunta "El Con Qué".
* **Diagramación ERD (Entidad-Relación):** Se utilizó para diseñar el modelo de datos TO-BE, asegurando la integridad referencial y eliminando la redundancia.
* **Vistas de Infraestructura Lógica:** Se diseñó un diagrama de infraestructura en la nube para representar el despliegue de los servicios PaaS (Platform-as-a-Service) en Azure.

Esta combinación de vistas proporciona una documentación de 360 grados de la solución, asegurando que todos los interesados (negocio, desarrolladores, operaciones) tengan una comprensión clara de la arquitectura.
