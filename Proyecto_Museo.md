# Museo Bellas Artes

## Miembros del grupo L7-DF-5

1. Naranjo Martín, Rafael
2. Sánchez Zamora, Kevin Steeven
3. Ropero Vega, Carlos Tomás
4. Roca San José, Guillermo Santiago

## 1. Introducción al problema.
Nuestro museo de arte necesita gestionar colecciones complejas que requieren una sincronización entre las obras, las galerías en donde se exponen y las guardadas en el almacén. 
Además, nuestra institución interactúa con diversos factores, desde los visitantes que desean explorar el arte o adquirirlo, hasta el personal encargado de la administración y la conservación de las distintas obras de arte (curaduría). 

La situación actual de la aplicación nos impide obtener una trazabilidad segura y exacta de las obras de arte (galerías/almacén), así como errores en la clasificación por tipo y género dentro de las galerías y los procesos de adquisición de piezas mediante compra directa o  subasta.

Debemos desarrollar una aplicación software centralizada que automatice el control de inventario de obras de arte, valide la asignación a galerías y medidas curatoriales, gestione usuario diferenciados (clientes, empleados, administrador) y proporcione un comercio en tiempo real. 

## 2. Glosario de términos

## 3. Visión general del sistema
El objetivo de este proyecto es solucionar el problema mencionado previamente mediante el desarrollo de una aplicación que cubra toda la información del museo, tanto la de las obras (su ubicación, galería, estado...) como los trabajadores y los clientes, para estos últimos debe cubrir también las compras de las piezas que quieran hacer o si quieren donar u ofrecer alguna pieza.

### 3.1. Requisitos generales

Como visitante quiero poder pujar por obras de arte. 
Como empleado quiero poder gestionar almacenes.
Como empleado 

### 3.2. Usuarios del sistema
Esta aplicación apunta a tener estos usuarios:

- Clientes: Que pueda comprar una entrada, ver las obras que están a la venta, poder unirse a las subastas disponibles, en general, obtener información del sitio.
- Empleados: Podrán ver su turno y dónde hacerlo. Así los guías, el servicio de limpieza, el de mantenimiento de las piezas y la seguridad se podrán organizar correctamente.
- Administrador: Verlo todo, que pueda ver dónde están los empleados, la información de los clientes sobre el museo (si ha comprado alguna obra, si participa en subastas), toda esta información que le ayudará a gestionar el museo.

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

RF-1.1: Listado de obras de arte 
RF-1.2: Creación de obras de arte 
RF-1.3: Edición de obras de arte 
RF-1.4: Eliminación de obras de arte 

RF-2.1: Listado de galerías 
RF-2.2: Creación de galerías 
RF-2.3: Edición de galerías 
RF-2.4: Eliminación de galerías 

RF-3.1: Listado de pujas 
RF-3.2: Creación de pujas 
RF-3.3: Edición de pujas 
RF-2.4: Eliminación de pujas 

RF-4.1: Listado de usuarios 
RF-4.2: Creación de usuarios 
RF-4.3: Edición de usuarios 
RF-4.4: Eliminación de usuarios 

RF-5.1: Listado de almacenes 
RF-5.2: Creación de almacenes 
RF-5.3: Edición de almacenes 
RF-5.4: Eliminación de almacenes 

#### 4.1.1. Requisitos de información

- Como administrador del sistema, quiero gestionar la siguiente información de obras de arte:
-- Titulo
-- Fecha de creación
-- Tipo: Tipo obra de arte
- Como administrador del sistema, quiero gestionar la siguiente información de Empleado:
-- Salario
- Como administrador del sistema, quiero gestionar la siguiente información de Almacén:
-- Nombre
-- Ubicación
-- Capacidad
- Como administrador del sistema, quiero gestionar la siguiente información de Visitante:
-- Nombre
-- Fecha de nacimiento
- Como administrador del sistema, quiero gestionar la siguiente información de Galería:
-- Nombre
-- Ubicación
-- Fecha de exposicion
-- Tipo: Tipo obra de arte
- Como administrador del sistema, quiero gestionar la siguiente información de Puja:
-- Precio
-- Fecha
- Como administrador del sistema, quiero gestionar la siguiente información de Usuario:
-- Email
-- Contraseña
- Como administrador del sistema, quiero gestionar la siguiente información de Subasta:
-- Fecha de inicio
-- Fecha de fin
-- Precio mínimo

#### 4.1.2. Reglas de negocio

- RN-01: No se puede superar la capacidad que un almacén puede almacenar obras de arte
- RN-02: Una obra no puede estar en un almacén y en una galería al mismo tiempo 
- RN-03: Una galería expone obras de arte del mismo tipo 
- RN-04: El precio de la puja del visitante deber ser mayor a la mitad de la anterior puja 
- RN-05: El precio de la puja debe ser mayor al precio mínimo de la subasta. 


### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

### 4.4. Pruebas de aceptación de reglas de negocio

RN-01: ubicación obligatoria.
Acción: un curador intenta guardar una obra sin seleccionar galería ni marcar su registro en almacén.

Resultado esperado: el sistema bloquea el guardado y exige asignar una galería existente o enviarla al almacén.

RN-02: coherencia curatorial.
Acción: un curador intenta asignar un cuadro (pintura / impresionista) a una galería configurada solo para escultura / contemporáneo.

Resultado esperado: el sistema cancela la asignación por incompatibilidad de tipo y género entre la obra y la galería.

RN-03: exclusividad de ubicación.
Acción: se asigna a una galería una obra que estaba en el almacén.

Resultado esperado: el sistema actualiza la ubicación a la galería y la elimina automáticamente del inventario de almacén

RN-04: restricción de transacciones.
Acción: un usuario con rol Empleado intenta comprar una obra o pujar en una subasta.

Resultado esperado: el sistema deniega la acción, notificando que solo los usuarios con clientes pueden realizar transacciones.

RN-05: bloqueo por subasta / venta.
Acción: un empleado intenta reubicar o cambiar de galería una obra en subasta activa o previamente vendida.

Resultado esperado: el sistema bloquea la modificación hasta que finalice el proceso o se cancele la transacción.

## 5. Modelo conceptual

<img width="4080" height="3060" alt="1000052475" src="https://github.com/user-attachments/assets/53291790-f177-4c8e-9c85-21cc58f25085" />

### 5.1. Diagramas de clases UML

- con restricciones.

### 5.2. Escenarios de prueba

- con descripción textual y diagrama de objetos UML.

## 6. Matrices de trazabilidad

- Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos.

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:------|:-----------|:-----------|:-----------|:-----------|
| RI-1  | X          | X          | X          | X          |
| RI-2  |            | X          |            | X          |
| RF-1  |            | X          |            | X          |
| RF-2  | X          |            | X          | X          |
| RN-1  |            | X          |            |            |
| RN-2  | X          | X          | X          |            |
| ...   |            |            |            |            |

