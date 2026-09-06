# Digitalización del Proceso de Inscripción de Modalidades de Grado

## Descripción

Sistema web para la **Institución Universitaria del Putumayo** orientado a digitalizar y centralizar el proceso de inscripción y gestión de modalidades de grado.

La plataforma permitirá a los estudiantes realizar solicitudes, cargar documentos y consultar el estado de su proceso, mientras que los funcionarios podrán revisar, validar, aprobar y realizar seguimiento a las solicitudes desde un único sistema.

## Objetivo

Optimizar el proceso de modalidades de grado mediante una plataforma digital que reduzca trámites manuales, desplazamientos, uso de documentos físicos y facilite la trazabilidad de cada solicitud.

## Stack tecnológico

| Tecnología       | Uso                          |
| ---------------- | ---------------------------- |
| **Next.js**      | Frontend y aplicación web    |
| **NestJS**       | Backend y API REST           |
| **JavaScript**   | Lenguaje de desarrollo       |
| **MySQL**        | Base de datos                |
| **Bootstrap**    | Interfaz y diseño responsive |
| **Vercel**       | Despliegue del frontend      |
| **Git / GitHub** | Control de versiones         |

## Módulos principales

* **Autenticación y usuarios**
* **Gestión de estudiantes**
* **Modalidades de grado**
* **Solicitudes**
* **Requisitos**
* **Gestión de documentos**
* **Revisión y aprobación**
* **Estados y seguimiento**
* **Notificaciones**
* **Reportes y auditoría**

## Arquitectura

```text
Next.js + Bootstrap
        │
        │ API REST
        ▼
      NestJS
        │
        ▼
      MySQL
```

## Roles

* **Estudiante:** crea y consulta solicitudes.
* **Director/Asesor:** revisa y realiza observaciones.
* **Coordinador:** valida y aprueba solicitudes.
* **Administrador:** administra usuarios, modalidades, requisitos y configuración.

## Resultado esperado

Una plataforma institucional centralizada que permita gestionar el proceso de modalidades de grado **desde la inscripción hasta su aprobación y cierre**, proporcionando mayor organización, trazabilidad y eficiencia.
