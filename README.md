# 🥊 Guardia Baja - Sitio Web Oficial & Bitácora de Desarrollo
**En Produccion**
*Última actualización: 19 de Abril de 2026*

Este repositorio contiene el código fuente y la documentación del sitio web promocional de **"Guardia Baja"**, un cortometraje venezolano que explora la vulnerabilidad y la resiliencia en el mundo del boxeo. 

El proyecto utiliza una **arquitectura híbrida**: GitHub funciona como el "Archivo Maestro" y servidor de recursos estáticos, mientras que la plataforma final de visualización es un despliegue optimizado para **WordPress/Elementor**.

---

## Bitácora de Desarrollo y Cambios Lógicos

### 18 - 19 de Abril, 2026: Fase 3 - Cirugía Estética, UX/UI y Casting
* **Módulo de Casting (Lógica CSS):** Se implementó una cuadrícula (Grid) simétrica de 3-2 para las 5 fichas de los personajes. Para vencer la deformación nativa de Flexbox, se aplicó `box-sizing: border-box` y `flex: 0 0 300px`, obligando al navegador a respetar las matemáticas exactas de los contenedores sin "engordar" las tarjetas.
* **Marquesina de Patrocinantes (Ticker):** Se programó un bucle infinito en CSS puro (`@keyframes`) para exhibir los logos de los aliados comerciales (Universitas y Endoret). 
* **Equilibrio de Peso Visual:** Se aplicó una regla de escalado del 35% (`transform: scale`) específicamente al logo de Endoret para equilibrar su volumen frente al formato rectangular del logo de Universitas.
* **Efecto "Fantasma Blanco":** Para mantener la elegancia sobre fondo oscuro, los logos del Ticker se procesan con `filter: brightness(0) invert(1) opacity(0.5)`, volviéndolos blancos translúcidos, y recuperan su color original al interactuar (`hover`).
* **Flujo Orgánico:** Se eliminaron las líneas divisorias (bordes CSS) entre el Ticker, los planes de patrocinio y el footer para erradicar el "efecto cajón", logrando una narrativa de navegación continua y fluida.

### 16 de Abril, 2026: Fase 2 - Arquitectura Híbrida y Presentación
* **El "Caballo de Troya" (Despliegue):** Se consolidó el protocolo de integración aislando el código HTML/CSS en un contenedor maestro (`.guardia-baja-app`) desprovisto de etiquetas `<body>` o `<html>`, permitiendo su inyección limpia mediante el widget HTML de Elementor sin generar conflictos con el tema nativo de WordPress.
* **Assets Remotos:** Se desacoplaron los recursos pesados (video de fondo `trailer.mp4` y fotografías del equipo). Ahora se sirven y consumen directamente desde las rutas estáticas de GitHub Pages, aliviando la carga del servidor principal.
* **Tipografía:** Integración vía `@font-face` de la fuente oficial del cortometraje, *Zumme Rough*.

### 13 de Abril, 2026: Fase 1 - Cimentación y Estructura Comercial
* **Infraestructura Base:** Creación del repositorio y sincronización de entornos locales con GitHub Desktop.
* **Identidad Visual:** Traducción de la estética del dossier al código, estableciendo la paleta de colores innegociable: Fondo Negro absoluto (`#000000`) y acentos en Rojo (`#e50914`).
* **Ingeniería Comercial:** Estructuración de los 4 niveles de patrocinio con una interfaz interactiva de revelado ("Reveal") para captar la atención de posibles inversores.

---

## Sobre el Proyecto

- **Director:** Luis Eduardo Pérez  Estudiante de la UCAB 
- **Ubicación de Rodaje:** CARACAS - VENEZUELA.
- **Estado:** En producción.

---

## Protocolo de Despliegue en WordPress

