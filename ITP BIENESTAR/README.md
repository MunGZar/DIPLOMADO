# ITP-BienestarCare AI: Triaje Psicológico Asistido, Detección Temprana de Sobrecarga Emocional y Agendamiento Confidencial

## 1. Resumen y propósito del proyecto

Sistema web institucional para la Institución Universitaria del Putumayo (UniPutumayo), orientado a digitalizar, automatizar y centralizar el proceso de triaje psicológico preventivo asistido por Inteligencia Artificial, detección temprana de sobrecarga emocional (estrés, ansiedad, burnout) y el agendamiento confidencial de citas de atención psicológica.

El sistema permitirá registrar evaluaciones emocionales asistidas por IA, calcular niveles de riesgo mediante cuestionarios estandarizados (PHQ-9, GAD-7), agendar citas confidenciales con profesionales de salud mental, gestionar historiales pseudonimizados, realizar seguimiento y generar reportes analíticos consolidados y anonimizados para la dirección de bienestar institucional.

### Arquitectura

Se utilizará una arquitectura modular y desacoplada, separando frontend, backend y base de datos.

---

## 2. Stack tecnológico

| Tecnología | Uso |
| :--- | :--- |
| **Next.js** | Frontend y aplicación web |
| **NestJS** | Backend y API REST |
| **JavaScript / TypeScript** | Lenguaje principal de desarrollo |
| **MySQL** | Base de datos relacional |
| **Prisma ORM** | Acceso y gestión de datos |
| **Bootstrap** | Diseño de interfaz responsive |
| **Vercel** | Despliegue del frontend y serverless |
| **Git / GitHub** | Control de versiones |

---

## 3. Arquitectura y estructura de carpetas

```text
itp-bienestar/
├── frontend/
│   ├── app/
│   ├── components/
│   ├── services/
│   ├── hooks/
│   ├── utils/
│   └── public/
│
├── backend/
│   └── src/
│       ├── auth/
│       ├── users/
│       ├── students/
│       ├── triage/
│       ├── overload-detection/
│       ├── psychologists/
│       ├── appointments/
│       ├── reviews/
│       ├── approvals/
│       ├── notifications/
│       ├── audit/
│       └── reports/
│
├── database/
│   └── prisma/
│       └── schema.prisma
│
└── README.md
```

El frontend contiene la interfaz y lógica de presentación. El backend contiene la lógica de negocio, integración con modelos de IA y API REST. Prisma gestiona la comunicación con la base de datos MySQL.

---

## 4. Comandos de desarrollo y verificación

### Frontend

```bash
npm install
npm run dev
npm run build
npm run lint
```

### Backend

```bash
npm install
npm run start:dev
npm run build
npm run lint
```

### Base de datos / Prisma

```bash
npx prisma generate
npx prisma migrate dev
npx prisma studio
```

Las modificaciones de la base de datos deberán realizarse mediante migraciones versionadas. No se deberán modificar tablas directamente en producción sin generar la migración correspondiente.

---

## 5. Estándares y convenciones de Frontend

- Utilizar componentes reutilizables.
- Mantener separación entre presentación y lógica.
- Utilizar Bootstrap para estilos y diseño responsive.
- Mantener una interfaz limpia, empática, accesible e institucional.
- Validar formularios y respuestas del triaje antes de enviarlos.
- Centralizar las llamadas a la API mediante servicios.
- Evitar código duplicado.
- Utilizar nombres descriptivos para componentes, funciones y variables.
- Optimizar imágenes y recursos estáticos.

---

## 6. Estándares y convenciones de Backend y API

- Utilizar arquitectura modular de NestJS.
- Separar controllers, services y acceso a datos.
- Utilizar API REST.
- Utilizar nombres consistentes para endpoints.
- Utilizar métodos HTTP correctamente: `GET`, `POST`, `PUT`, `PATCH`, `DELETE`.
- Mantener respuestas JSON uniformes.
- No colocar lógica de negocio directamente en los controllers.
- Validar toda información recibida desde el cliente.
- Documentar endpoints cuando sea necesario.

**Ejemplo de endpoints del módulo de agendamiento y triaje:**

```text
GET    /api/triage
POST   /api/triage/eval
GET    /api/appointments
POST   /api/appointments
GET    /api/appointments/:id
PATCH  /api/appointments/:id
DELETE /api/appointments/:id
```

---

## 7. Base de datos y ORM

La base de datos utilizará MySQL y Prisma ORM.

**Reglas:**

