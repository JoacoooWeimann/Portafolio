# Portafolio · Joaquín Weimann

Mi portafolio personal como desarrollador web Jr.

🔗 **Online:** https://joacoooweimann.github.io/Portafolio/

**Tecnologías:** HTML, CSS, Bootstrap 5, Bootstrap Icons, un poco de JavaScript. Publicado con **GitHub Pages**.

---

## Estructura

```
Portafolio/
├── index.html   ← Todo el contenido (una sola página con secciones)
├── style.css    ← Estilos propios, ordenados por sección (NAV, MAIN, conocimientos, proyectos, contacto)
└── imgs/        ← Logos de tecnologías, foto, capturas de proyectos y el CV en PDF
```

Secciones de `index.html` (cada una tiene un `id` para que el menú pueda saltar a ella con `href="#id"`):

| Sección | `id` | Qué tiene |
|---|---|---|
| Header | `inicio` | Navbar de Bootstrap que se colapsa en un botón en celular |
| Presentación | — | Nombre, título, frase y botón para descargar el CV |
| Sobre mí | `conocimientos` | Texto, educación y tecnologías (actuales, aprendiendo y de la escuela) |
| Proyectos | `proyectos` | Tarjetas con captura, tecnologías, descripción y links |
| Contacto | `contacto` | Redes y formulario que llega por email |

---

## Cómo agregar un proyecto nuevo

1. Sacar una captura del proyecto y guardarla en `imgs/` (mejor en `.jpg` o `.webp`, que pesan menos que `.png`).
2. En `index.html`, copiar el `<article class="card">` completo (hay un comentario arriba que lo marca) y pegarlo debajo.
3. Cambiar: la imagen, los íconos de tecnologías, el título, la descripción y los links de **Código** y **Demo**.

No hay que tocar el CSS: `.containercard` es un contenedor flex con `flex-wrap`, así que las tarjetas se acomodan solas en filas.

---

## Formulario de contacto (FormSubmit)

GitHub Pages solo sirve archivos estáticos: no puede procesar un formulario. Por eso se usa [FormSubmit](https://formsubmit.co), un servicio gratuito que recibe el POST y lo reenvía por email.

```html
<form action="https://formsubmit.co/TU-EMAIL" method="POST">
  <input type="hidden" name="_subject" value="Nuevo mensaje desde el portafolio"> <!-- asunto del email -->
  <input type="hidden" name="_next" value="https://...">   <!-- a dónde volver después de enviar -->
  <input type="hidden" name="_captcha" value="false">     <!-- sin captcha intermedio -->
```

La primera vez que alguien lo usa, FormSubmit manda un email para **activar** el formulario.

---

## Cambios de la actualización 2026

**Contenido**
- Título: "Desarrollador Web Jr." (antes: "Técnico informático", que pasó a Educación).
- "Sobre mí" actualizado: edad, stack actual y que estoy aprendiendo Node.js.
- Conocimientos divididos en: los que uso, **Aprendiendo** (Node.js) y **Usé en la escuela** (PHP, MySQL, Laravel).
- Proyectos: se reemplazaron los proyectos escolares por las [Landing Pages para comercios](https://github.com/JoacoooWeimann/landing-pages), con link al código.
- Etiquetas `og:` para que el link se vea con título e imagen al compartirlo en WhatsApp o LinkedIn.

**Correcciones**
- **Desborde horizontal en celular:** había elementos con `row` y `container` en la misma etiqueta. `.row` usa márgenes negativos pensados para ir *dentro* de un `.container`, no en el mismo elemento. Ahora es `container > row > col`.
- **Favicon roto:** la ruta decía `IMGS/` y la carpeta es `imgs/`. En Windows da igual, pero los servidores (como GitHub Pages) distinguen mayúsculas de minúsculas.
- `lang="es"` (estaba en `"en"`): lo usan los lectores de pantalla, el traductor y Google.
- Un solo `<h1>` por página. Las secciones usan `<h2>` y las tarjetas `<h3>`; así se ve el orden de importancia del contenido.
- Había un `<p>` dentro del `<h1>` y un `<button>` dentro de un `<a>`: son HTML inválido. El botón del CV ahora es un `<a class="btn-cv">`.
- La clase propia `.btn` pisaba la `.btn` de Bootstrap. Se renombró a `.btn-enviar`.
- Imágenes con `alt`, campos del formulario con `required` y `aria-label`.
- Se borraron estilos que ya no usaba ningún elemento (`.action-bottom-bar`, `.form-txt`, etc.).
- En celular, el menú se cierra solo al tocar una opción (JavaScript al final del `index.html`).

---

## Pendiente

- [ ] Reemplazar `imgs/WeimannJoaquin.pdf` por el CV actualizado.
- [ ] Agregar el link **Demo** de las landings cuando estén en Netlify (está comentado en la tarjeta).
