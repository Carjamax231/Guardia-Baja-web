# 🥊 Guardia Baja - Sitio Web Oficial (En Producción)

Este repositorio contiene el código fuente y los recursos (assets) del sitio web promocional de **"Guardia Baja"**, un cortometraje venezolano actualmente en fase de producción (2026).

El proyecto utiliza una **arquitectura híbrida**: GitHub funciona como el "Archivo Maestro" y servidor de recursos (Fuentes, Imágenes y Video), mientras que la plataforma final de visualización es un despliegue optimizado para **WordPress/Elementor**.

---

## 🎬 Sobre el Proyecto

**"Guardia Baja"** explora la vulnerabilidad y la resiliencia en el mundo del boxeo, centrándose en el conflicto interno de Jesús frente a las expectativas de su padre.

- **Director:** Luis Pérez
- **Ubicación:** Barquisimeto - Caracas, Venezuela.
- **Estado:** En producción.

---

## 🛠️ Especificaciones Técnicas

El sitio ha sido desarrollado bajo los siguientes pilares técnicos:

* **HTML5/CSS3 Puro:** Sin frameworks pesados para garantizar la máxima velocidad de carga.
* **Diseño Responsivo:** Optimizado para dispositivos móviles mediante *Media Queries*.
* **Tipografía Personalizada:** Integración de la fuente *Zumme Rough* vía `@font-face`.
* **Assets Remotos:** El video `trailer.mp4` y las fotografías del equipo se sirven directamente desde GitHub Pages para optimizar el almacenamiento del servidor WordPress.
* **Interactividad:** Efectos de *hover* dinámicos y animaciones de pulso para los llamados a la acción (CTA).

---

## 🏗️ Estructura del Repositorio

* `index.html`: Código fuente base para desarrollo y pruebas.
* `zumme-rough-bold.otf`: Fuente tipográfica oficial del proyecto.
* `trailer.mp4`: Video de fondo para la sección Hero.
* `/*.jpg`: Fotografías optimizadas de los integrantes del equipo.
* `favicon.png`: Icono de pestaña del sitio.

---

## 🚀 Despliegue en WordPress (Caballo de Troya)

Para actualizar el sitio en el dominio oficial:

1. Realizar los cambios necesarios en el archivo `index.html` de este repositorio.
2. Hacer `Push` a la rama `main`.
3. Copiar el código de `index.html`.
4. En **WordPress (Elementor)**, ubicar el widget de **HTML** y sustituir el contenido anterior por el nuevo código.
5. Asegurarse de que el ajuste de página en Elementor sea **"Elementor Canvas"**.

---

## 📩 Contacto y Redes

Si deseas sumarte como aliado o participar en el casting:

* **Instagram:** [@guardiabajacorto](https://www.instagram.com/guardiabajacorto/)
* **Email:** guardiabajacorto@gmail.com
* **Formulario de Casting:** [Postularse aquí](https://docs.google.com/forms/d/1IQJresLvQr94sdr5CinwGDoQYpIKeUrSz7weCBY7Qxg/viewform)

---
*Desarrollado con pasión por el cine y el código. 2026.*