# UNIDAD-4-BASE-DE-DATOS-EJERCICIO-17
1. Entidades Principales y Personas
titular

Almacena los datos personales de los dueños o responsables de las mascotas.

Atributos: dni_titular (clave primaria), nombre, apellido, telefono y correo.

mascota

Registra la información de los animales de compañía atendidos en la clínica.

Atributos: num_historia_clinica (clave primaria), nombre, color, especie, raza, sexo y dni_titular (clave foránea que vincula a la mascota con su titular).

veterinario

Contiene los datos del cuerpo médico profesional de la clínica.

Atributos: matricula_profesional (clave primaria), nombre, apellido, especialidad y telefono.

2. Catálogo de Insumos y Control Médico
vacuna

Administra el inventario y tipo de vacunas disponibles para la aplicación.

Atributos: codigo_vacuna (clave primaria), num_lote, nombre_comercial y laboratorio.

consulta

Registra las atenciones clínicas individuales brindadas a los pacientes.

Atributos: id_consulta (clave primaria), fecha, hora, peso, diagnostico, temperatura_corporal, num_historia_clinica (clave foránea hacia la mascota) y matricula_profesional (clave foránea hacia el veterinario que atendió).

3. Tablas Intermedias e Historiales
registro_aplicacion_vacuna

Tabla asociativa que registra la aplicación histórica de vacunas a las mascotas, permitiendo el control de refuerzos.

Atributos: Clave primaria compuesta por (num_historia_clinica, codigo_vacuna, fecha_aplicacion), además del campo fecha_refuerzo.

IMAGEN DE EJEMPLO DE UNA CONSULTA:
<img width="1307" height="333" alt="image" src="https://github.com/user-attachments/assets/1e6f9bba-6cb3-42d1-8f4b-ab20b0b296b9" />


4. Restricciones e Integridad Referencial (Foreign Keys)
El script configura de manera estricta las reglas de validación para asegurar la consistencia relacional mediante claves primarias y claves foráneas que conectan consultas con mascotas y veterinarios, mascotas con sus respectivos titulares, y registros de vacunación con las historias clínicas y el catálogo de vacunas.
