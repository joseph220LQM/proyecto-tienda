# Historias de Usuario — Backlog del Proyecto
## Sistema de Gestión de Ventas — Artículos Masculinos y Femeninos

**Proyecto:** Tienda de Artículos  
**Área:** Creatividad y Desarrollo  
**Rol:** Analista  
**Fecha:** Octubre 2026  

---

## Formato de Issue en GitHub

Cada historia de usuario corresponde a un Issue en el repositorio del proyecto.  
Se organiza en el tablero **GitHub Projects** como columnas: `Por hacer` → `En progreso` → `Hecho`.

---

## HU01 — Registrar cliente

**Etiqueta:** `feature` `módulo-clientes`

**Historia:**  
Como vendedor, quiero registrar un nuevo cliente en el sistema para poder asociarlo a sus compras futuras.

**Descripción:**  
El formulario de registro debe incluir los campos: número de identificación, nombre completo, teléfono, correo electrónico y dirección. Al guardar, el sistema debe verificar que no exista otro cliente con la misma identificación.

**Restricciones:**
- El número de identificación es único; no se admiten duplicados.
- Todos los campos son obligatorios excepto la dirección.
- El correo debe tener formato válido.

**Criterios de aceptación:**
- [ ] El sistema muestra un formulario con todos los campos requeridos.
- [ ] No permite guardar si algún campo obligatorio está vacío.
- [ ] Muestra un mensaje de error si la identificación ya existe.
- [ ] Confirma con un mensaje cuando el cliente se registra exitosamente.

---

## HU02 — Consultar cliente

**Etiqueta:** `feature` `módulo-clientes`

**Historia:**  
Como vendedor, quiero consultar los clientes registrados para encontrar rápidamente su información y poder asociarlos a una venta.

**Descripción:**  
El sistema debe mostrar todos los clientes en una tabla con sus datos principales. Debe incluir un campo de búsqueda que filtre por nombre o número de identificación.

**Restricciones:**
- La tabla debe actualizarse al realizar una búsqueda sin recargar toda la ventana.

**Criterios de aceptación:**
- [ ] Se muestran todos los clientes en una tabla con columnas: ID, nombre, teléfono, correo y dirección.
- [ ] El campo de búsqueda filtra resultados en tiempo real o al presionar buscar.
- [ ] Si no hay resultados, muestra un mensaje indicándolo.

---

## HU03 — Registrar producto

**Etiqueta:** `feature` `módulo-productos`

**Historia:**  
Como encargado, quiero registrar nuevos productos en el sistema para mantener actualizado el catálogo de artículos disponibles.

**Descripción:**  
El formulario debe permitir ingresar: código de producto, nombre, descripción, precio, categoría, género (masculino/femenino), talla y cantidad disponible.

**Restricciones:**
- El código del producto debe ser único.
- El precio debe ser mayor que cero.
- La cantidad inicial no puede ser negativa.
- El género solo puede ser "Masculino" o "Femenino".

**Criterios de aceptación:**
- [ ] El formulario contiene todos los campos requeridos.
- [ ] No permite guardar con campos vacíos o con precio/cantidad inválidos.
- [ ] Muestra error si el código ya existe.
- [ ] Confirma el registro exitoso con un mensaje al usuario.

---

## HU04 — Consultar producto

**Etiqueta:** `feature` `módulo-productos`

**Historia:**  
Como vendedor, quiero consultar los productos disponibles para conocer su información, precio y cantidad en inventario antes de registrar una venta.

**Descripción:**  
El sistema muestra todos los productos en una tabla. Permite buscar o filtrar por nombre, categoría o género.

**Restricciones:**
- Debe mostrar claramente la cantidad disponible de cada producto.

**Criterios de aceptación:**
- [ ] La tabla muestra: código, nombre, categoría, género, talla, precio y cantidad disponible.
- [ ] Permite buscar por nombre o filtrar por género/categoría.
- [ ] Los productos con cantidad cero se muestran diferenciados visualmente (ej. en rojo o con indicador).

---

## HU05 — Registrar venta

**Etiqueta:** `feature` `módulo-ventas`

**Historia:**  
Como vendedor, quiero registrar una nueva venta para almacenar los productos adquiridos por un cliente y generar el comprobante correspondiente.

**Descripción:**  
El proceso de venta permite seleccionar un cliente registrado, agregar uno o más productos con su cantidad, y calcular el total automáticamente. Al confirmar, la venta queda registrada y el inventario se actualiza.

