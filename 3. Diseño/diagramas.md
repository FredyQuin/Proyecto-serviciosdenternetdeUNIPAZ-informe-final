# Diagramas

Diagrama Entidad–Relación (ER)

Descripción

El diagrama ER representa las entidades principales del sistema y cómo se relacionan entre sí.
En este caso, el sistema de e-VALuacion tiene dos entidades principales:

Docente: representa a cada profesor que puede ser evaluado.

Evaluación: representa cada valoración que un estudiante hace sobre un docente.

Cada docente puede tener muchas evaluaciones, pero cada evaluación pertenece a un solo docente, estableciendo una relación 1 a N.

+------------------+         1        N     +--------------------+
|     Docente      |----------------------->|    Evaluación      |
+------------------+                        +--------------------+
| id (PK)          |                        | id (PK)            |
| nombre           |                        | docente_id (FK)    |
| correo (UNIQUE)  |                        | puntaje            |
| contrasena       |                        | comentario         |
|                  |                        | fecha              |
+------------------+                        +--------------------+


Relación: Un docente puede tener muchas evaluaciones.
Integridad referencial: evaluaciones.docente_id hace referencia a docentes.id.
Restricciones: puntaje solo puede tener valores entre 1 y 5.

Diagrama de Clases

Descripción

El diagrama de clases muestra la estructura lógica del código y las relaciones entre los objetos que representarían las tablas del sistema en un lenguaje de programación orientado a objetos (por ejemplo, JavaScript o Java).

Cada clase corresponde a una tabla del modelo ER y mantiene las mismas relaciones.

+----------------------+
|      Docente         |
+----------------------+
| - id: int            |
| - nombre: string     |
| - correo: string     |
| - contrasena: string |
+----------------------+
| +registrar()         |
| +iniciarSesion()     |
| +obtenerEvaluaciones()|
+----------------------+

            1
            |
            |  tiene
            |
            N
+----------------------+
|     Evaluacion       |
+----------------------+
| - id: int            |
| - puntaje: int       |
| - comentario: string |
| - fecha: datetime    |
| - docente_id: int    |
+----------------------+
| +crear()             |
| +obtenerPorDocente() |
+----------------------+


Docente

Representa a un profesor dentro del sistema.

Tiene métodos como registrar() e iniciarSesion().

Evaluacion

Representa la evaluación hecha por los estudiantes.

Se asocia al docente mediante docente_id.

Flujo típico (Ejemplo: estudiante evalúa a un docente):

Estudiante      API Backend (Express)      Controlador         Base de Datos
     |                    |                     |                     |
     |--- POST /evaluaciones ------------------>|                     |
     |                    |----- crear() -----> |                     |
     |                    |                     |--- INSERT ---------->|
     |                    |                     |<-- Confirmación ----|
     |<--- Respuesta 201: Evaluación creada ----|                     |
