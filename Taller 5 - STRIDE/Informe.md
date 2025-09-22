# Informe de Análisis de Seguridad para el CAF

## 1. Introducción y Resumen Ejecutivo
Este informe proporciona los resultados de un estudio de seguridad realizado en el proceso básico (CAF) del Centro de acondicionamiento físico (CAF). Para determinar la debilidad actual del flujo de trabajo, la evaluación se realizó con un modelo de amenaza de pasos (falsificación, manipulación, rechazo, información sobre información, rechazo de servicios y mayores privilegios). 

El diagnóstico general muestra que la herramienta de oficina general (formularios de Microsoft, Excel, SharePoint) y el uso excesivo de procesos manuales para manejar una cirugía significativa se asocia con riesgos importantes en todas las categorías.

La amenaza reveló el recubrimiento, reemplazando la identidad de datos y el procesamiento para distribuir información privada y terminación del servicio. El modelo operativo actual es débil y no cumple con las prácticas de seguridad apropiadas para dichos servicios.

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
