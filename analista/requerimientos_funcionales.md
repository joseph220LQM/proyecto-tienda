# Documento de Requerimientos Funcionales
## Sistema de Gestión de Ventas — Artículos Masculinos y Femeninos

**Proyecto:** Tienda de Artículos  
**Área:** Creatividad y Desarrollo  
**Rol:** Analista  
**Fecha:** Octubre 2026  

---

## 1. Introducción

Este documento describe los requerimientos funcionales del sistema de escritorio para la gestión de clientes, productos y ventas de una tienda de artículos masculinos y femeninos. El sistema busca reemplazar los procesos manuales actuales con una solución integrada que facilite el control del inventario y el seguimiento de las operaciones comerciales.

---

## 2. Actores del sistema

| Actor | Descripción |
|---|---|
| **Vendedor** | Actor principal. Gestiona clientes, registra ventas y consulta productos. |
| **Administrador** | Actor secundario. Consulta reportes, revisa ventas y verifica información registrada. |

---

## 3. Requerimientos Funcionales

### Módulo de Clientes

| Código | Requerimiento | Descripción detallada |
|---|---|---|
| RF01 | Registrar cliente | El sistema debe permitir registrar un nuevo cliente con los campos: número de identificación, nombre completo, teléfono, correo electrónico y dirección. No se deben permitir identificaciones duplicadas. |
| RF02 | Consultar clientes | El sistema debe mostrar la lista de clientes registrados en una tabla. Debe permitir buscar un cliente por nombre o número de identificación. |
| RF03 | Modificar cliente | El sistema debe permitir seleccionar un cliente y actualizar cualquiera de sus datos registrados. |
| RF04 | Eliminar cliente | El sistema debe permitir eliminar un cliente del sistema, aplicando validaciones para evitar eliminar clientes con ventas asociadas. |

### Módulo de Productos

| Código | Requerimiento | Descripción detallada |
|---|---|---|
| RF05 | Registrar producto | El sistema debe permitir registrar un producto con: código único, nombre, descripción, precio, categoría, género (masculino/femenino), talla y cantidad disponible en inventario. |
| RF06 | Consultar productos | El sistema debe mostrar todos los productos registrados en una tabla. Debe permitir filtrar por nombre, categoría o género. |
| RF07 | Modificar producto | El sistema debe permitir seleccionar un producto y actualizar sus datos. Se deben validar los campos antes de guardar. |
| RF08 | Eliminar producto | El sistema debe permitir eliminar un producto, validando que no esté asociado a ventas registradas. |

### Módulo de Ventas

| Código | Requerimiento | Descripción detallada |
|---|---|---|
| RF09 | Registrar venta | El sistema debe permitir crear una nueva venta seleccionando un cliente existente y uno o varios productos con su respectiva cantidad. El total se calcula automáticamente. |
| RF10 | Consultar ventas | El sistema debe mostrar el historial de ventas con información de fecha, cliente y total. |
| RF11 | Actualizar inventario | Al registrar una venta exitosa, el sistema debe descontar automáticamente la cantidad vendida del inventario de cada producto. |
| RF12 | Consultar detalle de venta | El sistema debe permitir ver el detalle completo de una venta: cliente, productos, cantidades, precios unitarios y total. |

---

## 4. Reglas del negocio asociadas

| Código | Regla |
|---|---|
| RN01 | Un cliente no puede tener dos registros con la misma identificación. |
| RN02 | Un producto debe tener un código único en el sistema. |
| RN03 | Todo producto debe estar clasificado como masculino o femenino. |
| RN04 | El precio de cualquier producto debe ser mayor que cero. |
| RN05 | La cantidad disponible de un producto no puede ser negativa. |
| RN06 | Toda venta debe estar asociada obligatoriamente a un cliente registrado. |
| RN07 | Una venta debe contener como mínimo un producto. |
| RN08 | La cantidad de cada producto vendido debe ser mayor que cero. |
| RN09 | No se puede registrar una venta si la cantidad solicitada supera el inventario disponible. |
| RN10 | El total de la venta se calcula automáticamente: suma de (precio × cantidad) por cada producto. |
| RN11 | Una venta válida queda registrada de forma definitiva en el sistema. |
| RN12 | El inventario se actualiza automáticamente al completarse una venta. |