- Definir las entidades y relaciones en `schema.prisma`.
- Utilizar migraciones versionadas.
- No modificar manualmente la estructura de producción.
- Utilizar relaciones e integridad referencial.
- Evitar duplicidad de información.
- Utilizar índices cuando sean necesarios.
- No almacenar contraseñas ni datos sensibles de salud mental en texto plano.
- Mantener las credenciales mediante variables de entorno.

---

## 8. Seguridad, autenticación y secretos

- Implementar autenticación segura basada en tokens (JWT).
- Utilizar autorización basada en roles (RBAC).
- Proteger las rutas según permisos.
- Validar y sanitizar los datos recibidos.
- Garantizar confidencialidad estricta y pseudonimización en los historiales de triaje psicológico.
- Utilizar variables de entorno para secretos y credenciales.
- Nunca almacenar contraseñas, tokens o claves directamente en el código.
- Nunca exponer credenciales del backend en el cliente.
- Validar permisos también en el backend.

**Roles principales:**

- `ESTUDIANTE`
- `PSICOLOGO`
- `COORDINADOR_BIENESTAR`
- `FUNCIONARIO`
- `ADMINISTRADOR`

---

## 9. Validaciones y manejo de errores

Las validaciones deberán realizarse tanto en frontend como en backend, siendo el backend la capa de validación definitiva.

El sistema deberá:

- Validar campos obligatorios.
- Validar formatos y tipos de datos.
- Validar archivos o documentos antes de almacenarlos.
- Manejar errores de forma uniforme.
- Mostrar mensajes claros y empáticos al usuario.
- Evitar exponer información sensible en los errores.

**Ejemplo de respuesta de error:**

```json
{
  "success": false,
  "message": "No se pudo procesar la solicitud de agendamiento",
  "statusCode": 400
}
```

---

## 10. Protocolo y restricciones del agente de desarrollo

Si el proyecto es desarrollado o asistido mediante IA, se deberán cumplir estas reglas:

- No utilizar placeholders en funcionalidades terminadas.
- No entregar código incompleto como solución final.
- No inventar datos, endpoints o requisitos institucionales.
- Verificar tipos, imports y dependencias antes de finalizar una tarea.
- Mantener la arquitectura y convenciones existentes.
- No modificar funcionalidades no relacionadas con la tarea.
- No eliminar código funcional sin justificación.
- No modificar la estructura de la base de datos sin crear una migración.
- Verificar que el proyecto compile después de cambios importantes.
- Mantener código limpio, modular y reutilizable.

**Regla principal:**

Antes de considerar una tarea terminada, verificar que el código compile, que las dependencias sean correctas y que la funcionalidad implementada sea coherente con la arquitectura del proyecto.

---

## 11. Módulos principales

- **Autenticación y usuarios:** Gestión de acceso seguro y roles.
- **Estudiantes / Comunidad ITP:** Perfil estudiantil e historial de atención.
- **Triaje psicológico asistido por IA:** Evaluación inicial con cuestionarios clínicos (PHQ-9, GAD-7) y modelos conversacionales.
- **Detección temprana de sobrecarga:** Algoritmos para identificar patrones de estrés y burnout.
- **Psicólogos y especialistas:** Gestión de disponibilidad, agenda y atención.
- **Solicitudes de agendamiento:** Reserva confidencial de citas de salud mental.
- **Documentos:** Gestión de consentimiento informado y anexos.
- **Revisiones y notas clínicas:** Registro confidencial de sesiones por parte de psicólogos.
- **Aprobaciones:** Asignación y confirmación de citas.
- **Estados y seguimiento:** Monitoreo del estado emocional y evolución del estudiante.
- **Notificaciones:** Recordatorios automáticos de citas y alertas preventivas.
- **Reportes y analítica:** Dashboard institucional con datos agregados y anonimizados.
- **Auditoría:** Registro de trazabilidad y accesos para garantía de privacidad.

---

## 12. Flujo general

```text
Estudiante / Usuario ITP
    ↓
Selecciona Triaje Psicológico
    ↓
Completa evaluación con IA (PHQ-9 / GAD-7)
    ↓
Carga documentos / Consentimiento (si aplica)
    ↓
Envía evaluación para clasificación de riesgo
    ↓
Validación y detección temprana de sobrecarga
    ↓
Solicitud y agendamiento confidencial de cita
    ↓
Asignación de psicólogo y revisión
    ↓
Atención psicológica y seguimiento
    ↓
Aprobación / Cierre de la atención
```

---

## 13. Resultado esperado

Una plataforma institucional centralizada que permita gestionar el proceso de triaje psicológico, detección temprana de sobrecarga emocional y agendamiento confidencial de citas de principio a fin en el Instituto Tecnológico del Putumayo (ITP), mejorando la atención preventiva, la confidencialidad, la organización y la eficiencia del servicio de bienestar institucional.
