## 🟣 1. Consentimiento y Principios de Tratamiento de Datos  
**Normas:** Ley 1581 de 2012, Decreto 1377 de 2013, ISO 27001 – A.18.1.4  

| Nº | Criterio de Cumplimiento | Nivel de Cumplimiento | Evidencia / Justificación | Recomendación |
|----|----------------------------|------------------------|----------------------------|----------------|
| 1 | Obtención del consentimiento informado antes del tratamiento de datos personales | ⚠️ Parcial | La plataforma solicita aceptación de términos y condiciones, pero no presenta un aviso de privacidad detallado sobre finalidad, uso, ni derechos del titular. | Implementar un aviso de privacidad visible y un registro digital del consentimiento por cada trámite. |
| 2 | Principio de finalidad (los datos solo se usan para el propósito declarado) | ✔️ Cumple | En los trámites públicos la finalidad está explícita en el tipo de gestión (certificados, peticiones, etc.), lo que se alinea con la finalidad legítima del tratamiento. | Mantener documentada la relación entre cada tipo de dato y su finalidad. |
| 3 | Principio de libertad (tratamiento solo con autorización) | ⚠️ Parcial | Aunque el portal requiere autenticación, no existe evidencia clara de control para evitar el tratamiento sin autorización expresa. | Incorporar un mecanismo que bloquee el procesamiento si el consentimiento no está verificado. |

---

## 🔵 2. Seguridad de la Información y Confidencialidad  
**Normas:** ISO/IEC 27001 (A.9, A.10, A.12, A.13), Ley 1581 – Art. 19  

| Nº | Criterio de Cumplimiento | Nivel de Cumplimiento | Evidencia / Justificación | Recomendación |
|----|----------------------------|------------------------|----------------------------|----------------|
| 4 | Control de acceso y autenticación de usuarios | ⚠️ Parcial | El sistema usa autenticación, pero no se especifica si hay políticas de contraseñas seguras o autenticación multifactor. | Implementar MFA y controles de bloqueo de sesión tras intentos fallidos. |
| 5 | Cifrado de datos sensibles en tránsito y reposo | ⚠️ Parcial | No se evidencia uso obligatorio de HTTPS/TLS ni cifrado en base de datos para campos sensibles. | Asegurar el cifrado SSL/TLS y el cifrado de datos sensibles (AES o RSA) en reposo. |
| 6 | Gestión de incidentes de seguridad | ❌ No cumple | No se observa un plan de respuesta a incidentes ni registro de brechas de seguridad. | Definir un procedimiento de respuesta a incidentes, con responsable, tiempos y registro de eventos. |
| 7 | Copias de seguridad y continuidad operativa | ✔️ Cumple | Al ser un portal estatal, se presume respaldo de información conforme a lineamientos gubernamentales. | Documentar políticas de backup y realizar pruebas periódicas de restauración. |

---

## 🟢 3. Retención, Eliminación y Actualización de Datos  
**Normas:** Ley 1581 – Art. 11 y 12; ISO 27001 – A.18.1.3  

| Nº | Criterio de Cumplimiento | Nivel de Cumplimiento | Evidencia / Justificación | Recomendación |
|----|----------------------------|------------------------|----------------------------|----------------|
| 8 | Definición de plazos de retención | ⚠️ Parcial | Los datos permanecen en el sistema sin una política clara de retención diferenciada según el tipo de trámite. | Establecer una política de retención de datos con tiempos máximos según el tipo de información. |
| 9 | Derecho de rectificación, actualización o supresión | ⚠️ Parcial | Los usuarios pueden solicitar cambios mediante PQRs, pero el procedimiento no es inmediato ni automatizado. | Incluir en la interfaz una opción directa para ejercer derechos ARCO (Acceso, Rectificación, Cancelación y Oposición). |
| 10 | Eliminación segura de datos | ❌ No cumple | No hay evidencia de mecanismos de eliminación segura (borrado lógico o físico). | Implementar procesos de eliminación segura y registros de auditoría cuando se supriman datos. |

---

## 🟠 4. Roles, Responsabilidades y Auditoría  
**Normas:** ISO 27001 – A.6, A.16; Ley 1581 – Art. 17 y 18  

| Nº | Criterio de Cumplimiento | Nivel de Cumplimiento | Evidencia / Justificación | Recomendación |
|----|----------------------------|------------------------|----------------------------|----------------|
| 11 | Designación de un Responsable y Encargado del tratamiento de datos | ⚠️ Parcial | El sistema pertenece al Estado, pero no se evidencia la figura del responsable designado para el manejo de datos. | Designar formalmente un Delegado de Protección de Datos (DPO) conforme al marco legal. |
| 12 | Registro de actividades y trazabilidad de accesos | ⚠️ Parcial | El sistema parece tener logs de acceso, pero no se especifica su alcance ni retención. | Implementar trazabilidad completa de acciones sobre datos personales con auditorías periódicas. |
| 13 | Auditorías internas de cumplimiento | ❌ No cumple | No hay evidencia de revisiones o auditorías de seguridad e integridad del tratamiento. | Realizar auditorías anuales conforme a ISO 27001 y Ley 1581. |

---

## 🔴 5. Prevención de Fugas y Riesgos Tecnológicos  
**Normas:** ISO 27001 – A.12.4, A.14; Habeas Data Art. 4-5  

| Nº | Criterio de Cumplimiento | Nivel de Cumplimiento | Evidencia / Justificación | Recomendación |
|----|----------------------------|------------------------|----------------------------|----------------|
| 14 | Control de exportación o descarga masiva de datos personales | ⚠️ Parcial | Los usuarios pueden descargar certificados, pero no hay límites claros para accesos masivos. | Implementar límites por sesión y monitoreo de patrones de descarga inusuales. |
| 15 | Gestión de vulnerabilidades técnicas | ❌ No cumple | No hay evidencia de escaneo de vulnerabilidades ni actualizaciones regulares. | Implementar pruebas de penetración y parches periódicos de software. |
| 16 | Política de uso aceptable por parte de funcionarios | ⚠️ Parcial | No se evidencia un código de conducta ni acuerdos de confidencialidad para empleados. | Establecer políticas de uso aceptable, acuerdos de confidencialidad y capacitaciones. |
