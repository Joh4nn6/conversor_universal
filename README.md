# Conversor

Aplicación web estática para convertir **Markdown o HTML** en documentos **PDF, DOCX, PNG, TXT y MD**, con una interfaz galáctica oscura, fondo animado y un título con degradado en movimiento. La vista previa muestra **exactamente** lo que se exportará.

## Características principales

- **Editor**: área de texto para escribir o pegar contenido en Markdown o HTML, con conteo de caracteres y palabras.
- **Carga de archivos**: admite archivos `.md`, `.markdown`, `.txt`, `.html` y `.htm` mediante un campo de tipo archivo.
- **Previsualización en vivo**: representa el contenido en una “hoja” blanca estilo A4, mostrando exactamente cómo se exportará.
- **Limpieza de front‑matter**: elimina bloques YAML al inicio del documento (entre `---` y `---`).
- **Sanitización**: remueve etiquetas `<script>`, `<iframe>` y atributos inseguros (`on*`, `javascript:`) del HTML para evitar código malicioso.
- **Exportaciones**:
  - **PDF** (html2pdf.js): multipágina, formato A4 vertical, escala 2; se fuerza fondo blanco y texto negro, con encabezado y pie de página (título y número de página). Colores inline definidos por el usuario se respetan.
  - **DOCX** (docx): cada línea del texto limpio (sin front‑matter) se convierte en un párrafo.
  - **PNG**: captura de la previsualización con fondo blanco.
  - **TXT** y **MD**: descarga directa del contenido sin front‑matter.
- **Tema oscuro/claro**: selector opcional; la exportación siempre será con fondo blanco y texto negro. El fondo galáctico se mueve suavemente y el título tiene un gradiente animado.
- **Botones**: animaciones suaves al pasar y presionar; el botón principal tiene un degradado animado.
- **Diseño responsive**: dos columnas en escritorio y una sola columna en pantallas ≤ 980 px.

### Compatibilidad con imágenes remotas y colores

- Si tu contenido incluye imágenes con URLs externas, el conversor intenta incrustarlas automáticamente para evitar problemas de CORS. Para mejor funcionamiento, aloja las imágenes en el mismo dominio o usa enlaces que permitan el acceso desde otros orígenes.
- Los colores definidos en elementos HTML inline (como `<span style="color:#e50914">`) se respetan tanto en la vista previa como en el PDF. Los emojis y caracteres especiales también se visualizan correctamente.

## Uso

1. Abre `index.html` en un servidor HTTP (por ejemplo, GitHub Pages, Vercel, Netlify o un servidor local). **No uses `file:///` directamente** para evitar restricciones de CORS que impiden cargar librerías y exportar PDF.
2. Escribe o pega tu Markdown/HTML en el editor, o bien carga un archivo desde tu equipo.
3. Observa la previsualización en la hoja blanca. Los estilos aplicados a tu Markdown/HTML (colores, resaltados, emojis) se mantendrán en la previsualización y en las exportaciones.
4. Haz clic en los botones de exportación para generar el formato deseado.

> **Colores:** El Markdown puro no define colores. Para aplicar colores específicos, usa HTML inline, por ejemplo: `<span style="color:#e50914">Texto</span>`. Estos colores se respetarán en la previsualización y en el PDF, siempre que no afecten la legibilidad.

## Estructura del proyecto

El repositorio contiene los siguientes archivos en la raíz:

```
/ (root)
 ├─ index.html     # estructura principal y lógica
 ├─ styles.css     # estilos y temas
 ├─ README.md      # este documento
 └─ galaxy-background.webp  # imagen de fondo estática
```

## Despliegue en GitHub Pages

1. Sube `index.html`, `styles.css`, `galaxy-background.webp` y `README.md` a la rama `main` (carpeta raíz) de tu repositorio.
2. En tu repositorio, ve a **Settings → Pages** y selecciona `main` como rama y `/ (root)` como carpeta.
3. Guarda la configuración; tu sitio quedará disponible en `https://<usuario>.github.io/<repo>/`.

## Uso offline opcional

Si deseas utilizar la aplicación completamente offline, descarga las librerías (`marked`, `html2pdf.bundle.min.js`, `docx`, `FileSaver`) y referencia los archivos locales en `index.html` en lugar de las CDN.

---

Proyecto creado con foco en rendimiento y robustez, sin dependencias pesadas ni animaciones globales. Inspirado en la estética de Netflix Premium.