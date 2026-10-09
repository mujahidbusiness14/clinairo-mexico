# Clinairo — sitio web (clinairo.mx)

Sitio de una sola página, estático, en español de México. Sin build step.

## Desplegar en Vercel

1. Sube esta carpeta a un repositorio de GitHub.
2. En Vercel: **Add New → Project → Import**.
3. Framework Preset: **Other**. Build Command: vacío. Output Directory: `.`
4. Deploy.
5. **Settings → Domains → Add** `clinairo.mx` y sigue las instrucciones de DNS.

O desde la terminal: `npx vercel --prod` dentro de esta carpeta.

## Qué incluye

| Archivo | Para qué |
|---|---|
| `index.html` | El sitio completo (CSS y JS en línea) |
| `aviso-de-privacidad.html` · `terminos.html` | Páginas legales — **borrador, requieren revisión de un abogado** |
| `404.html` | Página de error |
| `images/` | Fotografías optimizadas |
| `sitemap.xml` · `robots.txt` | Indexación |
| `llms.txt` | Contexto para buscadores con IA (ChatGPT, Claude, Perplexity) |
| `site.webmanifest` + favicons | Iconos e instalación como app |
| `favicon-48/96/144x144.png` | Requisito de Google: el favicon que sale en resultados de búsqueda debe ser múltiplo de 48px |
| `og-image.png` | Vista previa al compartir (1200×630) |
| `vercel.json` | Cabeceras de seguridad y caché |

## Seguridad

`vercel.json` aplica CSP, HSTS, X-Frame-Options: DENY, X-Content-Type-Options,
Referrer-Policy y Permissions-Policy. La CSP permite `'unsafe-inline'` porque el CSS
y el JS están en línea; si algún día se extraen a archivos, endurecerla.

## Pendientes antes de publicar

- [ ] Revisión legal del aviso de privacidad y los términos.
- [ ] Correo: el sitio usa `contact@clinairo.com` pero el dominio es `clinairo.mx`.
      Considerar `contacto@clinairo.mx`.
- [ ] Confirmar que el domicilio fiscal coincide con el que se registrará en Meta
      para la verificación de WhatsApp Business.
- [ ] Rehacer `og-image.png` en Canva con la tipografía de marca (Fraunces).
- [ ] Sección "Cómo funciona" (los 4 pasos) aún no existe; el enlace del menú
      apunta por ahora a la sección "No es otra plataforma".
- [ ] Verificar el dominio en Google Search Console y enviar el sitemap.
- [ ] El favicon aparece en Google días o semanas después del primer rastreo.
      No se puede forzar; sólo se acelera pidiendo la indexación de la página de inicio.

## Editar

Todo el contenido está en `index.html`. Para cambiar una foto, sustituye el archivo
en `images/` conservando el nombre.
