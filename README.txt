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

Variables SMTP en Vercel (ya configuradas, sin cambios):
SMTP_HOST=cp7124.webempresa.eu
SMTP_PORT=465
SMTP_SECURE=true
SMTP_USER=soporte@kelatos.com
SMTP_PASS=[configurada únicamente en Vercel]
CONTACT_EMAIL=soporte@kelatos.com
