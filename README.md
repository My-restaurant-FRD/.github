# “My Restaurant”

## Integrantes

- Angerossa Nicolás  
- Gomien Tomás  
- Natuche Lucas  
- Valdés Felipe  

---

## Objetivo

Desarrollar un sistema de información integral para restaurantes que permita digitalizar y automatizar el circuito operativo desde la toma de pedidos hasta el cobro final. El sistema buscará mejorar la experiencia tanto del personal como de los clientes, reduciendo errores y tiempos de espera.

### Objetivos específicos

- Optimizar la gestión de mesas  
- Gestionar pedidos online  
- Agilizar la toma de comandas desde una aplicación  
- Dirigir los pedidos automáticamente a los sectores correspondientes de la cocina por medio de comandas y facilitar la comunicación entre cocineros y mozos a través de notificaciones internas  
- Integrar una solución de cobro mediante API externa que permita cerrar el proceso de atención y liberar la mesa de forma eficiente  

---

## Funcionamiento del sistema

- Todos los meseros tendrán su cuenta en la aplicación para generar comandas  
- Se selecciona una de las mesas disponibles cuando se sientan los clientes  
- Se toma la comanda a través de la app (platos, bebidas y postres ya están cargados en la base de datos, con disponibilidad, condimentos y aclaraciones)  
- La comanda será dirigida automáticamente al sector de cocina correspondiente (comanderas/tablets)  
  - Las bebidas son notificadas al mesero  
- El chef marca los platos listos en la app, notificando al mesero  
- Cuando todos los platos están listos, se notifica al mesero para servir  
- Al pedir la cuenta, se cobra mediante API externa y se libera la mesa  

---

## Requerimientos del sistema

### Requerimientos funcionales

- Permitir al mesero realizar comandas en tiempo real con aclaraciones  
- Enviar comandas a los sectores correspondientes de cocina  
- Gestionar delivery mediante comandas telefónicas  
- Integrar con plataformas de pedidos online (ej. PedidosYa)  
- Permitir agregar/modificar/eliminar productos, mesas y elementos en tiempo real  
- Diferenciar métodos de pago: efectivo, tarjetas, apps  

### Requerimientos no funcionales

- **Performance:** Tiempo de respuesta < 5 segundos  
- **Disponibilidad:** Operativo durante todo el servicio, recuperación < 2 minutos. Hosteado en Microsoft Azure  
- **Seguridad:** Autenticación por rol y almacenamiento seguro de datos  
- **Escalabilidad:** Soportar aumento de mesas, mozos, comanderas  
- **Usabilidad:** Interfaz intuitiva y rápida de usar  

---

## Casos de uso

- CU01: Consultar comandas  
- CU02: Registrar comanda de mesa  
- CU03: Editar comanda  
- CU04: Cobrar comanda  
- CU05: Cancelar comanda  
- CU06: Consultar menú  
- CU07: Editar producto  
- CU08: Registrar producto  
- CU09: Consultar mesas  
- CU10: Editar mesa  
- CU11: Registrar mesa  
- CU12: Consultar sectores  
- CU13: Editar sector  
- CU14: Registrar sector  

---

![Diagrama de Casos de Uso](Diagrama%20de%20casos%20de%20uso.drawio.png)

---

## Definición de casos de uso

### CU01 - Consultar comandas

**Actores:** Chef, Cajero, Mesero  
**Referencias:** CU02, CU04  
**Descripción:** Consultar comandas registradas, mostrar detalles, editar  

---

### CU02 - Registrar comanda de mesa

**Actores:** Chef, Cajero, Mesero  
**Referencias:** CU10  
**Descripción:** Registrar nueva comanda (productos, cantidad, comentarios)  

---

### CU03 - Editar comanda

**Actores:** Chef, Cajero, Mesero  
**Descripción:** Editar productos, cantidades, comentarios, estado  

---

### CU04 - Cobrar comanda

**Actores:** Cajero  
**Descripción:** Registrar el total y método de pago. Cambiar estado a “Cerrado”  

---

### CU05 - Cancelar comanda

**Actores:** Cajero, Mesero  
**Descripción:** Cancelar una comanda. El estado pasa a “Cancelado”  

---

### CU06 - Consultar Menú

**Actores:** Chef, Cajero, Mesero  
**Referencias:** CU09, CU08  
**Descripción:** Ver productos del menú, editar si corresponde  

---

### CU07 - Editar producto

**Actores:** Administrador  
**Descripción:** Editar nombre, comandera, disponibilidad, precio unitario  

---

### CU08 - Registrar producto

**Actores:** Administrador  
**Descripción:** Agregar producto nuevo (nombre, precio, comandera, disponibilidad)  

---

### CU09 - Consultar mesas

**Actores:** Administrador  
**Referencias:** CU11, CU12  
**Descripción:** Ver mesas registradas y editar si corresponde  

---

### CU10 - Editar mesas

**Actores:** Administrador  
**Descripción:** Editar número de mesa y sector  

---

### CU11 - Registrar mesa

**Actores:** Administrador  
**Descripción:** Agregar una nueva mesa (número, sector)  

---

### CU12 - Consultar sectores

**Actores:** Administrador  
**Referencias:** CU14, CU15  
**Descripción:** Ver sectores registrados y editar si corresponde  

---

### CU13 - Editar sector

**Actores:** Administrador  
**Descripción:** Editar nombre del sector y comandera asociada  

---

### CU14 - Registrar sector

**Actores:** Administrador  
**Descripción:** Registrar un nuevo sector con su nombre  

---
