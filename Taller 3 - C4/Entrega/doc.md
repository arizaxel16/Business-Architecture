# Axel Ariza
# Juan Pablo Corral
# Andrés Camargo

---

## Documentación de Componentes Clave

- **Microsoft Forms**: Es un componente esencial para el registro de usuarios, ya que es la plataforma donde los usuarios se inscriben para acceder a los servicios del **CAF**.
- **Excel de Formulario**: Una hoja de cálculo de Excel sincronizada automáticamente con el formulario de Microsoft Forms. Permite centralizar los datos de los usuarios en un solo lugar, facilitando su gestión.
- **Excel Maestro**: El registro principal del CAF. Contiene todos los registros diarios, incluyendo información clave del usuario, y la hora de entrada y salida.

---

## Actores

Los actores son los responsables de que el proceso se lleve a cabo.

- **Usuarios**: Personas que utilizan los servicios del CAF.
- **Recepcionistas**: Personal encargado de la recepción y registro.
- **Entrenadores**: Profesionales que guían y asignan rutinas.

---

## Flujos de Información

1.  **Usuario** → **Microsoft Forms**: El usuario rellena el formulario de inscripción.
2.  **Forms** → **Excel de Formulario**: La información se sincroniza automáticamente con el Excel de Formulario.
3.  **Recepcionista** → **Excel de Formulario** → **Excel Maestro**: El recepcionista copia y pega manualmente los datos desde el Excel de Formulario al Excel Maestro para realizar el registro oficial.
4.  **Entrenador** ↔ **Usuario**: La asignación de rutinas se realiza de forma manual, ya sea en papel o de memoria.
5.  **Salida del usuario**: La recepción debe registrar la hora de salida en el Excel Maestro. Sin embargo, este paso a menudo se omite si el usuario no usa un casillero y sale sin avisar.

---

## Roles y Responsabilidades

-   **Usuario CAF**: Debe completar el formulario al ingresar y devolver la llave del casillero al salir si la ha solicitado.
-   **Recepcionista**: Encargado de validar la inscripción, entregar las llaves de los casilleros, copiar los datos al Excel Maestro y registrar las entradas y salidas.
-   **Entrenador**: Se encarga de asignar las rutinas y asesorar a los usuarios.

---

## Debilidades y Riesgos Actuales

-   **Proceso manual crítico (copiar/pegar)**: Existe un alto riesgo de **errores humanos**, duplicados o datos faltantes al transferir la información del Excel de Formulario al Excel Maestro.
-   **Inconsistencia en el registro de salida**: La falta de un registro completo de las salidas, especialmente para los usuarios que no usan casilleros, impide tener un seguimiento preciso del flujo de personas.
-   **Datos de entrenamiento fuera del sistema**: No hay un registro digital del progreso, la continuidad o el seguimiento de las rutinas de los usuarios.