**Restricciones:**
- No se puede registrar una venta sin cliente seleccionado.
- Debe haber al menos un producto en la venta.
- No se puede vender más unidades de las disponibles en inventario.
- El total es de solo lectura; se calcula automáticamente.

**Criterios de aceptación:**
- [ ] Permite seleccionar un cliente desde la lista de registrados.
- [ ] Permite agregar múltiples productos con cantidad editable.
- [ ] El total se calcula y actualiza automáticamente al agregar/quitar productos.
- [ ] Muestra error si se intenta vender más unidades de las disponibles.
- [ ] Al confirmar, la venta queda registrada y el inventario se descuenta.

---

## HU06 — Actualizar inventario tras venta

**Etiqueta:** `feature` `módulo-ventas` `módulo-productos`

**Historia:**  
Como encargado, quiero que el inventario se actualice automáticamente después de cada venta para conocer en todo momento las unidades disponibles de cada producto.

**Descripción:**  
Esta historia es parte del flujo de registro de venta. Al confirmar una venta, el sistema debe restar de forma automática la cantidad vendida al stock de cada producto involucrado.

**Restricciones:**
- El descuento de inventario ocurre solo si la venta se registra correctamente.
- Si la venta falla, el inventario no debe modificarse.

**Criterios de aceptación:**
- [ ] La cantidad disponible de cada producto disminuye según lo vendido.
- [ ] El cambio se refleja inmediatamente al consultar productos.
- [ ] Si la venta no se completa, el inventario permanece sin cambios.

---

## HU07 — Consultar ventas

**Etiqueta:** `feature` `módulo-ventas`

**Historia:**  
Como vendedor, quiero consultar el historial de ventas para conocer las operaciones realizadas y hacer seguimiento a los movimientos del negocio.

**Descripción:**  
El sistema muestra una tabla con todas las ventas registradas. Cada fila muestra la fecha, el cliente y el total de la venta.

**Restricciones:**
- Las ventas deben mostrarse ordenadas por fecha, de más reciente a más antigua.

**Criterios de aceptación:**
- [ ] La tabla muestra: número de venta, fecha, nombre del cliente y total.
- [ ] Las ventas están ordenadas de más reciente a más antigua.
- [ ] Al seleccionar una venta se puede acceder a su detalle.

---

## HU08 — Modificar producto

**Etiqueta:** `feature` `módulo-productos`

**Historia:**  
Como encargado, quiero modificar la información de un producto para mantener actualizados sus datos como precio, descripción o cantidad disponible.

**Descripción:**  
Al seleccionar un producto desde la tabla de consulta, el sistema carga sus datos en un formulario editable. El encargado puede modificar los campos necesarios y guardar los cambios.

**Restricciones:**
- El código del producto no puede modificarse si ya tiene ventas asociadas.
- Se deben validar los datos antes de guardar.

**Criterios de aceptación:**
- [ ] Al seleccionar un producto, sus datos se cargan en el formulario.
- [ ] Permite editar y guardar cambios con validación de campos.
- [ ] Muestra mensaje de confirmación al guardar exitosamente.
- [ ] Muestra error si los datos ingresados no son válidos.

---

## HU09 — Consultar detalle de venta

**Etiqueta:** `feature` `módulo-ventas`

**Historia:**  
Como administrador, quiero consultar el detalle completo de una venta para verificar los productos vendidos, las cantidades, los precios y el total cobrado.

**Descripción:**  
Al seleccionar una venta del historial, el sistema muestra una vista de detalle con toda la información de esa transacción.

**Restricciones:**
- El detalle es de solo lectura; no puede modificarse una vez registrada la venta.

**Criterios de aceptación:**
- [ ] Muestra el nombre y datos del cliente asociado a la venta.
- [ ] Lista todos los productos vendidos con cantidad y precio unitario.
- [ ] Muestra el total calculado de la venta.
- [ ] Incluye la fecha y número de la venta.

---

## Organización sugerida en GitHub Projects

| Columna | Issues |
|---|---|
| **Por hacer** | HU01, HU02, HU03, HU04, HU05, HU06, HU07, HU08, HU09 |
| **En progreso** | *(se mueven según avance del equipo)* |
| **Hecho** | *(se mueven al completar y validar)* |

**Etiquetas recomendadas:**
- `feature` — nueva funcionalidad
- `módulo-clientes` — funcionalidades del módulo de clientes
- `módulo-productos` — funcionalidades del módulo de productos
- `módulo-ventas` — funcionalidades del módulo de ventas
- `bug` — errores encontrados durante desarrollo
- `validación` — tareas de validación o pruebas
