# SeñalSur — beta temporal para GitHub Pages

Adaptación estática del proyecto terminado en el Paso 5. El proyecto completo y su respaldo PGlite original permanecen intactos por separado.

## Contenido y límites

- Catálogo del 17/10/2026: 1.615 canales, 1.752 feeds y 941 candidatos de reproducción. No se volvió a importar iptv-org.
- Búsqueda por nombre/ID externo/alternativos, filtros por país y categoría, 25 canales por página y selección manual de feeds.
- Se conservaron sin cambios el CSS público, HlsPlayer, la política de reproducción y el componente de logos originales.
- El catálogo se consulta en el navegador desde `public/catalog.json`. Es una copia de lectura; no se actualiza automáticamente.
- No hay PostgreSQL, panel administrativo, login ni APIs administrativas en esta versión. Las rutas administrativas no se publican.
- El JSON incluye únicamente datos públicos para mostrar y reproducir canales. No contiene cuentas, auditoría, notas administrativas, cabeceras privadas ni credenciales de base de datos.
- Las páginas de canal usan `/channel/?id=UUID&feed=UUID`. Esta forma permite abrirlas y recargarlas en un hosting estático.
- Las URLs de stream son necesariamente visibles en el navegador. Se conserva su contenido completo, incluidos parámetros. No hay proxy de video.
- HTTPS, CORS, cabeceras obligatorias, restricciones geográficas y disponibilidad del proveedor siguen aplicándose. Los 941 candidatos no son 941 señales verificadas como operativas.

## Publicar

1. Crear un repositorio público `tv-platform-beta` en la cuenta de GitHub, inicializado con README.
2. Subir los archivos fuente de esta carpeta, incluida `.github/workflows/pages.yml`, a `main`. No subir `node_modules`, `.next`, `.local` ni secretos.
3. En Settings → Pages → Build and deployment → Source, seleccionar **GitHub Actions**.
4. El workflow instala las dependencias con `npm ci`, genera el export y lo publica. Toma el nombre real del repositorio para configurar el prefijo de las URLs.
5. Esperar a que ambos jobs terminen correctamente y abrir la URL devuelta por el job de publicación. No se ha verificado todavía una URL pública.

El ZIP también incluye `out/`, el sitio ya compilado localmente bajo `/tv-platform-beta`. Ese directorio permite servir el resultado sin volver a compilar; el workflow genera su propio export desde las fuentes.

## Desarrollo y compilación

Node.js 24 y npm:

```bash
npm ci
npm run dev
npm run build
```

El prefijo por defecto es `/tv-platform-beta`. Para otro repositorio:

```bash
NEXT_PUBLIC_BASE_PATH=/nombre-del-repositorio npm run build
```

La salida se genera en `out/`. No hace falta una variable DATABASE_URL ni un archivo `.env`.

## Comprobaciones realizadas

Compilación estática y lint correctos. Verificación focalizada en Chromium del export servido bajo el prefijo de GitHub Pages: inicio, 25 tarjetas, paginación, búsqueda por ID externo, filtros combinados, AR/CL/PE/PY, detalle de canal, feed con varias alternativas, recarga directa, canal sin stream, ausencia de admin/API administrativa y ausencia de excepciones JavaScript. Móvil 390×844 sin desbordamiento y escritorio 1440×1000 revisados visualmente.

Conteos por país de origen: Argentina 498, Chile 497, Perú 420 y Paraguay 161; los otros 39 canales corresponden a países distintos. Esto conserva el catálogo completo existente.

Nativa, WOW TV y PiuraTV se intentaron reproducir desde el export local, sin interceptar sus respuestas: los intentos terminaron con errores de red `net::ERR_EMPTY_RESPONSE`, sin imagen decodificada. No se atribuye una causa específica a CORS, códec o geobloqueo. Repetir desde la URL pública y una red de visitante antes de afirmar disponibilidad.

La evidencia textual está en `validation/local-pages.json`. Las capturas internas no se distribuyen.

## Volver al despliegue completo

El proyecto Next.js + Prisma + PostgreSQL original no fue modificado por esta adaptación. Cuando Railway permita crear el proyecto, retomar su despliegue y migrar desde el respaldo verificado. Este repositorio estático no sustituye el respaldo administrativo ni la base de producción.
