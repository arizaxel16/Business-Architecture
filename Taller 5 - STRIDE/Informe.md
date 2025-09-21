# Informe de Análisis de Seguridad para el CAF

## 1. Introducción y Resumen Ejecutivo
Este informe presenta los resultados de un análisis de seguridad realizado sobre los procesos operativos críticos del Centro de Acondicionamiento Físico (CAF) de la Universidad de La Sabana. La evaluación se llevó a cabo utilizando el modelo de amenazas **STRIDE** (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege) para identificar vulnerabilidades en los flujos de trabajo actuales.

El diagnóstico general revela que la alta dependencia de procesos manuales y el uso de herramientas de ofimática de propósito general (Microsoft Forms, Excel, SharePoint) para gestionar operaciones críticas introducen riesgos de seguridad significativos en todas las categorías.  

Las amenazas identificadas van desde la suplantación de identidad y la alteración de datos hasta la exposición de información personal y la interrupción del servicio. Se concluye que el modelo operativo actual es frágil y no cumple con las buenas prácticas de seguridad para un servicio de esta naturaleza.

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
- La integridad de los datos de asistencia está comprometida.  
- La transferencia manual de datos desde Forms al Excel Maestro es un punto crítico de **Tampering**.  
- La falta de una autenticación robusta facilita el **Spoofing**.  
- La ausencia de un registro de auditoría inmutable abre la puerta a amenazas de **Repudiation**.  
- El almacenamiento en Excel, un sistema no diseñado para concurrencia, presenta un riesgo de **Denial of Service** por bloqueos de archivo.  

### 3.2 Flujo de Uso de Lockers
- Este proceso, basado en llaves físicas, es inherentemente inseguro.  
- Las llaves pueden ser duplicadas (**Tampering**) o entregadas sin una validación de identidad adecuada (**Spoofing** y **Elevation of Privilege**).  
- El principal riesgo es la seguridad física de las pertenencias de los usuarios.  

### 3.3 Flujo de Entrenamiento
- Este es el flujo con mayor riesgo de privacidad y seguridad física.  
- La gestión de rutinas en "papel y memoria" impide cualquier trazabilidad (**Repudiation**).  
- Se exponen datos potencialmente sensibles sobre la salud de los usuarios (**Information Disclosure**).  
- No existen garantías contra la suplantación de identidad de entrenadores (**Spoofing**), lo que podría derivar en lesiones.  

---

## 4. Conclusión del Diagnóstico
El análisis concluye que el nivel de riesgo de la operación actual es **alto**. Las estrategias de mitigación actuales son parches manuales sobre un sistema fundamentalmente inseguro.  

Se requiere una **reingeniería de los procesos** soportada por una **arquitectura tecnológica diseñada con la seguridad como pilar fundamental**.
