# Informe de Análisis de Seguridad para el CAF

## 1. Introducción y Resumen Ejecutivo
Los hallazgos de un estudio de seguridad efectuado en los procesos operativos fundamentales del Centro de Acondicionamiento Físico (CAF) de la Universidad de La Sabana se exponen en este informe. Para detectar debilidades en los flujos de trabajo actuales, se realizó la evaluación con el modelo de amenazas **STRIDE** (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service y Elevation of Privilege).

El diagnóstico general muestra que el empleo de herramientas de ofimática de uso general (Microsoft Forms, Excel, SharePoint) y la excesiva dependencia de procesos manuales para administrar operaciones esenciales conllevan riesgos importantes en términos de seguridad en todas las categorías. 

Las amenazas detectadas abarcan desde la sustitución de identidad y la manipulación de datos hasta la divulgación de información privada y el cese del servicio. Se determina que el modelo operativo en curso es débil y no se ajusta a las prácticas de seguridad adecuadas para un servicio de este tipo.

---

## 2. Metodología de Análisis: Modelo STRIDE
**STRIDE** es un modelo de clasificación de amenazas de seguridad que se enfoca en identificar diferentes tipos de vulnerabilidades en un sistema. Las seis categorías son:

- **Spoofing (Suplantación de identidad):** Falsificar la identidad de un usuario o componente.  
- **Tampering (Alteración de datos):** Modificar datos sin autorización.  
- **Repudiation (No repudio):** Negar haber realizado una acción.  
- **Information Disclosure (Revelación de información):** Exponer información a quienes no deberían tener acceso.  
- **Denial of Service (Denegación de servicio):** Impedir que el sistema funcione para usuarios legítimos.  
- **Elevation of Privilege (Elevación de privilegios):** Obtener permisos o accesos que no corresponden.  

---

## 3. Análisis de Flujos Críticos y Diagnóstico Técnico
El análisis STRIDE se aplicó a cuatro flujos de trabajo fundamentales del CAF, revelando un patrón de vulnerabilidades sistémicas.

### 3.1 Flujo de Registro (Entrada y Salida)
- La integridad de los datos relacionados con la asistencia está en peligro.  
- Un aspecto crítico de **Tampering** es la transferencia manual de datos desde Forms hacia el Excel Maestro.  
- La ausencia de una autenticación sólida favorece el **spoofing**.  
- La falta de un registro de auditoría inalterable facilita que ocurran amenazas de **Repudiation**.  
- El almacenamiento en Excel, una plataforma no creada para ser utilizada de manera concurrente, tiene un peligro de **Denial of Service** debido a bloqueos de archivo.  

### 3.2 Flujo de Uso de Lockers
- Este procedimiento, que se fundamenta en llaves físicas, es intrínsecamente inseguro.  
- Las llaves pueden ser replicadas (**Tampering**) o entregadas sin la verificación apropiada de identidad (**spoofing** y **Elevation of Privilege**).  
- La seguridad física de los objetos de los usuarios es el mayor riesgo.  

### 3.3 Flujo de Entrenamiento
- Este flujo tiene el riesgo más alto en términos de seguridad física y privacidad.  
- La administración de rutinas en "papel y memoria" imposibilita la trazabilidad (**Repudiation**).  
- Se muestra información que podría ser delicada acerca de la salud de los usuarios (**Divulgación de información**).  
- No hay garantías para evitar la suplantación de identidad de entrenadores (**Spoofing**), lo que podría resultar en lesiones.  

---

## 4. Conclusión del Diagnóstico
El análisis concluye que el nivel de riesgo de la operación actual es **alto**. Las estrategias de mitigación actuales son parches manuales sobre un sistema fundamentalmente inseguro.  

Se requiere una **reingeniería de los procesos** soportada por una **arquitectura tecnológica diseñada con la seguridad como pilar fundamental**.
