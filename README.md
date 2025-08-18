# Conversor Ultra Pro

Aplicación web profesional para convertir **Markdown**, **HTML** y **texto plano** en documentos **PDF de alta calidad**, **DOCX**, **PNG 4K**, **HTML standalone**, **TXT** y **MD**, con vista previa en tiempo real y una interfaz premium que evoca el estilo de Netflix y las mejores prácticas de diseño.

## 🚀 Características principales

### ✨ Interfaz de lujo

- **Tema oscuro de serie** con opción de cambiar a claro.
- **Fondo galáctico animado** con gradientes que cambian suavemente y efectos de glassmorphism.
- **Animaciones fluidas** y microinteracciones que dan vida a botones, iconos y títulos.
- **Diseño responsive**: la aplicación se adapta perfectamente a móviles, tablets y escritorio.

### 📝 Editor ultra avanzado

- **Área de edición** para Markdown, HTML o texto plano con fuente monospace.
- **Barra de herramientas** con acciones rápidas: negrita, cursiva, código, enlaces, imágenes, tablas, listas y títulos (H1–H3).
- **Carga de archivos** con arrastrar y soltar; admite `.md`, `.markdown`, `.txt`, `.html`, `.htm` y `.rtf`.
- **Acciones rápidas**: pegar desde portapapeles, auto‑formatear y limpiar.
- **Estadísticas en tiempo real**: caracteres, palabras, líneas, formato detectado y tiempo de lectura estimado.
- **Plantillas predefinidas**: Documento Académico, Reporte Corporativo, Currículum Profesional, Documentación Técnica y versiones **Pro** (Paper Académico Pro, Reporte Ejecutivo, Currículum Pro y Manual Técnico Avanzado).
- **Auto-guardado**: el contenido se guarda en `localStorage` cada 30 s y se puede recuperar al recargar la página.

### 📄 Exportación ultra premium

- **PDF profesional**: formato A4 con calidad configurable (0.7–1.0) y escala (1×–3×), encabezados y pies automáticos, líneas decorativas y tabla de contenidos cuando detecta más de dos títulos. Exporta documentos nítidos listos para impresión o presentación.
- **PNG de alta resolución**: captura fiel de la vista previa en blanco, con escala configurable hasta **4×** para obtener imágenes 4K y soporte de imágenes remotas.
- **DOCX estructurado**: respeta la jerarquía de encabezados y genera un documento compatible con Microsoft Word.
- **HTML standalone**: documento autónomo con estilos embebidos, tipografías legibles y tablas responsivas.
- **TXT/MD**: descarga del contenido limpio sin front‑matter ni tokens privados.
- **Print**: imprime la vista previa directamente desde el navegador.

### 🛡️ Seguridad y robustez

- **Sanitización HTML**: se eliminan etiquetas `<script>`, `<iframe>`, `<object>` y atributos peligrosos (`on*`, `javascript:`).
- **Limpieza de YAML**: se elimina el bloque de front‑matter al principio del documento.
- **Limpieza de caracteres privados**: se eliminan caracteres Unicode del área de uso privado y tokens de citación (`filecite`, `turnXfileY`).
- **Conversión de imágenes remotas**: las imágenes externas se descargan y convierten en Data URI para evitar problemas de CORS.
- **Límites de archivo**: configurable, ahora **50 MB** por defecto.

### ⚙️ Configuración avanzada

Puedes personalizar la experiencia desde el modal de configuración:

- Calidad PDF (estándar, alta, máxima)
- Escala de exportación (1×, 2×, 3×)
- Auto‑guardado (activado/desactivado)
- Numeración de líneas en el editor

## 🎯 Sistema de plantillas

La aplicación incluye cuatro plantillas listas para usar:

1. **Documento Académico** – Estructura para ensayos, papers y tesis con portada, resumen, introducción, desarrollo, conclusiones y referencias.
2. **Reporte Corporativo** – Informe profesional con resumen ejecutivo, análisis financiero (tabla de métricas), recomendaciones y próximos pasos.
3. **Currículum Profesional** – CV moderno con secciones de perfil, experiencia, educación, habilidades y certificaciones.
4. **Documentación Técnica** – Manual técnico con tabla de contenidos, requisitos, instalación, uso y guía de solución de problemas.

## 📌 Información adicional sobre convertidores

El conversor utiliza **html2pdf.js**, que combina `html2canvas` y `jsPDF` para generar PDF en el navegador. Esta librería tiene algunas limitaciones en comparación con soluciones de servidor como WeasyPrint o Prince XML【594604007913502†L14-L16】. Si necesitas soporte completo de CSS (CSS Grid, gradientes complejos, controles avanzados de page break o fuentes embebidas), considera estas alternativas:

- 🏆 **WeasyPrint** (gratuito, weasyprint.org) – Soporta CSS moderno (flexbox, grid, media queries) y fuentes personalizadas. Ideal para proyectos profesionales.
- 🥈 **Basados en Puppeteer** – Servicios como html-css-to-pdf.com, PDF24 Tools o HTMLtoPDF.io utilizan Chrome sin cabeza para renderizar tu HTML y convertirlo a PDF con alta fidelidad.
- 🥉 **Prince XML** (premium) – Ofrece el soporte más completo para CSS y tipografías, pero es un producto de pago.

Si al exportar encuentras problemas, probablemente se deban a limitaciones en el renderizado de:
- CSS Grid
- Gradientes y filtros complejos
- Controles detallados de `page-break` en tablas y secciones
- Fuentes embebidas o personalizados

Para la mayoría de documentos de texto y Markdown, **Conversor Ultra Pro** ofrece una conversión fluida y robusta directamente en el navegador, sin necesidad de instalaciones adicionales. Solo asegúrate de abrir la aplicación desde un servidor HTTP/HTTPS (GitHub Pages, Netlify, Vercel o un servidor local) y no con `file:///`, ya que los navegadores bloquean la carga de scripts y recursos externos【594604007913502†L14-L16】.

## 🛠️ Estructura del proyecto

Todos los archivos se encuentran en la raíz del repositorio:

```
/ (root)
 ├─ index.html      # Código HTML, CSS y JS embebido
 ├─ README.md       # Este documento
 └─ galaxy-background.webp  # Imagen de fondo
```

Para desplegar en **GitHub Pages**:
1. Sube estos archivos a la rama `main`.
2. Configura GitHub Pages en **Settings → Pages** seleccionando `main` como rama y `/ (root)` como carpeta.
3. Accede a `https://<usuario>.github.io/<repo>/` para usar el conversor.

## 🧰 Uso

1. Abre `index.html` desde GitHub Pages o un servidor local. **No uses `file:///` directamente**.
2. Escribe o pega tu contenido en el editor o carga un archivo.
3. Utiliza la barra de herramientas para dar formato y consulta las estadísticas en tiempo real.
4. Previsualiza el resultado en la hoja a la derecha. Usa los controles de zoom, pantalla completa y recarga.
5. Exporta tu documento en el formato deseado (PDF, DOCX, PNG, HTML, TXT, MD) o imprímelo.

## ℹ️ Créditos y agradecimientos

Inspirado en herramientas de conversión profesionales y en la estética de los servicios de streaming más populares. Integra tecnologías como `marked.js` para parseo de Markdown, `html2pdf.js` para generación de PDF y `docx.js` para documentos de Word. Implementado en **Vanilla JavaScript**, sin dependencias pesadas.

¡Disfruta de **Conversor Ultra Pro** y haz que tus documentos luzcan espectaculares!