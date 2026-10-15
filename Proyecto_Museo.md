# Museo Bellas Artes

## Miembros del grupo L7-DF-5

1. Naranjo Martin, Rafa
1. Sanchez Zamora, Kevin Steeven
1. Ropero Vega, Carlos Tomas
1. Roca San José, Guillermo Santiago

## 1. Introducción al problema.
Nuestro museo de arte necesita gestionar colecciones complejas que requieren una sincronización entre las obras, las galerías en donde se exponen y las guardadas en el almacén. 
Además, nuestra institución interactúa con diversos factores, desde los visitantes que desean explorar el arte o adquirirlo, hasta el personal encargado de la administración y la conservación de las distintas obras de arte (curaduría). 

La situación actual de la aplicación nos impide obtener una trazabilidad segura y exacta de las obras de arte (galerías/almacén), así como errores en la clasificación por tipo y género dentro de las galerías y los procesos de adquisición de piezas mediante compra directa o  subasta.

Debemos desarrollar una aplicación software centralizada que automatice el control de inventario de obras de arte, valide la asignación a galerías y medidas curatoriales, gestione usuario diferenciados (clientes, empleados, administrador) y proporcione un comercio en tiempo real. 

## 2. Glosario de términos
Obra de Arte: Es una pieza artística individual que forma parte del catálogo del museo.

Galería: Sala física de exposición dentro del museo donde se exhiben las obras al público bajo un tipo y género específicos.

Almacén: Lugar donde se guardan y conservan las obras que no están expuestas en ninguna galería.

Subasta: Evento de venta pública donde se vende la obra a la persona que más dinero esté dispuesto a pagar.

Puja: Acto de ofrecer una cantidad de dinero por una obra en subasta para intentar superar el precio actual establecido por una puja anterior.

## 3. Visión general del sistema
El objetivo de este proyecto es solucionar el problema mencionado previamente mediante el desarrollo de una aplicación que cubra toda la información del museo, tanto la de las obras (Su ubicación, galería, estado...) como los trabajadores y los clientes, para estos últimos tenemos que cubrir también las compras de las piezas que quieran hacer o si quieren donar u ofrecer alguna pieza.

### 3.1. Requisitos generales

### 3.2. Usuarios del sistema

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

RF-01: el sistema debe permitir listar todas las obras de are registradas en el inventario general del museo.

RF-02: el sistema deber permitir consultar el detalle completo de una obra e arte específica(autor, tipo, género, valor y estado de ubicación).

RF-03: el sistema deber permitir listar todas la galerías del museo junto con las obras de are expuestas en cada una de ellas. 

RF-04:  el sistema deber permitir consultar el listado de obras de arte que se encuentran actualmente almacenadas en el almacén. 

RF-05: el sistema deber permitir listar el historial de compras realizadas por un cliente específico.

RF-06: el sistemas deber permitir consultar las subastas activas, finalizadas y el listado de pujas asociadas a cada una. 

RF-07: el sistema deber permitir listar los empleados registrados y sus área de asignación dentro del museo. 

#### 4.1.1. Requisitos de información

Usuario: nombre, correo electrónico, contraseña.
Galería: nombre, tipo, género, capacidad.
Obra de arte: título, autor, tipo, género, precio, estado.
Compra: fecha, precio, estado 
Subasta: fecha de inicio, fecha de fin, precio inicial, estado 

#### 4.1.2. Reglas de negocio

RN-01 (Ubicación obligatoria): toda obra de arte debe estar asignada a una galería específica o, en su defecto, encontrarse registrada obligatoriamente en el almacén del museo.

RN-02 (Coherencia curatorial): una galería solo puede exponer obras de arte que coincidan exactamente con el tipo y género definidos para dicha galería.

RN-03 (Exclusividad de ubicación): una obra de arte no puede estar expuesta en una galería y en el almacén de forma simultánea. 

RN-04 (Restricción de transacciones): únicamente los usuarios registrados con el rol de cliente tienen permitido realizar compras directas o emitir pujas en las subastas. 

RN-05 (Bloqueo por subasta/venta): una obra que se encuentre participando una subasta o que haya sido comprada no puede ser modificada en su ubicación ni reasignada a galerías hasta concluir con el proceso. 

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



