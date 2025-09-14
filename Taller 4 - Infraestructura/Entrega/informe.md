# Informe Técnico – Diagnóstico de Infraestructura del CAF (Centro de Acondicionamiento Físico)

## Integrantes
- Juan Pablo Corral
- Felipe Camargo
- Axel Ariza

---

## 1. Contexto General

El CAF de la Universidad de La Sabana cuenta con una infraestructura tecnológica mínima para soportar sus operaciones. Actualmente, la gestión de usuarios, lockers y registros de entrada/salida se realiza de forma manual utilizando archivos Excel locales, con dos computadores conectados a la red general de empleados de la universidad.

Los servicios adicionales incluyen:
- **Google Forms** para el registro inicial de nuevos usuarios.
- **Correo electrónico institucional** para notificaciones manuales y un newsletter enviado desde el sistema central de la universidad.
- **Báscula de tamizaje** desconectada de la red, con registro manual en Excel.
- **Spotify**, utilizado en los computadores para reproducir música en los parlantes del CAF.
- **Canva**, usado ocasionalmente por empleados para elaborar presentaciones corporativas o administrativas bajo demanda.

El CAF depende completamente de la infraestructura central de TI de la universidad, sin contar con recursos dedicados propios.

---

## 2. Debilidades y Cuellos de Botella Identificados

1. **Dependencia de Excels locales**
   - No existe un sistema centralizado ni en la nube.
   - Riesgo de pérdida de datos por errores humanos, fallas del PC o ausencia de respaldos.

2. **Ausencia de respaldo y recuperación (Disaster Recovery)**
   - No hay redundancia en la información.
   - Los datos se almacenan en memoria local sin políticas claras de backup.

3. **Falta de automatización en procesos críticos**
   - Registro manual de entradas/salidas y llaves de lockers genera lentitud y posibilidad de errores.
   - El tamizaje de la báscula no se integra con los sistemas digitales, aumentando la duplicidad de trabajo.

4. **Dependencia total de la red central de la universidad**
   - No existe segmentación o subneteo para el CAF.
   - Vulnerabilidad potencial en seguridad y disponibilidad.

5. **Uso limitado de servicios digitales modernos**
   - El Google Forms es un “microservicio” útil, pero aislado.
   - No hay integración con bases de datos, CRM o sistemas de reservas.

6. **Sistemas desconectados sin integración con la operación principal**
   - Spotify, aunque útil para la experiencia de usuario, no está integrado en la arquitectura de TI.
   - Canva se utiliza de manera aislada, sin un flujo estandarizado dentro de los procesos administrativos.

---

## 3. Diagnóstico Técnico

El CAF se encuentra en un **estado tecnológico básico y altamente manual**.  
Su arquitectura es **on-premise dependiente**, con dos PCs y almacenamiento local, conectados a la red institucional.

- **Eficiencia:** Baja, debido a procesos manuales y repetitivos.
- **Escalabilidad:** Nula, ya que los Excels no soportan múltiples usuarios concurrentes ni trazabilidad robusta.
- **Seguridad:** Limitada, pues no hay control de accesos digitales ni políticas de respaldo.
- **Disponibilidad:** Dependiente de la red universitaria; en caso de falla de red o del PC, las operaciones se detienen.
- **Flexibilidad:** Los sistemas desconectados (Spotify, Canva, báscula) funcionan de manera aislada y no aportan a la gestión centralizada de información.

---

## 4. Buenas Prácticas de Arquitectura de Infraestructura

Para superar las limitaciones actuales, se recomiendan **buenas prácticas** inspiradas en entornos **cloud, on-premise e híbridos**:

### 4.1. Gestión de Datos
- Migrar los Excels a un sistema de **almacenamiento centralizado en la nube** (Google Sheets, OneDrive/SharePoint, o una pequeña base de datos en la nube).
- Implementar **copias de seguridad automáticas** y control de versiones.

### 4.2. Infraestructura
- Mantener PCs locales para la operación diaria (**on-premise**).
- Usar un **modelo híbrido**, donde los datos y formularios estén en la nube pero la operación de ingreso siga en los equipos locales.
- Evaluar segmentación de la red universitaria para el CAF (**subred o VLAN**) como medida de seguridad y aislamiento.

### 4.3. Procesos y Automatización
- Reemplazar Excels con un **sistema de gestión ligero (ERP/CRM básico o SaaS especializado en gimnasios/centros deportivos)**.
- Integrar la báscula con un software que registre automáticamente los resultados.

### 4.4. Seguridad
- Aplicar **controles de acceso digital** (perfiles de usuario para administrativos).
- Cumplir con políticas de **ciberseguridad universitaria** y normativas de protección de datos (Habeas Data, GDPR si aplica).

---

## 5. Conclusión

El CAF opera actualmente con un esquema simple y manual, adecuado solo para baja escala. Sin embargo, existen **riesgos altos en términos de seguridad, disponibilidad y confiabilidad de la información**.

La transición hacia un modelo **híbrido (on-premise + cloud)** con almacenamiento centralizado, respaldo automático y herramientas digitales ligeras permitiría mejorar la eficiencia, reducir errores humanos y aumentar la confiabilidad de los datos.

Los sistemas desconectados como **Spotify** y **Canva** aportan valor al ambiente y comunicación del CAF, pero deberían incluirse en la documentación de infraestructura como **soportes auxiliares no críticos**, reforzando la visión integral de la arquitectura tecnológica.

---
