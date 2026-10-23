# SeñalSur — beta pública temporal

**Web:** https://dylanchdel-dev.github.io/tv-platform-beta/

Repositorio independiente: `dylanchdel-dev/tv-platform-beta`. No se modificaron otros proyectos de GitHub. El proyecto completo Next.js + Prisma + PostgreSQL y su respaldo PGlite original permanecen intactos por separado.

## Estado del despliegue

GitHub Actions finalizó con **Success** en la primera ejecución del workflow `Publicar beta temporal`:
https://github.com/dylanchdel-dev/tv-platform-beta/actions/runs/39879336661

La beta se publica desde el export estático ya compilado y verificado incluido en `SenalSur_GitHub_Pages_beta.zip`. El workflow extrae `tv-platform-github-pages/out/`, comprueba los conteos y lo publica mediante las acciones oficiales de GitHub Pages. No necesita volver a compilar ni descargar datos de iptv-org.

## Datos y funciones

- Catálogo del **17/10/2026**: **1.615 canales, 1.752 feeds y 941 candidatos de reproducción**.
- Búsqueda por nombre, ID externo y nombres alternativos; filtros por país y categoría; 25 canales por página.
- Argentina 498, Chile 497, Perú 420 y Paraguay 161; otros países 39.
- Detalle del canal, selección manual de feed y alternativas dentro de la misma señal.
- Diseño público, componente de logos, HlsPlayer y política de reproducción originales conservados.
- Catálogo de lectura; no hay actualización automática.

## Comprobaciones sobre la URL pública

Se abrió la web real en el navegador de Work y se verificaron: inicio con 25 tarjetas y total 1.615; segunda página distinta; los cuatro filtros nacionales y sus conteos; búsqueda de 13C combinada con Chile y Culture; detalle de canal; recarga directa del enlace de Antena SUR; canal Metro sin stream con el mensaje esperado; rutas `/admin/` y `/api/admin/status/` sin servicio administrativo (página 404).

Escritorio público revisado a 1.363 píxeles de ancho, sin desbordamiento horizontal. Vista móvil 390×844 revisada localmente sobre el mismo export publicado; no se probó en un dispositivo físico.

### Reproducción real, sin interceptar los proveedores

| Canal | Resultado desde la web publicada |
| --- | --- |
| Caritas TV (Paraguay) | Reproducción confirmada: estado playing, video de 1.920 píxeles de ancho y tiempo superior a 25 segundos. |
| Antena SUR (Perú) | Reproducción confirmada: estado playing, video de 1.920 píxeles de ancho y tiempo superior a 21 segundos. |
| 13C (Chile) | Falló con estado NETWORK, sin imagen decodificada. No se atribuye una causa más específica sin evidencia. |

Estos resultados corresponden a esta prueba y ubicación. No garantizan disponibilidad permanente ni reproducción de todos los candidatos del catálogo.

## Límites de la versión temporal

GitHub Pages sirve archivos estáticos. Esta adaptación **no incluye PostgreSQL, panel administrativo, login ni APIs administrativas**. No hay contraseñas predeterminadas, credenciales de base, notas administrativas o auditoría en los datos publicados.

Las URLs de stream son necesariamente visibles para el navegador. HTTPS, permisos CORS, cabeceras obligatorias, geobloqueos y disponibilidad externa siguen aplicándose. No hay proxy de video ni se eluden restricciones. Algunos logos externos pueden fallar; se mantiene el fallback original.

Las páginas usan `/channel/?id=UUID&feed=UUID` para funcionar y recargarse en hosting estático. No se implementaron funciones adicionales.

## Mantener esta publicación

- **Settings → Pages → Source: GitHub Actions**.
- El workflow `.github/workflows/pages.yml` se activa al actualizar el ZIP o el propio workflow; los cambios del README no vuelven a desplegar el sitio.
- Para actualizar la beta, generar y verificar un nuevo export con el prefijo `/tv-platform-beta` y reemplazar el ZIP conservando su estructura; revisar los conteos esperados del workflow si cambian los datos.
- Los archivos fuente y el lockfile están dentro del ZIP. Para trabajar en esa copia: Node.js 24, `npm ci`, `npm run dev` y `npm run build`. La salida es `out/`; no necesita `.env` ni DATABASE_URL.
- Para recuperar el proyecto completo y su administración, retomar el despliegue original de Railway con PostgreSQL real y el respaldo ya verificado.
