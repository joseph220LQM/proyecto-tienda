# Documento de Requerimientos No Funcionales
## Sistema de Gestión de Ventas — Artículos Masculinos y Femeninos

**Proyecto:** Tienda de Artículos  
**Área:** Creatividad y Desarrollo  
**Rol:** Analista  
**Fecha:** Octubre 2026  

---

## 1. Introducción

Los requerimientos no funcionales definen las condiciones de calidad, restricciones técnicas y comportamientos esperados del sistema que no están directamente relacionados con las funciones del negocio, pero que son indispensables para garantizar su correcto funcionamiento y mantenibilidad.

---

## 2. Requerimientos No Funcionales

### 2.1 Plataforma y tecnología

| Código | Requerimiento | Descripción |
|---|---|---|
| RNF01 | Tipo de aplicación | La aplicación será de escritorio, diseñada para ejecutarse en sistemas operativos Windows. |
| RNF02 | Interfaz gráfica | La interfaz de usuario se desarrollará utilizando Java Swing. |
| RNF03 | Base de datos | El sistema utilizará MySQL como motor de base de datos. |
| RNF04 | Conexión a base de datos | La comunicación entre la aplicación y la base de datos se realizará mediante JDBC, usando el conector MySQL versión 9.6 o 9.7. |

### 2.2 Validaciones y comportamiento

| Código | Requerimiento | Descripción |
|---|---|---|
| RNF05 | Validación de campos obligatorios | Todos los formularios del sistema deben validar que los campos requeridos estén diligenciados antes de procesar cualquier operación. |
| RNF06 | Validación de valores numéricos | Los campos de precio y cantidad deben aceptar únicamente valores mayores que cero. |
| RNF07 | Control de inventario en ventas | El sistema no debe permitir registrar una venta si la cantidad solicitada de un producto supera las unidades disponibles en inventario. |
| RNF08 | Mensajes al usuario | El sistema debe mostrar mensajes claros y comprensibles ante operaciones exitosas, errores de validación o fallos de conexión. |

### 2.3 Mantenibilidad

| Código | Requerimiento | Descripción |
|---|---|---|
| RNF09 | Organización del código | El código fuente debe estar estructurado por responsabilidades (clases separadas para conexión, lógica de negocio e interfaz), facilitando su mantenimiento y escalabilidad. |

---

## 3. Restricciones del proyecto

- El sistema no requiere módulo de autenticación de usuarios en esta versión.
- El desarrollo se realizará en un entorno local; no se contempla despliegue en red en esta fase.
- El conector JDBC debe ser la versión 9.6 o 9.7, según especificación del proyecto.