Para actualizar el sitio en el dominio oficial:
1. Realizar y probar los cambios en el archivo `index.html` de este repositorio local.
2. Hacer `Commit` y `Push` a la rama `main`.
3. Copiar la totalidad del código fuente de `index.html`.
4. En **WordPress (Elementor)**, ubicar el widget de **HTML**, borrar el código anterior y pegar la nueva versión.
5. Guardar y verificar que el ajuste de página sea **"Elementor Canvas"**.
---
# 📈 Log de Cambios - Lunes 20 de Abril
**Proyecto:** Sitio Web Oficial - "Guardia Baja"

### 1. UI/UX: Estrategia de Conversión (Hero Section)
* **Evolución del Botón:** Se transformó el acceso único de patrocinio en un sistema de **"Doble Impacto"**.
* **Implementación:** Creación del contenedor `.hero-botones` mediante **Flexbox** para asegurar simetría visual.
* **Resultado:** El sitio ahora presenta dos llamados a la acción con la misma jerarquía: **"Planes de Patrocinio"** y **"Postularse al Casting"**, equilibrando la captación de aliados comerciales y talento artístico.

### 2. Optimización Móvil (Responsive Design)
* **La "Llave Maestra":** Se incorporó la etiqueta `<meta name="viewport" content="width=device-width, initial-scale=1.0">` en la cabecera del código. Esto corrigió el error de escala que forzaba la visualización de escritorio en dispositivos móviles.
* **Media Queries (@768px):**
    * **Apilamiento Vertical:** Los botones del Hero ahora se posicionan uno sobre otro en móviles, mejorando la ergonomía táctil.
    * **Ajuste de Títulos:** Reducción del tamaño del `h1` para evitar desplazamientos de contenido y mejorar la legibilidad en pantallas pequeñas.
    * **Fichas de Casting:** Se forzó el ancho al 100% para garantizar una visualización limpia de los integrantes en el teléfono.

### 3. Performance y Gestión de Assets
* **Migración de Formatos:** Sustitución de archivos PNG de alta resolución (originales de 66MB) por versiones optimizadas en **JPEG**.
* **Estandarización de Dimensiones:** Se fijó un tamaño estricto de **500px x 750px** para todas las imágenes de los integrantes, manteniendo una relación de aspecto 2:3.
* **Impacto:** Reducción masiva del tiempo de carga y del consumo de datos, asegurando un rendimiento óptimo incluso en conexiones móviles limitadas.

### 4. Estética y Filtros CSS
* **Calibración de Imagen:** Ajuste del post-procesamiento digital aplicado por código para rescatar detalles en sombras y texturas oscuras.
* **Valores Finales de Producción:**
    * `filter: grayscale(100%)`: Mantiene la estética cruda y cinematográfica.
    * `contrast(105%)`: Calibración para evitar el empaste de las prendas negras.
    * `brightness(1.1)`: Incremento ligero para aportar nitidez a las facciones.
* **Dinamismo:** Se conservó la transición suave al estado `:hover` para que la imagen recupere su color original al interactuar con ella.

### 5. Configuración de Entorno y Despliegue
* **Contexto de IA:** Creación del archivo `CONTEXT.md` para estandarizar las reglas innegociables de diseño (colores `#000` y `#e50914`) en asistentes de código.
* **Protocolo de WordPress:** Se estableció el método de migración segura, copiando exclusivamente desde la etiqueta `<style>` hacia abajo para respetar el encabezado nativo de Elementor en `guardiabaja.com`.
---

## Contacto

* **Instagram:** [@guardiabajacorto](https://www.instagram.com/guardiabajacorto/)
* **Email:** guardiabajacorto@gmail.com
* **Formulario de Casting:** [Postularse aquí](https://docs.google.com/forms/d/1IQJresLvQr94sdr5CinwGDoQYpIKeUrSz7weCBY7Qxg/viewform)

---
* Web desarrollada por Carlos Javier Perez | Barquisimeto - Lara.*
https://www.instagram.com/carlosjperezss/
