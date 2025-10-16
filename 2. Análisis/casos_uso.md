# Casos de Uso

Listado de casos de uso principales.

- Caso de uso 1: Actor - Descripción

---Registrar evaluación docente---
Elemento	Descripción
Nombre:	Registrar evaluación docente
Actor principal:	Docente
Objetivo:	Permitir al docente ingresar una evaluación para cada estudiante.
Precondiciones:	El docente debe estar autenticado en el sistema.
Flujo principal:	1. El docente inicia sesión.
2. Selecciona el curso o grupo.
3. Ingresa los criterios y calificaciones.
4. Guarda la evaluación.
5. El sistema confirma el registro.
Postcondiciones:	La evaluación queda almacenada y visible en el historial del docente.
Excepciones:	- Error de conexión.
- Faltan campos obligatorios.
- Sesión expirada.

- Caso de uso 2: Actor - Descripción

---Generar reporte de desempeño---
Elemento	Descripción
Nombre:	Generar reporte de desempeño
Actor principal:	Administrador académico
Objetivo:	Obtener un informe consolidado del desempeño de los docentes según las evaluaciones registradas.
Precondiciones:	Debe existir información registrada de las evaluaciones docentes.
Flujo principal:	
1. El administrador accede al módulo de reportes.
2. Selecciona periodo y área.
3. Solicita el reporte.
4. El sistema genera el informe en formato PDF o Excel.
5. El administrador descarga o visualiza el resultado.
Postcondiciones: El reporte queda disponible para consulta o respaldo.
Excepciones:
- No existen datos registrados.
- Error al generar el archivo.
