# CiberIoT — Guía técnica para fotografías e imágenes

> Documento interno de producción. Estas indicaciones no se muestran en la página pública y no modifican los estilos visuales. Las medidas son recomendaciones de exportación para los espacios que existen actualmente en el prototipo; pueden ajustarse cuando se reemplacen las imágenes de referencia y se revise el encuadre real.

## Criterios generales

- **Formato preferido:** WebP para fotografías de la web. AVIF puede utilizarse si el flujo de publicación lo permite y se conserva una alternativa compatible. JPEG es aceptable como original o respaldo.
- **No usar:** PNG para fotografías, salvo que se necesite transparencia; imágenes reenviadas por WhatsApp, capturas de pantalla, miniaturas descargadas o archivos con marcas de agua.
- **Calidad de exportación:** WebP entre 78 y 85; JPEG entre 78 y 85. Revisar visualmente antes de publicar.
- **Peso orientativo:** imágenes de tarjetas entre 100 y 220 KB; imágenes de portada entre 250 y 450 KB en escritorio y 120 a 250 KB en móvil. Son objetivos, no límites rígidos: priorizar que la imagen se vea bien sin cargar archivos innecesariamente grandes.
- **Color:** sRGB.
- **Encuadre:** dejar espacio alrededor de rostros, logos y elementos importantes. El diseño utiliza recortes automáticos (`cover`/`object-fit: cover`), por lo que los bordes pueden quedar fuera.
- **Nombres de archivo:** minúsculas, sin espacios ni tildes; usar guiones. Ejemplo: `entrevista-especialista-ciberseguridad-ot.webp`.
- **Accesibilidad:** cada imagen informativa debe tener un texto `alt` que describa lo que realmente aparece. Si es puramente decorativa, usar `alt=""`.
- **Derechos:** usar fotografías propias, autorizadas o con licencia adecuada. Confirmar autorización de las personas identificables cuando corresponda. No presentar imágenes de stock como si fueran coberturas reales de CiberIoT.

## Especificaciones por espacio

| Espacio actual | Uso y encuadre recomendado | Escritorio | Móvil | Peso objetivo |
|---|---|---:|---:|---:|
| Portada principal (`.newsroom-hero`) | Fotografía panorámica de industria, centro de operaciones, minería o tecnología. Mantener el motivo principal hacia el centro/derecha y dejar zona izquierda limpia para el texto. | 2200 × 1200 px, 16:9 | 900 × 1200 px, 3:4, con encuadre propio | 250–450 KB / 120–250 KB |
| Imagen visual del hero (`.newsroom-visual`) | Fotografía de contexto tecnológico o comunicacional. Evitar fondos con demasiado detalle detrás del logo y la frase. | 1400 × 1000 px, aprox. 7:5 | 900 × 1000 px, aprox. 9:10 | 180–300 KB / 100–180 KB |
| Tarjetas de entrevistas | Retrato ambiental o fotografía de conversación. Priorizar rostros, micrófonos y contexto; evitar recortar cabezas o manos. | 1400 × 900 px, 14:9 | 900 × 900 px, 1:1, si el recorte de escritorio no funciona | 120–220 KB |
| Tarjetas de programas | Estudio, cámaras, micrófonos, panelistas o captura autorizada del programa. | 1400 × 900 px, 14:9 | 900 × 900 px, 1:1, si requiere otro encuadre | 120–220 KB |
| Eventos y coberturas | Fotografía documental de escenario, expositores, asistentes o stand. Buscar una toma horizontal que cuente qué ocurrió. | 1400 × 900 px, 14:9 | 900 × 1100 px, aprox. 4:5, para destacar personas/escenario | 120–220 KB |
| Multimedia / destacado YouTube | Miniatura horizontal del video o fotografía de producción. El contenido importante debe quedar dentro del área central. | 1600 × 900 px, 16:9 | 900 × 1200 px, 3:4, solo si se crea una pieza vertical específica | 150–280 KB |
| Logo | Mantener el archivo vectorial actual. No convertirlo en fotografía ni aplicar recortes. | SVG preferido | El mismo SVG adaptable | SVG optimizado, idealmente menos de 50 KB |

