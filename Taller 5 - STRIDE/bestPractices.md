# Buenas Prácticas de Seguridad para el Sector

Para un Centro de Acondicionamiento Físico en un entorno universitario, las buenas prácticas de seguridad deben combinar la **protección de datos personales**, el **control de acceso físico** y la **integración con el ecosistema tecnológico de la institución**.

---

## 1. Gestión de Identidad y Acceso (IAM)

- **Single Sign-On (SSO) Institucional:**  
  Integrar el sistema del CAF con el directorio activo de la universidad (probablemente **Azure AD**, dado el uso de M365). Esto asegura que solo estudiantes, personal y administrativos activos puedan acceder. Al iniciar sesión con sus credenciales universitarias, se elimina casi por completo el riesgo de **Spoofing**.

- **Control de Acceso Físico y Lógico Unificado:**  
  El **carné universitario** debe ser el único *token* de acceso.  
  - Uso para autenticación en la aplicación.  
  - Uso en el acceso físico a través de torniquetes.  
  - Uso en la asignación de lockers electrónicos.  
  Esto crea una experiencia **segura y sin fricciones**.

---

## 2. Protección de Datos (Data Security)

- **Principio de Mínimo Privilegio (RBAC):**  
  Implementar un sistema de **Roles y Permisos**:  
  - Personal de recepción → solo registrar visitas.  
  - Entrenadores → gestionar planes de entrenamiento.  
  - Administradores → ver reportes.  
  Nadie debería tener acceso directo a la base de datos, mitigando la **Elevación de Privilegios**.

- **Centralización en una Base de Datos Segura:**  
  Reemplazar todas las hojas de Excel por una **base de datos relacional**.  
  Estas permiten **control de acceso, integridad de datos y auditoría**, algo imposible de lograr con Excel.

- **Cifrado de Datos:**  
  Toda la información personal y de entrenamiento debe estar cifrada:  
  - **En tránsito:** usando **HTTPS** para la comunicación con la app.  
  - **En reposo:** con **cifrado a nivel de base de datos**.  
  Esto protege contra la **Revelación de Información**.

---

## 3. Trazabilidad y Auditoría

- **Logs Inmutables:**  
  El sistema debe registrar cada acción crítica (inicio de sesión, registro de visita, modificación de un plan de entrenamiento) en un **log de auditoría inmutable**.  
  Esta es la principal defensa contra las amenazas de **Repudiation**.

- **Monitoreo de Acceso:**  
  Implementar **alertas automáticas** para detectar actividades sospechosas:  
  - Intentos fallidos de inicio de sesión.  
  - Intentos de acceso a datos no autorizados.  

---
