---
name: yanez_odair
description: Identidad de marca de Servicio Técnico Yanez (fontanería y electricidad a domicilio, Vigo y Pontevedra) — colores exactos extraídos del logo real, tipografía Lato con su jerarquía de pesos, reglas de uso del logotipo y reglas de contacto/CTA. Consulta esta skill siempre que vayas a generar cualquier documentación o pieza para este negocio: memos, informes, guías de marca, posts o plantillas para Facebook/Instagram/LinkedIn/TikTok/YouTube, portadas, mockups, presentaciones o cualquier documento con su identidad visual — incluso si el usuario no dice "marca" ni "branding" y solo pide "un post para Yanez", "una plantilla", "un documento" o "algo para el negocio". El objetivo es que todo lo que se cree para Servicio Técnico Yanez use siempre los mismos colores, la misma tipografía y las mismas reglas de logo, sin tener que redescubrirlos cada vez.
---

# Identidad de marca — Servicio Técnico Yanez

Esta skill es la fuente de verdad de la identidad visual de **Servicio Técnico
Yanez** (fontanería y electricidad a domicilio, Vigo y Pontevedra, tel/WhatsApp
**655 292 399**). Los valores de abajo no son una propuesta: están medidos
directamente sobre el logotipo real del negocio (muestreo de píxeles), así que
úsalos tal cual en vez de inventar una paleta o tipografía nueva.

El tono de la marca es **confianza y cercanía doméstica** — atención 24/7,
trato humano, resolución de averías reales — no un tono "tech corporativo".
Ténlo en cuenta al escribir copy: cercano y directo, siempre con una llamada a
la acción hacia el teléfono.

## Paleta de colores

| Nombre | Hex | Uso |
|---|---|---|
| Azul Marino | `#050A30` | Titulares, texto principal, fondos oscuros de portadas |
| Azul Yanez (primario) | `#2F7FB7` | Color de marca — icono, botones, elementos destacados |
| Azul Claro | `#6FA9CE` | Degradados, brillos del icono, fondos secundarios |
| Naranja Yanez (acento) | `#F3820D` | Acento eléctrico — CTAs, cifras y datos clave |
| Azul CTA | `#004AAD` | Enlaces, teléfono de contacto, texto de llamada a la acción |
| Celeste Fondo | `#D7EAF2` | Fondo original del logotipo — tarjetas y fondos suaves |

No sustituyas el naranja por otro tono ni uses la marca en escala de grises —
el contraste azul/naranja (agua/electricidad) es el propio concepto del logo.

## Tipografía: Lato

Toda la marca usa **una sola familia**, Lato. La jerarquía se construye
variando el peso, nunca mezclando con otra fuente:

| Peso | Cuándo usarlo |
|---|---|
| Black 900 | Titulares, nombre de marca ("YANEZ"), CTAs grandes |
| Bold 700 | Subtítulos, botones, teléfono/CTA, énfasis dentro de un párrafo |
| Regular 400 | Cuerpo de texto, descripciones, copy largo |
| Light 300 | Etiquetas, datos secundarios, texto superpuesto sobre fotos |
| Italic 400 | Citas de clientes, matices |

Para piezas HTML/artifact, incrusta Lato como `@font-face` con `data:` URIs en
vez de enlazar Google Fonts (el CSP de los artifacts bloquea CDNs externos).
Los cuatro pesos + la itálica ya están descargados en `assets/`:
`lato-300.woff2`, `lato-400.woff2`, `lato-400i.woff2`, `lato-700.woff2`,
`lato-900.woff2`. Léelos y conviértelos a base64 para el `@font-face` — no
hace falta volver a descargarlos de Google Fonts cada vez.

## El logotipo

- **assets/logo_full.png** — lockup completo (icono + "Servicio Técnico
  YANEZ" + "Atención 24/7 | Calidad y Confianza"), fondo celeste `#D7EAF2`
  horneado (no es transparente).
- **assets/logo_icon.png** — solo el icono (gota de agua azul + rayo naranja
  superpuesto = fontanería + electricidad), recortado, útil para avatares,
  favicons o marcas de agua pequeñas.

Ambos archivos son copias locales listas para usar (léelos con el asset
loader / conviértelos a base64 para incrustar) — no dependen de tener acceso
a Google Drive. El original vive en Drive, carpeta "logo", archivo
`logo_google_Copia_070715.png` (el nombre es engañoso, es el logo real),
`fileId` `16zIkCtQbzaZKVvbFPndwSn1oVeGfGhG_`, privado (solo
`yanezoda@gmail.com`). Si en algún momento necesitas subirlo a una
herramienta externa que solo acepta URLs públicas (Canva `upload-asset-from-url`,
Gamma), no podrás usar la URL de Drive directamente — pide al usuario que
comparta el archivo como "cualquiera con el enlace puede ver", o usa las
copias de `assets/` cuando la herramienta acepte archivo/base64 en vez de URL.

Reglas de uso:
- No deformar ni rotar el icono.
- No cambiar el naranja del rayo por otro color.
- Dejar alrededor del icono un margen de respiro mínimo equivalente a la
  altura de la gota.
- Tamaño mínimo en digital: ~32px de alto.
- Como el logo no tiene fondo transparente, evita colocarlo sobre fotos
  oscuras o muy saturadas sin una base clara detrás — se pierde.

## Reglas de contacto y llamada a la acción

Esto ya es una regla permanente del negocio (ver `CLAUDE.md` del repo) — esta
skill la refuerza, no la sustituye:

1. Incluir siempre el logo (o el icono si el espacio es pequeño).
2. Evitar fondos planos/lisos — usar degradados, texturas o fotos reales de
   los trabajos en vez de solo texto sobre un color sólido.
3. Incluir el teléfono **655 292 399**, la disponibilidad 24/7, y una llamada
   a la acción explícita (pedir presupuesto, llamar, escribir por WhatsApp) —
   no basta con mostrar el caso, hay que invitar a actuar.

## Cómo aplicar esto según el tipo de entregable

**Documentación de texto** (memos, informes, guías, resúmenes): usa el Azul
Marino para titulares y el Azul CTA para cualquier enlace o dato de contacto;
mantén el copy en tono cercano, no corporativo; si el documento va a Word o
PDF, usa Lato si está disponible como fuente del sistema o del generador, y si
no, elige una sans-serif humanista similar antes que una fuente genérica tipo
Arial por defecto.

**Piezas visuales / redes sociales** (posts, portadas, plantillas, mockups en
HTML o Canva): aplica la paleta completa, la jerarquía tipográfica de pesos, y
las reglas de logo y contacto de arriba. Un ejemplo ya construido con estos
mismos criterios (paleta extraída, Lato incrustado como `@font-face`, dos
mockups de aplicación — portada de Facebook y plantilla de post cuadrado) es
el artifact "Identidad Yanez" generado en una sesión anterior; sirve como
referencia de estilo, pero no hace falta tenerlo abierto para aplicar esta
skill.

**Canva**: recuerda las limitaciones ya conocidas del equipo (`generate-design`
desactivado, TikTok solo acepta JPEG/WEBP y resolución ≤~1080p, sin
herramienta para borrar diseños — mover temporales a la carpeta "BORRAR" de
Canva). Consulta `CLAUDE.md` del repo para el detalle completo de estos
workarounds; esta skill no los duplica.
