# Casos de Prueba de Front-End (UI / UX)

Este documento detalla las pruebas manuales enfocadas exclusivamente en la capa visual, interactividad y experiencia de usuario (Front-End) para las dos versiones del proyecto: la versión original (Bootstrap) y la versión re-diseñada (Figma Tokens / CSS Custom).

## 1. Responsividad y Adaptabilidad (Layout)
| ID | Caso de Prueba | Pasos | Resultado Esperado | Estado |
|---|---|---|---|---|
| UI-01 | Vista Móvil (Mobile) | 1. Abrir DevTools (F12). 2. Cambiar a vista de dispositivo (ej. iPhone 12 / 390px). 3. Navegar por Inicio, Carrito y Login. | La barra de navegación colapsa (hamburguesa). Los productos se muestran en 1 columna. No hay desbordamiento horizontal (scroll). | `[ ]` |
| UI-02 | Vista Tablet | 1. Cambiar resolución a ~768px (ej. iPad). 2. Revisar la grilla de productos y carrito. | Los productos se reorganizan en 2 columnas. Los márgenes laterales son consistentes. | `[ ]` |
| UI-03 | Vista Escritorio (Desktop) | 1. Maximizar ventana (>1024px). 2. Revisar barra de navegación y tarjetas de productos. | Diseño full-width correcto. Los productos se listan en 3 o 4 columnas. | `[ ]` |

## 2. Interactividad y Estados Visuales
| ID | Caso de Prueba | Pasos | Resultado Esperado | Estado |
|---|---|---|---|---|
| UI-04 | Estados de Botones (Hover/Active) | 1. Pasar el cursor sobre el botón "Agregar al Carrito". 2. Hacer clic y mantener. | Cambio de color/sombra en hover. Efecto visual de 'presionado' al hacer clic. | `[ ]` |
| UI-05 | Enlaces de Navegación (Hover) | 1. Pasar el cursor sobre los links del Header/Navbar (Inicio, Carrito, Registro). | Subrayado sutil o cambio de color que indica interactividad. | `[ ]` |
| UI-06 | Tarjetas de Producto (Hover) | 1. Pasar el cursor sobre la tarjeta o la imagen del producto. | Elevación sutil de la tarjeta (shadow) o micro-animación en la imagen. | `[ ]` |

## 3. Validaciones de Formularios en Cliente
| ID | Caso de Prueba | Pasos | Resultado Esperado | Estado |
|---|---|---|---|---|
| UI-07 | Campos Requeridos (HTML5) | 1. Ir a `/registro/` o `/consulta/`. 2. Dejar campos vacíos. 3. Hacer clic en Enviar. | El navegador bloquea el envío y muestra un tooltip nativo de "Complete este campo". | `[ ]` |
| UI-08 | Formato de Email Inválido | 1. En formulario de ingreso, escribir `usuario_sin_arroba` en el campo Email. 2. Enviar. | Alerta visual del navegador indicando que falta el "@" o formato incorrecto. | `[ ]` |
| UI-09 | Feedback de Error/Éxito visual | 1. Introducir credenciales incorrectas en login. | El mensaje de error debe resaltar (generalmente en rojo) y tener suficiente contraste (accesibilidad). | `[ ]` |

## 4. Consistencia del Sistema de Diseño (Tokens)
*(Especialmente para la versión con IA/CSS Custom)*
| ID | Caso de Prueba | Pasos | Resultado Esperado | Estado |
|---|---|---|---|---|
| UI-10 | Tipografía y Jerarquía | 1. Revisar los H1, H2, y párrafos en la página principal. | Las fuentes cargan correctamente (ej. Google Fonts). Los tamaños respetan la escala tipográfica definida. | `[ ]` |
| UI-11 | Paleta de Colores | 1. Verificar botones primarios, fondos y textos. | Los colores corresponden exactamente a las variables CSS (Figma Tokens) sin hardcodear colores aleatorios. | `[ ]` |
| UI-12 | Espaciados (Paddings/Margins) | 1. Inspeccionar el contenedor principal y tarjetas de producto. | Espacios uniformes, alineación vertical/horizontal coherente (basado en rems o variables espaciales). | `[ ]` |

## 5. Elementos Multimedia y de Interfaz
| ID | Caso de Prueba | Pasos | Resultado Esperado | Estado |
|---|---|---|---|---|
| UI-13 | Carga de Imágenes (Imágenes Rotas) | 1. Revisar el catálogo de productos y el mockup. | Todas las imágenes cargan. Si una falla, debe tener un atributo `alt` descriptivo o una imagen por defecto (fallback). | `[ ]` |
| UI-14 | Visibilidad de Tablas | 1. Ir a la vista del `/carrito/` o la lista de `/usuarios/`. | Las tablas tienen bordes o separadores claros. No se desbordan en móviles (debe haber scroll horizontal en el contenedor si es necesario). | `[ ]` |

---
**Instrucciones de Ejecución:** Para ejecutar estos casos de forma efectiva, se utilizará una combinación de navegación manual humana y el uso de *Chrome/Edge Developer Tools* (Device Toolbar) para simular dispositivos y estados.
