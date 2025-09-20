# Taller – Evaluación de Seguridad con STRIDE  

### Caso: CAF – Centro de Acondicionamiento Físico, Universidad de La Sabana  

---

## 📌 Flujo 1: Registro de entrada (Forms → Excel Maestro)  

### Tabla STRIDE  

| Amenaza (STRIDE)               | Ejemplo en el Flujo                                                                | Posible Impacto                                             | Estrategias de Mitigación                                                                 |
|--------------------------------|------------------------------------------------------------------------------------|-------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| **S – Spoofing**               | Un usuario se registra con cédula falsa o suplanta a otro estudiante.              | Acceso no autorizado al CAF, inconsistencias en reportes.   | Validación de identidad contra base institucional (LDAP/BD estudiantes).                  |
| **T – Tampering**              | Alteración manual de datos al copiar de Forms a Excel Maestro.                     | Errores en el registro oficial, falsificación de información.| Automatizar integración Forms → Excel Maestro; controles de integridad en los datos.      |
| **R – Repudiation**            | Un usuario niega haber ingresado en una fecha específica.                          | Conflictos en control de acceso y trazabilidad.             | Registros de entrada con sello de tiempo y logs inmutables en OneDrive/SharePoint.        |
| **I – Information Disclosure** | Acceso no autorizado a los Excels (OneDrive/SharePoint) con datos personales.      | Exposición de cédulas y datos sensibles.                    | Configuración estricta de permisos en OneDrive; cifrado en tránsito y reposo.             |
| **D – DoS**                    | Saturación de Forms/Excel impidiendo la recolección de registros.                  | Bloqueo de la operación de entrada al CAF.                   | Respaldo de formularios alternos y monitoreo de disponibilidad en O365.                   |
| **E – Elevation of Privilege** | Personal no autorizado obtiene permisos de edición en el Excel Maestro.            | Alteración masiva de datos de usuarios.                      | Control de roles en SharePoint y revisión periódica de permisos.                          |

---

## 📌 Flujo 2: Uso de lockers y llaves físicas  

### Tabla STRIDE  

| Amenaza (STRIDE)               | Ejemplo en el Flujo                                 | Posible Impacto                                   | Estrategias de Mitigación                         |
|--------------------------------|-----------------------------------------------------|---------------------------------------------------|---------------------------------------------------|
| **S – Spoofing**               | Usuario reclama un locker con identidad falsa.      | Uso indebido del servicio y robo de pertenencias. | Solicitar carnet físico institucional.            |
| **T – Tampering**              | Copia no autorizada de llaves físicas.              | Acceso indebido a lockers.                        | Uso de cerraduras numeradas y control de llaves.  |
| **R – Repudiation**            | Usuario niega haber recibido una llave.             | Conflictos en responsabilidades.                  | Registro manual con firma al entregar llave.      |
| **I – Information Disclosure** | Extracción de pertenencias privadas del locker.     | Robo de objetos personales.                       | Implementar lockers con llaves electrónicas o biometría. |
| **D – DoS**                    | Ocupación masiva de lockers con identidades falsas. | Escasez de disponibilidad para usuarios reales.   | Control de asignación y bloqueo de duplicados.    |
| **E – Elevation of Privilege** | Recepcionista otorga llave sin validar identidad.   | Acceso indebido a recursos.                       | Procedimiento estandarizado de entrega con validación. |

---

## 📌 Flujo 3: Entrenamiento y rutinas (Entrenador – Usuario)  

### Tabla STRIDE  

| Amenaza (STRIDE)               | Ejemplo en el Flujo                                      | Posible Impacto                                      | Estrategias de Mitigación                          |
|--------------------------------|----------------------------------------------------------|------------------------------------------------------|----------------------------------------------------|
| **S – Spoofing**               | Alguien se hace pasar por entrenador.                    | Rutinas inadecuadas o peligrosas para la salud.      | Identificación del personal con uniforme/carnet.   |
| **T – Tampering**              | Rutinas en papel alteradas por terceros.                 | Ejercicios erróneos, riesgo físico.                  | Registro digital básico (app/Excel controlado).    |
| **R – Repudiation**            | Entrenador niega haber asignado una rutina.              | Conflictos en responsabilidades ante accidentes.     | Bitácoras firmadas digital o físicamente.          |
| **I – Information Disclosure** | Exposición de rutinas personalizadas (ej. lesiones).     | Pérdida de privacidad en datos de salud.             | Manejo confidencial y almacenamiento restringido.  |
| **D – DoS**                    | Entrenador no disponible o exceso de usuarios atendidos. | Usuarios sin supervisión.                            | Agendar citas y definir cupos máximos por hora.    |
| **E – Elevation of Privilege** | Un usuario actúa como entrenador para dar instrucciones. | Riesgo físico a otros usuarios.                      | Validación visual y protocolos de supervisión.     |

---

## 📌 Flujo 4: Registro de salida del usuario  

### Tabla STRIDE  

| Amenaza (STRIDE)               | Ejemplo en el Flujo                                   | Posible Impacto                                      | Estrategias de Mitigación                         |
|--------------------------------|-------------------------------------------------------|------------------------------------------------------|---------------------------------------------------|
| **S – Spoofing**               | Otro estudiante registra la salida por un usuario.    | Datos inconsistentes en control de asistencia.       | Validación con cédula o carnet en salida.         |
| **T – Tampering**              | Alteración manual en el Excel Maestro para “marcar” salida inexistente. | Inconsistencias en reportes.                        | Bloquear edición libre y usar macros de validación.|
| **R – Repudiation**            | Usuario niega no haber registrado su salida.          | Dificultad para rastrear permanencia.                | Firma digital o sello de tiempo en registro.      |
| **I – Information Disclosure** | Acceso no autorizado al historial de asistencia.       | Pérdida de privacidad de datos académicos/deportivos.| Control de accesos y cifrado en OneDrive.         |
| **D – DoS**                    | Sobrecarga en el Excel Maestro (bloqueos de archivo). | Registro de salidas se interrumpe.                   | Uso de base de datos ligera en vez de Excel.      |
| **E – Elevation of Privilege** | Usuario común obtiene acceso de edición al Excel Maestro. | Manipulación de múltiples registros.                | Roles diferenciados en SharePoint con auditoría.  |
