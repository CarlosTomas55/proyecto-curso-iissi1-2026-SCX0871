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

Titulo

Fecha de creación

Tipo: Tipo obra de arte
- Como administrador del sistema, quiero gestionar la siguiente información de Empleado:
Salario
- Como administrador del sistema, quiero gestionar la siguiente información de Almacén:

Nombre

Ubicación

Capacidad

- Como administrador del sistema, quiero gestionar la siguiente información de Visitante:

Nombre

Fecha de nacimiento

- Como administrador del sistema, quiero gestionar la siguiente información de Galería:

Nombre

Ubicación

Fecha de exposicion

Tipo: Tipo obra de arte

- Como administrador del sistema, quiero gestionar la siguiente información de Puja:

Precio

Fecha

- Como administrador del sistema, quiero gestionar la siguiente información de Usuario:

Email

Contraseña

- Como administrador del sistema, quiero gestionar la siguiente información de Subasta:

Fecha de inicio

Fecha de fin

Precio mínimo

#### 4.1.2. Reglas de negocio

- RN-01: No se puede superar la capacidad que un almacén puede almacenar obras de arte
- RN-02: Una obra no puede estar en un almacén y en una galería al mismo tiempo 
- RN-03: Una galería expone obras de arte del mismo tipo 
- RN-04: El precio de la puja del visitante deber ser mayor a la mitad de la anterior puja 
- RN-05: El precio de la puja debe ser mayor al precio mínimo de la subasta. 


### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

### 4.4. Pruebas de aceptación de reglas de negocio



## 5. Modelo conceptual

### 5.1. Diagramas de clases UML

<img width="2720" height="2720" alt="modelo_conceptual_subastas_obras_arte" src="https://github.com/user-attachments/assets/c3ec88b3-4472-4a1b-b858-9e2e550ad67a" />

### 5.2. Escenarios de prueba

- con descripción textual y diagrama de objetos UML.

## 6. Matrices de trazabilidad

- Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos.

|        | Almacén    | obraDeArte | Galería   | seExponen  |  Puja       |   Subasta  |   seHacen  |
|:------ |:-----------|:-----------|:----------|:-----------|:------------|:-----------|:-----------|
| RN-01  | X          |            |           |            |             |            |            |
| RN-02  |            | X          |           |            |             |            |            |
| RN-03  |            |            | X         | X          |             |            |            |
| RN-04  |            |            |           |            | X           | X          | X          |
| RN-05  |            |            |           |            | X           | X          | X          |


