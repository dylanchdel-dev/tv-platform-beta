# SeñalSur — beta temporal con señales comprobadas

Web: https://dylanchdel-dev.github.io/tv-platform-beta/

## Selección pública — 23/10/2026

La beta publica únicamente **13 canales, 13 feeds y 13 streams HTTPS** cuya reproducción fue comprobada desde la aplicación pública en Chrome de Work. Se observó video decodificado y avance del tiempo, no solo una respuesta HTTP o un manifiesto HLS. Se excluyeron también los feeds vacíos y las alternativas que no fueron probadas de los canales aprobados.

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

## Catálogo original conservado

El snapshot completo del 17/10/2026 contiene 1.615 canales, 1.752 feeds, 941 streams y 1.646 logos. Permanece intacto en el proyecto original y sus respaldos. Esas cifras **no son el contenido de la selección pública actual**. No se reimportaron datos ni se modificaron URLs de proveedores. El inventario histórico de deportes se conserva en [SPORTS_VALIDATION.md](SPORTS_VALIDATION.md).

TNT Sports Argentina/Chile, ESPN Premium, TyC Sports, L1 Max, Tigo Sports+, Teletrak, Turf Móvil y Sqala no tienen prueba positiva aplicable y quedan fuera. Ver ESPN u otro canal no demuestra que transmita un partido concreto. No está confirmada la cobertura completa de Liga Argentina, Liga Chilena, Libertadores, Copa Argentina, Copa Chile, Sudamericana o Champions.

## Publicación y mantenimiento

Repositorio independiente `dylanchdel-dev/tv-platform-beta`; no se modifican otros proyectos. El ZIP incluye fuentes, lockfile y export estático compilado bajo `tv-platform-github-pages/`. `.github/workflows/pages.yml` extrae y valida `out/` antes de publicar mediante las acciones oficiales de GitHub Pages. Settings → Pages → Source: GitHub Actions. Se activa al cambiar el ZIP o el workflow en main.

Para actualizar: comprobar reproducción real de cada URL; actualizar catálogo y manifiesto con la misma fecha e IDs; ejecutar `npm run build` (Node.js 24), validar la correspondencia y reemplazar el ZIP con su estructura actual. No publicar el respaldo completo como catálogo sin nuevas pruebas. No hacen falta `.env` ni DATABASE_URL para esta adaptación.

Búsqueda, filtros, diseño, logos y reproductor existentes conservados. Con 13 canales todos caben en una sola página. Las rutas usan `/channel/?id=UUID&feed=UUID`; enlaces antiguos fuera de la selección muestran que la señal no está validada.

## Límites del hosting temporal

GitHub Pages es estático: **no hay PostgreSQL, panel administrativo, login ni APIs administrativas** en esta beta. Las rutas administrativas no tienen backend. No contiene secretos, credenciales, cuentas administrativas ni datos de auditoría.

Railway sigue siendo el destino del proyecto completo Next.js + Prisma + PostgreSQL y administración. Cambiar el hosting no elimina CORS, bloqueos regionales, HTTP incompatible con HTTPS o errores externos del proveedor. Para restaurar el proyecto completo debe retomarse el despliegue Railway y el respaldo ya verificado; no se declara realizado aquí.
