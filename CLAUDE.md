# Contexto del negocio — Servicio Técnico Yanez

Este repositorio se usa como base de sesión para gestionar las redes sociales
y publicaciones de **Servicio Técnico Yanez** (Fontanería y Electricidad a
domicilio, Vigo y Pontevedra). El contenido del repo en sí (colección de
workflows n8n) no está relacionado con el negocio — este archivo solo guarda
contexto e instrucciones persistentes para futuras sesiones de Claude,
independientemente del equipo/dispositivo desde el que se inicie la sesión
(el archivo vive en GitHub, no en un equipo concreto).

## Datos de cuenta

- **Metricool brandId**: `6689346` (label `yanezoda_1`, owner `yanezoda@gmail.com`)
- **Timezone**: `Europe/Madrid`
- **Teléfono/WhatsApp de contacto**: `655 292 399` — incluir siempre en las
  publicaciones como llamada a la acción (llamar, WhatsApp, "pide presupuesto
  gratis").
- **Redes conectadas y en uso**: Facebook, Instagram, LinkedIn, TikTok, YouTube.
- **Redes conectadas pero SIN usar todavía**: Pinterest, Google Business Profile
  (GBP). Están disponibles en la cuenta de Metricool pero no se les ha
  publicado nada aún. Para usar Pinterest hace falta el nombre exacto de un
  tablero (`pinterestData.boardId` o nombre humano) — pedírselo al usuario
  antes de programar nada ahí. No programar nada en ninguna de las dos sin
  confirmar antes con el usuario.
- **Cuentas publicitarias conectadas** (no son redes de publicación orgánica):
  Facebook Ads, Google Ads.
- **X/Twitter: NO disponible.** El usuario no tiene acceso a esa cuenta y
  pidió eliminarla del flujo de trabajo (confirmado 2026-08-11). Ya no
  aparece en `networksData` de `getBrandSettings`, así que está
  desconectada de Metricool. **No programar publicaciones en Twitter/X.**
  Si algún post antiguo la sigue teniendo como red, hay que corregirlo
  (pasar el contenido a otra red o dejarlo en borrador).

## Google Drive — carpeta de contenido para redes

- Carpeta principal: **"REDES YANEZ"**
  (id `1eB9MrLqBI7902cvaReu7Usz6nbuWHdXw`).
- El usuario sube ahí los vídeos y fotos reales de los trabajos (no
  generados por IA) para que se conviertan en publicaciones. Revisar esta
  carpeta cuando el usuario diga que ha subido contenido nuevo — buscar por
  `parentId` con `Google_Drive__search_files`.
- El Google Drive de esta cuenta **está vinculado a Metricool**: se puede
  pasar directamente la `viewUrl` de un archivo de Drive
  (`https://drive.google.com/file/d/<id>/view?usp=drivesdk`) como `media` en
  `createScheduledPost`/`updateScheduledPost` y Metricool lo descarga solo,
  sin que Claude tenga que mover los bytes. Es la forma correcta de subir
  vídeos/fotos grandes que el usuario proporciona.
- Carpeta **"logo"** con el logo de marca (ver sección siguiente).

## Logo de marca

- Ubicación: Google Drive, carpeta **"logo"**.
- Archivo: `logo_google_Copia_070715.png` (el nombre del archivo es engañoso —
  NO es el logo de Google, es el logo real del negocio).
- Google Drive file ID: `16zIkCtQbzaZKVvbFPndwSn1oVeGfGhG_`
- Descripción visual: gota de agua azul con un rayo naranja superpuesto
  (icono fontanería + electricidad), texto "Servicio Técnico YANEZ" y
  subtítulo "Atención 24/7 | Calidad y Confianza".
- **Este archivo es privado** (solo el owner tiene permiso). Canva/Gamma no
  pueden descargarlo porque sus herramientas solo aceptan URLs ya públicas.
  Si se necesita el logo real incrustado en una imagen generada, pedir al
  usuario que lo comparta como "cualquiera con el enlace puede ver"; mientras
  tanto, aproximar el icono (gota azul + rayo naranja) descriptivamente en el
  prompt de generación en vez del archivo exacto.

## Regla permanente para imágenes de publicaciones

Al generar o editar imágenes para publicaciones en redes sociales de este
negocio (Canva, Gamma, etc.):

1. **Incluir siempre el logo** de la marca (ver arriba, o su aproximación si
   el archivo real no está disponible).
2. **Evitar fondos planos/lisos.** Usar composiciones con más profundidad:
   degradados, texturas, fotos o elementos visuales relacionados con
   fontanería/electricidad, en vez de solo texto sobre un color sólido.
3. **Incluir información de contacto clara**: servicios ofrecidos, teléfono
   655 292 399, disponibilidad (24/7), y una llamada a la acción explícita
   invitando a contactar/pedir presupuesto (no solo mostrar el caso, invitar
   a actuar).

Esta regla aplica a todas las sesiones futuras, no solo a la conversación en
la que se definió.

## Transparencia IA (Reglamento UE 2024/1689, art. 50) — obligatorio desde 2026-08-02

Desde el 2 de agosto de 2026 aplican las obligaciones de transparencia del
artículo 50 del Reglamento europeo de IA (deepfakes y sistemas conversacionales
que interactúan con personas). Aplican a cualquier proyecto de este negocio
que use avatar digital o asistente automatizado de contacto con clientes:

- **Vídeos con avatar de Odair** (HeyGen u otra herramienta de clonación de
  cara/voz): todo vídeo debe llevar el texto **"Avatar digital de Odair
  Yanez generado mediante IA"** visible en pantalla como overlay de texto —
  no basta con ponerlo solo en la descripción/caption de la red social, que
  puede quedar oculta tras "ver más". Añadirlo igual que el resto de textos
  del vídeo, idealmente visible al inicio y/o de forma persistente en una
  esquina durante todo el vídeo.
- **Asistente virtual de contacto con clientes** (bot de WhatsApp u otro
  canal automatizado con LLM): el primer mensaje de cualquier conversación
  debe identificarse como IA antes de pedir cualquier dato del cliente, con
  este texto fijo:
  > "Hola, soy el asistente virtual de Servicio Técnico Yanez. Recogeré los
  > datos del trabajo y Odair revisará personalmente el presupuesto y la
  > disponibilidad."

  No cambiar esta redacción sin confirmarlo antes con el usuario.

Esta regla aplica a todas las sesiones futuras, no solo a la conversación en
la que se definió.

## Patrón habitual de publicación (una "campaña" por caso)

Cada trabajo/caso real (avería resuelta, instalación, consejo) se suele
convertir en varios posts, uno por red, con texto adaptado a cada una,
publicados el mismo día con minutos de diferencia:

- **Facebook + Instagram**: mismo post, texto más largo y narrativo. Si el
  material es vídeo de un trabajo real, usar tipo `REEL` en ambas redes; si
  es una imagen/gráfico, tipo `POST`.
- **LinkedIn**: versión más profesional/corta del mismo caso, red aparte.
- **TikTok**: versión muy corta, en tono directo, con hashtags simples.
- **YouTube**: solo si hay vídeo real disponible, como Short
  (`youtubeData.type: "short"`).

Todas las publicaciones creadas deben llevar `draft: false` y
`autoPublish: true` — si no, se quedan "atascadas" y nunca se publican solas
(ver problema conocido más abajo).

## Problemas técnicos conocidos y cómo resolverlos

- **TikTok rechaza fotos en PNG.** Solo acepta JPEG/WEBP para posts de foto.
  Si un post de TikTok usa una imagen `.png`, convertirla a `.jpg` (ver
  workaround de Canva abajo) antes de programarlo o volverá a dar error.
- **TikTok también tiene un límite de resolución (~1080p).** Una imagen de
  1856×2304 fue rechazada por exceder el máximo; el mismo archivo a
  1080×1341 sí se aceptó. Exportar para TikTok siempre a un tamaño con el
  lado mayor ≤ ~1350px.
- **Los posts a veces se crean con `draft: true` y `autoPublish: false`** (da
  igual el origen). Quedan visibles como "Pending" pero nunca se publican
  solos, aunque pase su hora. Revisar esto de forma proactiva en cualquier
  publicación futura y corregirlo con `updateScheduledPost`.
- **No se puede hacer `curl`/descarga directa desde Bash a CDNs externos**
  (p. ej. `static.metricool.com`, `cdn.gamma.app`): la política de red de
  este entorno lo bloquea (403). Hay que apoyarse en las herramientas MCP
  (Canva, Google Drive, Gamma), que sí pueden traer contenido desde sus
  propios servidores sin pasar por el sandbox de Claude.
- **La generación de diseños con IA de Canva (`generate-design`) está
  desactivada para este equipo/cuenta.** No se puede usar para crear piezas
  nuevas. Tampoco `import-design-from-url` funciona con imágenes sueltas
  (solo con documentos estructurados tipo PDF/PPTX).
  - Workaround para convertir formato o montar una imagen con overlay de
    texto: `upload-asset-from-url` (sube la imagen como asset) → copiar o
    reusar un diseño existente como lienzo en blanco (`copy-design` /
    `resize-design`) → `edit-design` para borrar los elementos originales e
    insertar la imagen a pantalla completa (`insert_fill`) + texto
    (`add_text` + `format_text`) → `export-design` como jpg.
  - Canva **no tiene herramienta para borrar diseños**. Los archivos de
    trabajo temporales se mueven a la carpeta de Canva
    **"BORRAR - copias temporales (Claude)"** (id `FAHR_KBkr-U`) en vez de
    dejarlos sueltos — revisarla de vez en cuando y vaciarla a mano desde
    Canva si se acumula.
  - No generar vídeo real con estas herramientas: si Metricool pide vídeo
    (p. ej. Reels, YouTube) y no hay grabación real disponible, se puede
    exportar un diseño estático de Canva como `.mp4` (queda como una imagen
    fija con duración de vídeo, no tiene movimiento) solo como último
    recurso, dejando claro al usuario que no es vídeo real.

## Estado de la semana (referencia, puede quedar desactualizado)

A fecha 2026-08-11 hay campañas ya programadas y activadas (`draft:false`,
`autoPublish:true`) para el 12, 13, 14, 15 y 16 de agosto, más posts sueltos
de Facebook los días 17, 18 y 19. Antes de dar nada por hecho, comprobar el
estado real con `getScheduledPosts` — esta sección es solo una foto de
referencia, no la fuente de verdad.
