# 🧠 Contexto Técnico: Proyecto "Guardia Baja"

Este documento es la "Ley de Oro" para el desarrollo del sitio web del cortometraje. Cualquier IA trabajando en este repositorio debe seguir estas directrices.

## 🎨 Identidad Visual e Interfaz
- **Colores Innegociables:** Fondo Negro Absoluto (`#000000`) y acento Rojo Principal (`#e50914`).
- **Fuentes:** La fuente principal para títulos es `Zumme Rough`.
- **Estética:** Estilo cinematográfico, alto contraste, sin bordes visibles entre secciones (flujo orgánico).

## 🛠️ Reglas de Código (CSS/HTML)
- **Aislamiento:** Todo el CSS debe estar contenido dentro de la clase maestra `.guardia-baja-app` para evitar conflictos con WordPress.
- **Especificidad > !important:** Está prohibido el uso de `!important` a menos que sea el último recurso. Los conflictos se resuelven aumentando el rango de autoridad (especificidad) del selector.
- **Marquesina (Ticker):** Se utiliza un sistema de `ticker-track` con animación de keyframes.
- **Logos:** Los logos de aliados en el ticker usan filtros de "Fantasma Blanco" (`brightness(0) invert(1)`) y recuperan color al hacer `hover`.
- **Equilibrio Visual:** El logo de Endoret requiere un `transform: scale(1.35)` base para equilibrarse con Universitas.

## 🚀 Arquitectura de Despliegue
- El sitio es un "Caballo de Troya": HTML/CSS puro inyectado en un widget de Elementor (WordPress).
- Los recursos pesados (videos, imágenes) se sirven desde GitHub Pages.