## ¿Se necesita una foto distinta para móvil?

No siempre. El navegador ya adapta las imágenes al ancho disponible, pero el recorte puede cambiar con `cover`.

- **Portada principal:** sí conviene preparar una versión móvil vertical, porque en pantallas angostas cambia mucho la composición y el texto ocupa otra proporción. Se puede conectar con una regla CSS dentro de `@media (max-width: 680px)`, sin cambiar la identidad visual.
- **Imagen visual del hero:** revisar el recorte en móvil. Preparar alternativa vertical solo si el logo, la fotografía o el texto quedan demasiado cortados.
- **Tarjetas de entrevistas, programas y coberturas:** primero probar la misma imagen con el recorte actual. Preparar una versión móvil cuadrada/vertical solo cuando el sujeto principal se pierda.
- **Multimedia:** mantener 16:9 para miniaturas de videos horizontales. Si se destaca un Reel o Short vertical, tratarlo como pieza distinta, no estirar una miniatura horizontal.

Cuando existan dos versiones, utilizar `<picture>` con `<source media="(max-width: 680px)">` y un `<img>` de respaldo. Para fondos CSS, definir una imagen alternativa en el media query correspondiente. No agregar versiones móviles hasta tener los archivos y comprobar el resultado.

## Recomendaciones de fotografía por sección

### Entrevistas
- Foto horizontal de dos personas conversando o de la persona entrevistada en contexto.
- Plano medio o medio corto; rostro bien iluminado.
- Evitar fondos con logos ajenos prominentes, pantallas ilegibles o elementos distractores.
- Si se usa una captura del video, seleccionar un fotograma nítido y autorizado.

### Programas y producción
- Estudio, cámara, micrófono, panel de conversación o detrás de cámaras.
- Evitar fotografías genéricas de bancos de imágenes si se puede mostrar la producción real de CiberIoT.
- Para episodios, usar una portada coherente entre capítulos.

### Eventos y coberturas
- Priorizar fotos propias: escenario, expositor, público, acreditación, stand y conversaciones.
- Registrar nombre del evento, ciudad, fecha y autor/fuente.
- Evitar usar una imagen de stock como prueba de que CiberIoT asistió a un evento.

### Industria, minería y tecnología
- Plantas, faenas, centros de control, automatización, redes industriales y equipos tecnológicos.
- Evitar fotografías que revelen información sensible de instalaciones, pantallas operativas, credenciales o datos de terceros.

## Lista de revisión antes de publicar

- [ ] La imagen corresponde al contenido y no induce a error.
- [ ] Se cuenta con permiso o licencia para utilizarla.
- [ ] Está exportada en WebP (o AVIF/JPEG de respaldo) y en sRGB.
- [ ] Se comprimió sin pérdida visual evidente y se verificó el peso.
- [ ] El motivo principal permanece visible en escritorio y móvil.
- [ ] Se definió un texto alternativo descriptivo.
- [ ] Se registraron autor/fuente, fecha y crédito cuando corresponda.
- [ ] Si es referencial, está claramente identificada como tal y no como material real de CiberIoT.

## Nota de implementación

Las dimensiones anteriores son tamaños de archivo recomendados, no dimensiones CSS. No se deben fijar atributos `width` y `height` con estos valores si el espacio visual tiene otra proporción. Mantener el comportamiento responsive existente y utilizar `width: 100%; height: 100%; object-fit: cover;` en tarjetas cuando corresponda. Para imágenes de contenido, reservar proporciones con `aspect-ratio` o dimensiones intrínsecas cuando se integre el gestor de publicaciones, evitando saltos de diseño al cargar.

**Importante:** las imágenes que aparecen actualmente en el prototipo son referencias visuales. Deben sustituirse por fotografías propias o material autorizado antes de presentar la web como versión publicada.
