# Plan de Aseguramiento de Calidad (QA Test Cases)

A continuación se detallan los casos de prueba diseñados para validar el correcto funcionamiento de todas las características de la aplicación "Grenboxd" en sus **dos versiones paralelas** (Sin IA vs Con IA).

**Entornos de Ejecución Manual:**
- **Versión Sin IA (Legacy/Base):** `http://127.0.0.1:8000/`
- **Versión Con IA (Generada Automáticamente):** `http://127.0.0.1:8001/`

*Ambos entornos fueron probados de forma manual y simultánea superando todos los tests descritos.*
## 1. Autenticación y Registro
| ID | Caso de Prueba | Precondición | Pasos | Resultado Esperado | Estado |
|---|---|---|---|---|---|
| AUTH-01 | Registro exitoso | Ninguna | 1. Ir a `/registro/`. 2. Llenar form válido. 3. Enviar. | Usuario creado y redirigido a Inicio con sesión iniciada. | `[x]` |
| AUTH-02 | Ingreso exitoso | Usuario existente | 1. Ir a `/ingreso/`. 2. Llenar credenciales. 3. Enviar. | Sesión iniciada y redirigido a Inicio. | `[x]` |
| AUTH-03 | Ingreso fallido | Usuario existente | 1. Ir a `/ingreso/`. 2. Llenar password erróneo. 3. Enviar. | Error de validación en pantalla (no ingresa). | `[x]` |
| AUTH-04 | Cierre de sesión | Usuario logueado | 1. Hacer clic en "Salir" o ir a `/salir/`. | Sesión terminada y redirigido a Inicio. | `[x]` |

## 2. Gestión de Usuarios (CRUD)
| ID | Caso de Prueba | Precondición | Pasos | Resultado Esperado | Estado |
|---|---|---|---|---|---|
| CRUD-01 | Protección de ruta (No Login) | Usuario SIN sesión | 1. Intentar acceder a `/usuarios/`. | Redirección forzada a `/ingreso/` protegiendo la ruta. | `[x]` |
| CRUD-02 | Acceso permitido (Con Login)| Usuario logueado | 1. Ir a `/usuarios/`. | Muestra tabla con lista de todos los usuarios registrados. | `[x]` |
| CRUD-03 | Editar Usuario | Usuario logueado | 1. Clic en Editar. 2. Cambiar email. 3. Guardar. | Email actualizado exitosamente y reflejado en la lista. | `[x]` |
| CRUD-04 | Eliminar Usuario | Usuario logueado | 1. Clic en Eliminar en un usuario. 2. Confirmar. | Usuario borrado permanentemente de la base de datos. | `[x]` |

## 3. Catálogo y API Externa
| ID | Caso de Prueba | Precondición | Pasos | Resultado Esperado | Estado |
|---|---|---|---|---|---|
| API-01 | Carga dinámica de Productos | Conexión a internet | 1. Ir a la página de Inicio `/`. | La API carga los datos, que se transforman a nombres e imágenes de verdulería con precios en ARS. | `[x]` |

## 4. Carrito de Compras (Session)
| ID | Caso de Prueba | Precondición | Pasos | Resultado Esperado | Estado |
|---|---|---|---|---|---|
| CART-01 | Agregar producto al carrito | Ninguna | 1. En Inicio, clic en "Agregar" en cualquier producto. | Redirige a `/carrito/` y el producto aparece listado. | `[x]` |
| CART-02 | Sumar cantidades acumulativas | Producto ya en carrito | 1. Volver al inicio y agregar exactamente el mismo producto. | La cantidad del producto aumenta +1, no se duplica la fila. | `[x]` |
| CART-03 | Cálculo matemático del Total | 2+ Productos en carrito | 1. Ir a `/carrito/`. | El precio "Total" inferior es la suma exacta de los subtotales. | `[x]` |
| CART-04 | Limpiar sesión del carrito | Productos en carrito | 1. Clic en "Limpiar Carrito". | El carrito queda completamente vacío. | `[x]` |

## 5. Formulario de Consultas
| ID | Caso de Prueba | Precondición | Pasos | Resultado Esperado | Estado |
|---|---|---|---|---|---|
| FORM-01 | Enviar consulta válida | Ninguna | 1. Ir a `/consulta/`. 2. Llenar los campos requeridos. 3. Enviar. | Los datos se guardan y se muestra la pantalla `consulta_exitosa.html`. | `[x]` |
