# 🛠️ Taller 6 – Checklist de Cumplimiento Normativo  
### Cliente: Centro de Acondicionamiento Físico (CAF) – Universidad de La Sabana  
**Equipo:** [Nombre del equipo]  
**Fecha:** [dd/mm/aaaa]  
**Curso:** Arquitectura Empresarial – AREM  
**Asistente Virtual:** AEVA  

---

## 🎯 Objetivo
Verificar los aspectos legales, normativos y de cumplimiento aplicables al sistema de información y procesos del CAF, tomando como referencia marcos como la **Ley 1581 de 2012 (Habeas Data)**, **ISO/IEC 27001**, y otras buenas prácticas de seguridad y gobernanza de datos.

---

## 🧩 1. Contexto del Cliente

**Entidad:** Centro de Acondicionamiento Físico – Universidad de La Sabana  
**Sector:** Educación / Bienestar Universitario  
**Procesos evaluados:**
1. **Registro al CAF:** incluye captura de datos personales y médicos de estudiantes, profesores y administrativos.  
   - El registro incluye lectura y aceptación del **tratamiento de datos personales**.  
   - Los archivos se almacenan localmente en equipos del CAF.  
2. **Rutina de entrenamiento personalizada:** comunicación directa entre entrenador y usuario sobre objetivos, dolencias y evolución física.  

**Aspectos técnicos:**
- Información almacenada en **archivos Excel** locales.  
- Solo **empleados autorizados del CAF** pueden acceder a los datos, aunque no existen medidas avanzadas de seguridad (cifrado, logs, auditoría).  
- Existe **responsable institucional formal** como parte de la estructura universitaria.  

---

## ⚖️ 2. Normativas Analizadas

| Marco / Norma | Enfoque principal | Aplicabilidad al CAF |
|----------------|-------------------|----------------------|
| **Ley 1581 de 2012 (Habeas Data)** | Protección de datos personales en Colombia | Obligatoria: manejo de datos personales y médicos |
| **Decreto 1377 de 2013** | Reglamenta Ley 1581 sobre consentimiento y avisos de privacidad | Aplica: los usuarios deben aceptar políticas al registrarse |
| **ISO/IEC 27001** | Gestión de seguridad de la información | Recomendado como guía para controles y auditorías |
| **Protección contra fugas de datos** | Control de acceso, trazabilidad y cifrado | Alta relevancia por uso de archivos locales |
| **Consentimiento informado y roles** | Gobernanza y control del tratamiento de datos | Cumple parcialmente: hay responsable formal pero sin plan de auditoría |
| **Normativas sectoriales (MinSalud, MinTIC)** | Protección de datos de salud y confidencialidad | Aplica por manejo de datos médicos sensibles |

---

## 🧾 3. Checklist – Hoja 1 (Cumplimiento)

| Nº | Categoría | Criterio de Cumplimiento | Nivel de Cumplimiento (✅ / ⚠️ / ❌) | Evidencia / Justificación | Recomendación |
|----|------------|---------------------------|-------------------------------------|---------------------------|----------------|
| 1 | Habeas Data | Política de tratamiento de datos personales publicada y disponible | ✅ | Los usuarios leen y aceptan la política al registrarse | Mantener actualizada la política y realizar revisión anual |
| 2 | Habeas Data | Registro de consentimiento informado | ✅ | Se obtiene consentimiento explícito durante el registro | Digitalizar y centralizar registros para trazabilidad |
| 3 | ISO 27001 | Control de acceso a la información | ⚠️ | Solo empleados del CAF acceden, pero sin autenticación segura ni logs | Implementar contraseñas seguras y bitácoras de acceso |
| 4 | ISO 27001 | Copias de respaldo y recuperación ante desastres | ❌ | Información local sin respaldo automatizado | Habilitar almacenamiento seguro en nube institucional |
| 5 | Protección de Datos | Cifrado de información sensible | ❌ | Archivos Excel sin cifrado | Cifrar los archivos o migrar a sistema seguro (p. ej., SharePoint) |
| 6 | Auditoría y trazabilidad | Registro de accesos y modificaciones | ❌ | No existen registros de quién modifica los datos | Crear un sistema básico de logs o control de cambios |
| 7 | Roles y Responsabilidades | Designación formal de responsables de datos | ✅ | CAF cuenta con responsables institucionales | Definir funciones específicas de protección de datos en el CAF |
| 8 | Sectorial (MinSalud) | Manejo ético y confidencial de datos médicos | ⚠️ | Se manejan datos médicos en archivos abiertos | Restringir visualización y capacitar al personal sobre confidencialidad |

---

## 🧩 4. Hoja 2 (Brechas y Priorización)

| Categoría | Brecha | Riesgo | Recomendación Prioritaria | Nivel de Prioridad |
|------------|--------|--------|----------------------------|--------------------|
| ISO 27001 | Falta de control avanzado y trazabilidad | Fuga o modificación indebida de datos | Implementar autenticación y registro de accesos | 🔴 Alta |
| Protección de Datos | No existe cifrado ni respaldo automatizado | Pérdida de información sensible | Configurar respaldos en nube institucional y cifrado básico | 🔴 Alta |
| Auditoría | No hay trazabilidad de cambios | No se puede identificar uso indebido de datos | Crear log de modificaciones o usar sistema centralizado | 🟠 Media |
| Sectorial | Falta de protocolo de manejo de datos médicos | Riesgo ético y reputacional | Establecer guía de confidencialidad y capacitación anual | 🟡 Baja |

---

## 🧠 5. Informe Técnico – Hallazgos y Recomendaciones

**Hallazgos principales:**
- Cumplimiento básico con la **Ley 1581** (consentimiento y política vigente).  
- Existencia de **responsables formales**, aunque sin procesos de auditoría definidos.  
- **Controles de acceso mínimos** (sólo personal del CAF), pero sin mecanismos de seguridad avanzados.  
- Ausencia de **cifrado, respaldo automático y trazabilidad**, lo cual representa vulnerabilidad operativa.  

**Recomendaciones generales:**
1. Implementar **cifrado y respaldos automáticos** en la nube institucional.  
2. Activar **autenticación con credenciales personales** para cada colaborador del CAF.  
3. Establecer un **registro de accesos y modificaciones** (bitácora digital o logs).  
4. Crear un **protocolo de confidencialidad de datos médicos** y capacitar al personal.  
5. Realizar **auditorías internas semestrales** de cumplimiento normativo.  

---

## 📚 6. Referencias Normativas

- **Ley 1581 de 2012 – Protección de Datos Personales (Colombia)**  
- **Decreto 1377 de 2013 – Reglamentación de Habeas Data**  
- **ISO/IEC 27001:2022 – Information Security Management Systems**  
- **Guía MinTIC – Protección de Datos Personales y Seguridad de la Información**  
- **Resolución 1995 de 1999 – Historia Clínica (MinSalud)**  

---

## 📊 7. Conclusión
El CAF cumple con los principios básicos del Habeas Data, pero presenta **brechas técnicas y operativas** en materia de seguridad y trazabilidad.  
La adopción de **controles de seguridad digital, respaldo en la nube y auditorías internas** permitirá fortalecer su cumplimiento normativo y proteger la información sensible de sus usuarios.

---
