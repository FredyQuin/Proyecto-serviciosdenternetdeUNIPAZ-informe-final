# Modelos de Datos

Descripción de las entidades y sus relaciones.

- Entidad 1: Atributos
- Entidad 2: Atributos

Entidades:

DOCENTES: Almacena la información de los profesores

id (PK): Identificador único
nombre: Nombre del docente
correo (UK): Email único para inicio de sesión
contrasena: Contraseña encriptada


EVALUACIONES: Registra las evaluaciones realizadas

id (PK): Identificador único de la evaluación
docente_id (FK): Referencia al docente evaluado
puntaje: Calificación del 1 al 5
comentario: Opinión del estudiante
fecha: Timestamp de la evaluación



Relación:

Un docente puede recibir muchas evaluaciones (relación 1:N)
Cada evaluación pertenece a un solo docente
