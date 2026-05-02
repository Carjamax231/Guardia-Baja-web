# REGISTRO DE ÚLTIMOS CAMBIOS Y AJUSTES TÉCNICOS (LOG)
**Proyecto:** Guardia Baja (Ecosistema Web / WooCommerce)

## 1. Arquitectura del Flujo de Compra (Direct Checkout)
*   **Estrategia:** Se evadió el flujo tradicional de E-commerce (Shop -> Cart -> Checkout) para mantener la inmersión del "Pitch".
*   **Implementación:** Los botones de "PATROCINAR" en el archivo `index.html` (Gimnasio de Aliados) utilizan enlaces dinámicos con el ID del producto. Ejemplo: `href="https://guardiabaja.com/checkout/?add-to-cart=63"`. Esto añade el plan al carrito y redirige al usuario directamente a la caja registradora.

## 2. Configuración de WooCommerce (Shortcode vs Blocks)
*   **Ajuste Crítico:** Se eliminó el bloque moderno de WooCommerce (WooCommerce Checkout Block) de la página de "Checkout" porque su estructura bloqueaba las modificaciones de CSS.
*   **Solución:** Se reemplazó por el shortcode clásico `[woocommerce_checkout]`. Esto permitió que el CSS personalizado pudiera penetrar y modificar el diseño de los formularios. *(Nota: Este mismo ajuste debe mantenerse para la página de Cart si se llegase a usar).*

## 3. Configuración Global del Tema (Astra)
Para evitar conflictos de CSS, los colores base se configuraron directamente en el Personalizador de Astra (Apariencia > Personalizar > Global > Colores):
*   **Site / Content Background (Fondo):** `#000000` (Negro)
*   **Theme Color / Links (Normal):** `#e50914` (Rojo Guardia Baja)
*   **Links (Hover):** `#b0060f` (Rojo oscuro)
*   **Heading (Títulos H1-H6):** `#ffffff` (Blanco)
*   **Body Text (Párrafos):** `#cccccc` (Gris claro)
*   **Borders (Bordes):** `#333333` (Gris oscuro)
*   **Header / Footer:** Fondo ajustado a `#000000` desde sus respectivos constructores en el Personalizador.

## 4. Inyección de CSS Específico (Modo Oscuro de Formularios)
Para las áreas rebeldes (cajas de texto y notificaciones) que el tema Astra no cubría, se inyectó el siguiente código en *CSS Adicional*:
```css
/* FORZAR CAJAS DE TEXTO OSCURAS WOOCOMMERCE */
body.woocommerce form .form-row input.input-text,
body.woocommerce input[type="text"],
body.woocommerce input[type="email"],
body.woocommerce input[type="tel"],
body.woocommerce textarea,
.woocommerce-checkout input.input-text,
.woocommerce-checkout textarea {
    background-color: #111111 !important;
    color: #ffffff !important;
    border: 1px solid #333333 !important;
    border-radius: 0px !important;
    box-shadow: none !important;
}

/* Efecto al escribir (Borde Rojo) */
body.woocommerce form .form-row input.input-text:focus,
body.woocommerce textarea:focus {
    border-color: #e50914 !important;
    outline: none !important;
}

/* APAGAR LUCES DE NOTIFICACIONES Y CUPONES */
.woocommerce-message, 
.woocommerce-info, 
.woocommerce-error, 
.woocommerce-form-coupon {
    background-color: #111111 !important;
    color: #cccccc !important;
    border-top: 3px solid #e50914 !important;
    border-left: none !important;
    border-right: none !important;
    border-bottom: none !important;
}

/* Letras del enlace rojo en notificaciones */
.woocommerce-info a,
.showcoupon {
    color: #e50914 !important;
    font-weight: bold !important;
}

## 5. Notas sobre el Entorno y Troubleshooting

*Caché Agresivo: El servidor utiliza el plugin SpeedyCache. Siempre que se hagan cambios en el CSS o en la estructura, es obligatorio purgar la caché (Clear All Cache) para visualizar los cambios en modo incógnito.

*Falsos Positivos en el Editor: Extensiones del navegador como Quillbot pueden generar superposiciones visuales (como círculos rojos de error) en la caja de edición de CSS de WordPress, los cuales no son errores reales de sintaxis.

