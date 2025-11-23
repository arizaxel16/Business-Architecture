# Resumen Ejecutivo: Transformación Digital del CAF

**Proyecto:** Sistema de Gestión y Acceso Inteligente CAF
**Equipo:** Domus (Axel Ariza, Andrés Felipe Camargo, Juan Pablo Corral)
**Fecha:** 22 de Noviembre de 2025

## 1. Contexto y Desafío
El Centro de Acondicionamiento Físico (CAF) de la Universidad de La Sabana se enfrentaba a limitaciones operativas que eran críticas debido a procesos que se hacian manualmente. La dependencia que tenian a las hojas de cálculo (Excel) para el registro de usuarios y la gestión física de llaves generaba filas, inconsistencia en los datos y riesgos de seguridad, impidiendo asi una toma de decisiones basada en datos reales.

## 2. Solución Propuesta (Arquitectura TO-BE)
Se diseñó e implementó una arquitectura empresarial orientada a servicios, repaldada por el ecosistema **Microsoft 365** existente de la Universidad. La solución consta de:
* **Experiencia de Usuario:** Una *Progressive Web App (PWA)* integrada en Microsoft Teams para el agendamiento, check-in digital, seguimiento de rutinas y demás cosas.
* **Automatización:** Flujos de trabajo en **Power Automate** que eliminan procesos manuales en el registro y asignación de lockers.
* **Datos Unificados:** Centralización de la información en **Dataverse for Teams**, garantizando asi una "única fuente de verdad" segura y auditable.

## 3. Beneficios Clave
* **Eficiencia Operativa:** Reducción estimada del 90% en el tiempo de registro de ingreso (de 2 min a <10 seg).
* **Cero Costo de Licenciamiento:** La arquitectura utiliza licencias institucionales existentes, maximizando el ROI.
* **Seguridad y Gobierno:** Autenticación mediante **Azure Active Directory**, eliminando accesos no autorizados y protegiendo los datos personales.
* **Escalabilidad:** Infraestructura en la nube elástica, capaz de soportar picos de demanda sin inversión en hardware.

## 4. Conclusión
La arquitectura propuesta transforma al CAF en un entorno "Smart Wellness", alineando asi la tecnología con la estrategia institucional de digitalización y mejorando radicalmente la experiencia de la comunidad universitaria.

