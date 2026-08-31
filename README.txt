RECOVERLAB — RECUPERACIÓN DE DATOS APPLE MAC (MADRID)

Repositorio procesado por primera vez en esta sesión (no tenía README).

Dominio:
https://empresarecuperaciondatosdiscoduro.com.es/
(ya estaba correctamente configurado en canonical, og:url y JSON-LD;
confirmado también directamente por el cliente al pasar este
repositorio. Sin colisión con ningún otro dominio revisado en esta
sesión.)

Teléfono: +34 914 46 85 03, consistente en la caja de información,
botones y footer (un único número, sin discrepancias); no se ha
tocado.

Sitio one-page desde su origen: no hay eliminaciones de /servicios/ ni
/modelos/ en el historial, así que NO se ha añadido middleware.mjs, no
aplica.

REVISIÓN (todo lo aplicado en esta primera pasada):
- BUG REAL — sin menú móvil: .links se ocultaba a partir de 920px
  (display:none) sin ningún botón ni menú alternativo, así que la
  navegación desaparecía por completo en móvil. Añadido botón
  .menu-btn + desplegable #mobileMenu con todos los enlaces.
- BUG REAL — sin CSS de posicionamiento del chat: no existía ninguna
  regla para #n8n-chat .chat-window-toggle/.chat-window, así que el
  widget se mostraba en su posición por defecto del CDN, sin borde y
  potencialmente solapado con el botón flotante de WhatsApp (que
  además estaba en bottom:112px, una posición no estándar en la
  familia). Añadida la posición estándar (chat por encima del
  WhatsApp, con borde blanco) y devuelto el WhatsApp a bottom:22px.
- Google Analytics: no existía. Añadido G-20HX03CKP8.
- Meta robots: no existía. Añadido.
- Schema.org: no existía. Añadido LocalBusiness (nombre, url,
  teléfono, descripción, dirección, areaServed Madrid, sameAs con
  Google Maps y YouTube).
- Sección SEO: no existía. Añadida sección "Guía" (id="guia", enlazada
  en el menú de escritorio y móvil) con contenido propio sobre qué
  hacer y qué evitar cuando un Mac falla y hay datos importantes
  dentro.
- Banner de cookies: no existía. Añadido (Aceptar / Rechazar /
  Política de privacidad → https://kelatos.com/privacy-policy/), con
  diseño apilado a ancho completo en móvil.
- .navcall: ya mostraba solo "Llamar ahora" (sin bug de texto largo);
  añadido white-space:nowrap como salvaguarda estándar.
- H1 de portada reescrito, corto, directo y totalmente afirmativo (sin
  interrogación ni condicionales — antes usaba "si podrás recuperar
  tus datos"), incluye la marca: "Tu Mac no funciona. Aquí protegemos
  y recuperamos tus datos." Tamaño del H1 aumentado: clamp(36-56px) →
  clamp(46-74px) en escritorio, 34px → 46px en móvil.
- package.json: añadido engines (node 22.x).
- api/contacto.js ya usaba SMTP + nodemailer correctamente; no
  requería conversión.

REVISIÓN ADICIONAL (a petición del cliente):
- Menú de escritorio: varios enlaces ("Qué ha pasado", "Cómo
  trabajamos", "Pedir cita", "Contacto") se partían en dos líneas por
  falta de espacio (7 enlaces + píldora "Llamar ahora" + logo de
  300px en una fila). Añadido white-space:nowrap a .links a y
  reducidos ligeramente gap (22px→18px) y font-size (14px→13.5px)
  para que quepan en una sola línea sin partirse.
- Icono de WhatsApp del botón grande: el <svg> no tenía tamaño
  definido (sin width/height ni regla CSS), así que se mostraba al
  tamaño por defecto del navegador, mucho más grande de lo previsto.
  Añadido .btn svg{width:22px;height:22px;margin-right:8px;flex:0 0
  22px}.

REVISIÓN ADICIONAL (checklist unificado de la familia, a petición del cliente):
- H1 repetía la plantilla "no funciona" ("Tu Mac no funciona. Aquí
  protegemos y recuperamos tus datos."). Reescrito en formato
  imperativo, incluye la marca: "Recuperamos los datos de tu Mac con
  garantía." (8 palabras).
- BUG REAL — el botón CTA de teléfono no tenía icono, a diferencia del
  de WhatsApp. Añadido (verificado con cuidado el cierre de las
  etiquetas </a>: 30 aperturas / 30 cierres).
- BUG REAL — la casilla de política de privacidad existía pero el
  texto no enlazaba a ningún sitio. Añadido el enlace estándar de la
  familia a https://kelatos.com/privacy-policy/, resaltado en azul.
- Añadida franja de aviso de servicio técnico independiente debajo del
  menú (no existía). Verificado antes que .header no usa
  display:flex directamente.
- Añadido "Sábados, domingos y días festivos estamos cerrados" debajo
  del horario.
- Verificado sin bugs: .hero-orbit es una forma decorativa sin texto
  (no es el patrón de etiqueta rotada tipo hero-chip); el ticker
  ".hero::after" ya se ocultaba correctamente en móvil; Cal.com ya
  estaba presente; schema.org ya usaba correctamente el único
  teléfono de este repo.
- NO SE HA TOCADO — mismo patrón que en reparacion-ordenadores-madrid
  (repo procesado en esta misma sesión): el formulario usa un envío
  HTML tradicional (action="/api/contacto" con recarga de página) en
  vez del fetch/AJAX del resto de la familia. Es funcionalmente
  coherente (la API responde con una página que muestra un alert() y
  redirige), así que no se ha considerado un bug.

Variables SMTP en Vercel (ya configuradas, sin cambios):
SMTP_HOST=cp7124.webempresa.eu
SMTP_PORT=465
SMTP_SECURE=true
SMTP_USER=soporte@kelatos.com
SMTP_PASS=[configurada únicamente en Vercel]
CONTACT_EMAIL=soporte@kelatos.com
