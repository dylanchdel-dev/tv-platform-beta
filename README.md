# SeñalSur — beta temporal con señales comprobadas

Web: https://dylanchdel-dev.github.io/tv-platform-beta/

## Selección pública — 23/10/2026

La beta publica únicamente **14 canales, 14 feeds y 14 streams HTTPS** cuya reproducción fue comprobada en Chrome de Work. Las 13 señales iniciales se probaron desde la aplicación pública. TyC Sports / tyc24 también superó la prueba desde la beta publicada: video 1920×1080, estado playing y tiempo avanzando hasta 80,8 segundos. Se observó video decodificado y avance del tiempo, no solo una respuesta HTTP o un manifiesto HLS. Se excluyeron también los feeds vacíos y las alternativas que no fueron probadas de los canales aprobados.

Cada tarjeta muestra la fecha de comprobación. `out/validation.json` y `public/validation.json` registran canal, feed, stream, hash SHA-256 de la URL y métricas observadas. El workflow exige una prueba positiva para cada candidato publicado y rechaza URLs o IDs sin evidencia correspondiente. Son pruebas manuales del día indicado; **no garantizan disponibilidad permanente, acceso desde todas las regiones ni derechos o identidad editorial de retransmisiones externas**. No hay checker automático ni proxy.

| Canal | Tiempo observado | Ancho decodificado |
| --- | ---: | ---: |
| Antena SUR | 32.4 s | 1920 px |
| Caritas TV | 32.3 s | 1920 px |
| ESPN 2 Latin America | 100.8 s | 1920 px |
| ESPN 3 Latin America | 49.0 s | 1920 px |
| Monterrico TV | 35.5 s | 1920 px |
| ESPN 4 Latin America | 48.4 s | 1920 px |
| CRTV | 36.6 s | 1280 px |
| Canal Showsport | 38.2 s | 960 px |
| ESPN 5 Latin America | 46.5 s | 1920 px |
| ESPN 6 Latin America | 101.2 s | 1920 px |
| ESPN 7 Latin America | 45.6 s | 1920 px |
| ESPN Latin America | 101.8 s | 1920 px |
| FIFA+ | 33.8 s | 1280 px |
| TyC Sports · tyc24 (beta pública) | 80.8 s | 1920 px |

## Catálogo original conservado

El snapshot completo del 17/10/2026 contiene 1.615 canales, 1.752 feeds, 941 streams y 1.646 logos. Permanece intacto en el proyecto original y sus respaldos. Esas cifras **no son el contenido de la selección pública actual**. No se reimportaron datos ni se modificaron URLs de proveedores. El inventario histórico de deportes se conserva en [SPORTS_VALIDATION.md](SPORTS_VALIDATION.md).

TNT Sports Argentina/Chile, ESPN Premium, L1 Max, Tigo Sports+, Teletrak, Turf Móvil y Sqala no tienen prueba positiva aplicable y quedan fuera. Ver ESPN u otro canal no demuestra que transmita un partido concreto. No está confirmada la cobertura completa de Liga Argentina, Liga Chilena, Libertadores, Copa Argentina, Copa Chile, Sudamericana o Champions.

## Publicación y mantenimiento

Repositorio independiente `dylanchdel-dev/tv-platform-beta`; no se modifican otros proyectos. El ZIP incluye fuentes, lockfile y export estático compilado bajo `tv-platform-github-pages/`. `.github/workflows/pages.yml` extrae y valida `out/` antes de publicar mediante las acciones oficiales de GitHub Pages. Settings → Pages → Source: GitHub Actions. Se activa al cambiar el ZIP o el workflow en main.

Para actualizar: comprobar reproducción real de cada URL; actualizar catálogo y manifiesto con la misma fecha e IDs; ejecutar `npm run build` (Node.js 24), validar la correspondencia y reemplazar el ZIP con su estructura actual. No publicar el respaldo completo como catálogo sin nuevas pruebas. No hacen falta `.env` ni DATABASE_URL para esta adaptación.

Búsqueda, filtros, diseño, logos y reproductor existentes conservados. Con 14 canales todos caben en una sola página. Las rutas usan `/channel/?id=UUID&feed=UUID`; enlaces antiguos fuera de la selección muestran que la señal no está validada.

## Límites del hosting temporal

GitHub Pages es estático: **no hay PostgreSQL, panel administrativo, login ni APIs administrativas** en esta beta. Las rutas administrativas no tienen backend. No contiene secretos, credenciales, cuentas administrativas ni datos de auditoría.

Railway sigue siendo el destino del proyecto completo Next.js + Prisma + PostgreSQL y administración. Cambiar el hosting no elimina CORS, bloqueos regionales, HTTP incompatible con HTTPS o errores externos del proveedor. Para restaurar el proyecto completo debe retomarse el despliegue Railway y el respaldo ya verificado; no se declara realizado aquí.

## Integración focalizada de TyC — 23/10/2026

Se probaron siete URLs de iptv-org, revisión eb57e1587128c80bff25c598b3367d009ec6c803, en el banco oficial HTTPS de hls.js. TyC Sports / tyc24 y Amagi reprodujeron allí. La marca observada en Amagi fue TyC Sports Fan, con programación distinta; se preparó un feed separado para evitar mezclarlas como alternativas automáticas.

La verificación desde la aplicación publicada confirmó únicamente **TyC Sports / tyc24**: video 1920×1080, playing y avance de 5,8 a 34,2 y 80,8 s. La opción User-Agent de VLC no fue necesaria y se retiró solo para esa URL, conservando el reproductor y la política general. El stream y feed de TyC mantienen sus IDs originales.

**TyC Sports Fan no superó la prueba en la beta pública:** falló con NETWORK y videoWidth 0, también tras un reintento. Se retira del catálogo y del manifiesto de aprobados; no debe figurar como señal pública validada. La causa precisa no se atribuye a CORS o región sin evidencia adicional. Que funcionara en el banco externo no sustituyó la prueba del sitio real.

ESPN Premium Chile devolvió HTTP 403 al cargar el manifiesto. ESPN Premium Argentina y tres fuentes DSports, todas HTTP, fallaron desde el banco HTTPS, con manifestLoadError y sin video decodificado; esto no demuestra que sus servidores estén caídos. Estas cinco fuentes tampoco se publican. TNT Sports y Disney+ no tienen URL para integrar en la revisión examinada.

Actualización solo de datos: export estático existente conservado, sin recompilar; se reemplazaron out/catalog.json y out/validation.json y se verificó su correspondencia exacta con las pruebas. El catálogo completo original y el respaldo PGlite permanecen intactos. No se reimportaron datos, no se añadió proxy ni se modificó la seguridad del navegador. La reproducción observada no garantiza acceso desde otras regiones, disponibilidad permanente o cobertura de un partido futuro. En la prueba prolongada de tyc24 en hls.js hubo un buffer stall que se recuperó; la comprobación posterior en la beta tuvo video en movimiento.
