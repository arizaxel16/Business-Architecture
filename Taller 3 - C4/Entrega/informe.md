### Reporte de los procesos y sistemas del CAF

---

### **1. Introducción**

Este informe describe los procesos actuales del Centro de Acondicionamiento Físico (CAF) de la Universidad de La Sabana, con un enfoque en los sistemas y actores involucrados en el ingreso y salida de los usuarios. Como arquitectos de negocio, nuestro objetivo es analizar la operación existente a través de diagramas C4 (C1 Contexto y C2 Contenedores) para identificar oportunidades de mejora y optimización.

---

### **2. Componentes Clave y Actores**

Los procesos del CAF se basan en una serie de componentes y actores clave que interactúan para gestionar la entrada y salida de los usuarios y el seguimiento de sus actividades.

#### **2.1 Componentes Clave**

* [cite_start]**Microsoft Forms**: Este es un componente clave en el proceso de registro de usuarios, ya que es la herramienta que utilizan para inscribirse y acceder a los servicios del CAF[cite: 6, 7].
* [cite_start]**Excel de Formulario**: Se sincroniza automáticamente con el formulario para tener los datos de los usuarios en un solo lugar y que sean fáciles de trabajar[cite: 8, 9].
* **Excel Maestro**: Este es el registro diario y central de todas las actividades en el CAF. [cite_start]Contiene información esencial del usuario, así como la fecha y hora de su entrada y salida[cite: 10, 11].

#### **2.2 Actores**

[cite_start]Los actores son los responsables de la ejecución de los procesos[cite: 13].

* **Usuario CAF**: Es el estudiante, profesor o empleado que utiliza el gimnasio. [cite_start]Su principal responsabilidad es completar el formulario de ingreso y devolver la llave del casillero al salir (solamente si la pidió)[cite: 12, 13, 24].
* [cite_start]**Recepcionista**: Valida la inscripción, organiza la entrega de las llaves de los casilleros y registra manualmente la entrada y salida de los usuarios en el **Excel Maestro**[cite: 13, 26].
* [cite_start]**Entrenador**: Asesora a los usuarios y les asigna rutinas de ejercicio[cite: 13, 27].

---

### **3. Flujo de Información y Procesos**

El flujo de información en el CAF es una combinación de procesos manuales y automatizados.

1.  [cite_start]**Registro Inicial**: El usuario rellena el formulario de Microsoft Forms[cite: 15].
2.  [cite_start]**Sincronización de Datos**: El formulario se sincroniza automáticamente con el Excel de Formulario[cite: 16].
3.  [cite_start]**Registro Oficial**: La recepcionista copia y pega manualmente los datos desde el Excel de Formulario al Excel Maestro, lo que constituye el registro oficial de la entrada del usuario[cite: 17, 18, 20].
4.  [cite_start]**Asignación de Rutinas**: El entrenador asigna rutinas a los usuarios, basándose en notas manuales y memoria, ya que esta información no se registra en un sistema[cite: 19, 32].
5.  [cite_start]**Registro de Salida**: La recepcionista debe registrar la salida del usuario en el Excel Maestro[cite: 21]. [cite_start]Sin embargo, este paso a menudo se omite si el usuario no tiene llave para el casillero y sale sin avisar a nadie[cite: 22].

---

### **4. Debilidades y Riesgos Identificados**

El análisis de los diagramas C4 y el flujo de trabajo actual revela varias debilidades y riesgos significativos.

* [cite_start]**Proceso Manual Crítico**: La dependencia del proceso manual de copiar y pegar datos entre los archivos de Excel introduce un alto riesgo de errores humanos, como duplicación de entradas o datos faltantes, del Excel de formulario hacia el Excel maestro[cite: 29].
* [cite_start]**Inconsistencia en el Registro de Salida**: Los usuarios sin casillero no registran la salida, lo que genera una inconsistencia en los datos y no permite un registro completo[cite: 31].
* [cite_start]**Falta de Seguimiento de Entrenamiento**: La información sobre las rutinas y el progreso de los usuarios se maneja de forma externa al sistema, lo que impide un registro de progreso, continuidad o siquiera un seguimiento al usuario[cite: 32].

---

### **5. Conclusiones y Próximos Pasos**

El informe demuestra que los procesos actuales del CAF, si bien funcionales, dependen en gran medida de acciones manuales que son propensas a errores. Las inconsistencias en el registro de salida y la falta de un sistema para el seguimiento del entrenamiento limitan la capacidad de la administración para obtener datos completos y precisos.

Como próximos pasos, se recomienda explorar soluciones tecnológicas que automaticen la transferencia de datos, eliminen la dependencia de procesos manuales, y permitan un registro de entrada y salida más consistente. Además, se debe investigar un sistema que permita a los entrenadores registrar y hacer seguimiento del progreso de los usuarios de manera digital.