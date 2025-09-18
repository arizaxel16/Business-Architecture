# Taller 5 – Evaluación de Seguridad con STRIDE

### Caso: EdukIT – Plataforma de Educación Virtual

---

## Flujo 1: Acceso de Estudiantes a Cursos y Materiales

### Tabla STRIDE

| Amenaza (STRIDE)                                             | Ejemplo en el Flujo                                        | Posible Impacto                                                 | Estrategias de Mitigación                                     |
|--------------------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------------|---------------------------------------------------------------|
| **S – Spoofing (Suplantación)**                              | Un atacante se hace pasar por un estudiante válido.        | Acceso no autorizado a cursos y recursos pagos.                 | Autenticación multifactor, detección de anomalías en login.   |
| **T – Tampering (Manipulación)**                             | Alteración de URLs para descargar materiales restringidos. | Distribución ilegal de contenido.                               | Validación de tokens y controles de integridad en descargas.  |
| **R – Repudiation (Repudio)**                                | El estudiante niega haber accedido a cierto material.      | Dificultad para auditoría académica y resolución de conflictos. | Registro seguro (logs con sellado de tiempo y no repudio).    |
| **I – Information Disclosure (Divulgación de información)**  | Exposición de materiales internos a usuarios no inscritos. | Pérdida de propiedad intelectual.                               | Control de permisos por rol y cifrado de datos en tránsito.   |
| **D – Denial of Service (DoS)**                              | Ataque que sobrecarga el servidor de contenidos.           | Interrupción en el acceso a cursos.                             | Escalamiento automático de recursos y mitigación anti-DDoS.   |
| **E – Elevation of Privilege (Escalamiento de privilegios)** | Un estudiante consigue permisos de administrador.          | Alteración de calificaciones y materiales.                      | Principio de mínimo privilegio y revisión periódica de roles. |

---

## 📌 Flujo 2: Publicación de Contenidos por Docentes

### Tabla STRIDE

| Amenaza (STRIDE)               | Ejemplo en el Flujo                                          | Posible Impacto                                 | Estrategias de Mitigación                                     |
|--------------------------------|--------------------------------------------------------------|-------------------------------------------------|---------------------------------------------------------------|
| **S – Spoofing**               | Un atacante suplanta a un docente para subir material falso. | Contenido malicioso en la plataforma.           | MFA, certificados digitales para validación de identidad.     |
| **T – Tampering**              | Modificación de archivos ya publicados.                      | Pérdida de integridad del contenido.            | Versionado seguro y hash de archivos.                         |
| **R – Repudiation**            | Un docente niega haber publicado cierto contenido.           | Conflictos legales o reputacionales.            | Logs firmados y trazabilidad en el CMS.                       |
| **I – Information Disclosure** | Acceso a borradores o material privado.                      | Filtración de exámenes o evaluaciones.          | Roles diferenciados y cifrado en repositorio.                 |
| **D – DoS**                    | Sobrecarga en la subida de archivos.                         | Bloqueo temporal en la publicación de material. | Limitación de tamaño de archivos y control de tasa de subida. |
| **E – Elevation of Privilege** | Un docente obtiene permisos de administrador.                | Alteración de notas o configuración global.     | Controles RBAC estrictos y auditorías periódicas.             |

---

## 📌 Flujo 3: Procesamiento de Pagos con Terceros

### Tabla STRIDE

| Amenaza (STRIDE)               | Ejemplo en el Flujo                                         | Posible Impacto                             | Estrategias de Mitigación                                   |
|--------------------------------|-------------------------------------------------------------|---------------------------------------------|-------------------------------------------------------------|
| **S – Spoofing**               | Suplantación de identidad de usuario en pagos.              | Fraudes financieros.                        | Integración con pasarela PCI-DSS, MFA.                      |
| **T – Tampering**              | Alteración de montos en la transacción.                     | Pérdida económica para la empresa.          | Validación de datos entre EdukIT y pasarela de pago.        |
| **R – Repudiation**            | Usuario niega haber realizado un pago.                      | Disputas legales y de servicio.             | Generación de comprobantes digitales con firma electrónica. |
| **I – Information Disclosure** | Exposición de datos de tarjeta o cuenta bancaria.           | Robo de identidad y fraude.                 | Tokenización de tarjetas y cifrado extremo a extremo.       |
| **D – DoS**                    | Ataque que bloquea la integración con el servicio de pagos. | Imposibilidad de registrar transacciones.   | Redundancia de proveedores y failover automático.           |
| **E – Elevation of Privilege** | Un atacante accede a funciones administrativas de pagos.    | Manipulación de cuentas y desvío de fondos. | Segregación de funciones y auditoría continua.              |

---

## 📌 Flujo 4: Almacenamiento de Datos Personales y Notas Académicas

### Tabla STRIDE

| Amenaza (STRIDE)               | Ejemplo en el Flujo                                       | Posible Impacto                         | Estrategias de Mitigación                        |
|--------------------------------|-----------------------------------------------------------|-----------------------------------------|--------------------------------------------------|
| **S – Spoofing**               | Acceso no autorizado a bases de datos.                    | Filtración de datos personales.         | Autenticación fuerte y control de accesos DB.    |
| **T – Tampering**              | Modificación de notas por un atacante.                    | Pérdida de integridad académica.        | Controles de integridad y registros de cambios.  |
| **R – Repudiation**            | Estudiante niega haber modificado datos personales.       | Confusión en la gestión académica.      | Auditoría con trazabilidad de modificaciones.    |
| **I – Information Disclosure** | Exposición de datos sensibles (DNI, historial académico). | Riesgos legales y pérdida de confianza. | Cifrado en reposo (AES-256) y en tránsito (TLS). |
| **D – DoS**                    | Ataque que impide consultas a la base de datos.           | Caída del sistema académico.            | Replicación y balanceo de carga.                 |
| **E – Elevation of Privilege** | Un usuario común obtiene permisos de administrador de BD. | Alteración masiva de datos.             | Control granular de roles y monitoreo SIEM.      |