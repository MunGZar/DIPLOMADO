Sistema de Gestión de Modalidades de Grado

1. Resumen y propósito del proyecto

Sistema web institucional para la Institución Universitaria del
Putumayo, orientado a digitalizar y centralizar el proceso de
inscripción y gestión de modalidades de grado.

El sistema permitirá registrar solicitudes, validar requisitos, cargar
documentos, realizar revisiones y aprobaciones, consultar estados y
mantener la trazabilidad completa del proceso.

Arquitectura

Se utilizará una arquitectura modular y desacoplada, separando
frontend, backend y base de datos.

2. Stack tecnológico

Tecnología         Uso

Next.js        Frontend y aplicación web
NestJS         Backend y API REST
JavaScript     Lenguaje principal
MySQL          Base de datos
Prisma ORM     Acceso y gestión de datos
Bootstrap      Diseño de interfaz responsive
Vercel         Despliegue del frontend
Git / GitHub   Control de versiones

3. Arquitectura y estructura de carpetas

modalidades-grado/
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
│       ├── modalities/
│       ├── applications/
│       ├── requirements/
│       ├── documents/
│       ├── reviews/
│       ├── approvals/
│       ├── notifications/
│       └── reports/
│
├── database/
│   └── prisma/
│       └── schema.prisma
│
└── README.md

El frontend contiene la interfaz y lógica de presentación. El backend
contiene la lógica de negocio y API. Prisma gestiona la comunicación con
MySQL.

4. Comandos de desarrollo y verificación

Frontend

npm install
npm run dev
npm run build
npm run lint

Backend

npm install
npm run start:dev
npm run build
npm run lint

Base de datos / Prisma

npx prisma generate
npx prisma migrate dev
npx prisma studio

Las modificaciones de la base de datos deberán realizarse mediante
migraciones versionadas. No se deberán modificar tablas directamente
en producción sin generar la migración correspondiente.

5. Estándares y convenciones de Frontend

Utilizar componentes reutilizables.

Mantener separación entre presentación y lógica.

Utilizar Bootstrap para estilos y diseño responsive.

Mantener una interfaz limpia, institucional y consistente.

Validar formularios antes de enviarlos.

Centralizar las llamadas a la API mediante servicios.

Evitar código duplicado.

Utilizar nombres descriptivos para componentes, funciones y
variables.

Optimizar imágenes y recursos estáticos.

6. Estándares y convenciones de Backend y API

Utilizar arquitectura modular de NestJS.

Separar controllers, services y acceso a datos.

Utilizar API REST.

Utilizar nombres consistentes para endpoints.

Utilizar métodos HTTP correctamente: GET, POST, PUT, PATCH,
DELETE.

Mantener respuestas JSON uniformes.

No colocar lógica de negocio directamente en los controllers.

Validar toda información recibida desde el cliente.

Documentar endpoints cuando sea necesario.

Ejemplo:

GET    /api/applications
POST   /api/applications
GET    /api/applications/:id
PATCH  /api/applications/:id
DELETE /api/applications/:id

7. Base de datos y ORM

La base de datos utilizará MySQL y Prisma ORM.

Reglas:

Definir las entidades y relaciones en schema.prisma.

Utilizar migraciones versionadas.

No modificar manualmente la estructura de producción.

Utilizar relaciones e integridad referencial.

Evitar duplicidad de información.

Utilizar índices cuando sean necesarios.

No almacenar contraseñas en texto plano.

Mantener las credenciales mediante variables de entorno.

8. Seguridad, autenticación y secretos

Implementar autenticación segura.

Utilizar autorización basada en roles.

Proteger las rutas según permisos.

Validar y sanitizar los datos recibidos.

Utilizar variables de entorno para secretos y credenciales.

Nunca almacenar contraseñas, tokens o claves directamente en el
código.

Nunca exponer credenciales del backend en el cliente.

Validar permisos también en el backend.

Roles principales:

ESTUDIANTE
DIRECTOR
COORDINADOR
FUNCIONARIO
ADMINISTRADOR

9. Validaciones y manejo de errores

Las validaciones deberán realizarse tanto en frontend como en backend,
siendo el backend la capa de validación definitiva.

El sistema deberá:

Validar campos obligatorios.

Validar formatos y tipos de datos.

Validar archivos antes de almacenarlos.

Manejar errores de forma uniforme.

Mostrar mensajes claros al usuario.

Evitar exponer información sensible en los errores.

Ejemplo de respuesta:

{
  "success": false,
  "message": "No se pudo procesar la solicitud",
  "statusCode": 400
}

10. Protocolo y restricciones del agente de desarrollo

Si el proyecto es desarrollado o asistido mediante IA, se deberán
cumplir estas reglas:

No utilizar placeholders en funcionalidades terminadas.

No entregar código incompleto como solución final.

No inventar datos, endpoints o requisitos institucionales.

Verificar tipos, imports y dependencias antes de finalizar una
tarea.

Mantener la arquitectura y convenciones existentes.

No modificar funcionalidades no relacionadas con la tarea.

No eliminar código funcional sin justificación.

No modificar la estructura de la base de datos sin crear una
migración.

Verificar que el proyecto compile después de cambios importantes.

Mantener código limpio, modular y reutilizable.

Regla principal

Antes de considerar una tarea terminada, verificar que el código
compile, que las dependencias sean correctas y que la funcionalidad
implementada sea coherente con la arquitectura del proyecto.

11. Módulos principales

Autenticación y usuarios.

Estudiantes.

Modalidades de grado.

Requisitos.

Solicitudes.

Documentos.

Revisiones.

Aprobaciones.

Estados y seguimiento.

Notificaciones.

Reportes.

Auditoría.

12. Flujo general

Estudiante
    ↓
Selecciona modalidad
    ↓
Completa solicitud
    ↓
Carga documentos
    ↓
Envía solicitud
    ↓
Validación
    ↓
Revisión
    ↓
Correcciones (si aplica)
    ↓
Aprobación
    ↓
Cierre de solicitud

13. Resultado esperado

Una plataforma institucional centralizada que permita gestionar el
proceso de modalidades de grado de principio a fin, mejorando la
organización, trazabilidad y eficiencia del trámite.