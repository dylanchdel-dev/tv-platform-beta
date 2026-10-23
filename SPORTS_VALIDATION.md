# Revisión de Deportes — 23/10/2026

> Registro histórico anterior al filtro público. La selección inicial publicó 13 señales comprobadas. La revisión posterior de TyC incorpora únicamente tyc24 tras una nueva prueba positiva desde la beta. TyC Sports Fan falló en la aplicación y se retiró; ver README. Los resultados de esta tabla son históricos; TyC fue probado nuevamente con resultado positivo y se documenta por separado en README. Ver README y validation.json.

Se revisaron las 60 entradas de Deportes del catálogo original publicado, sin importar nuevos datos ni modificar URLs. Las 17 entradas con al menos un candidato HTTPS sin cabeceras obligatorias se probaron desde la URL pública en Chrome de Work, pulsando «Reproducir señal». Se confirmó video mediante estado `playing`, dimensiones decodificadas y avance del tiempo; no solo descarga de un manifiesto.

Resultado: **11 reprodujeron video, 6 fallaron al reproducir, 11 no tienen una fuente directa compatible y 32 no tienen URL**. El tiempo observado corresponde a esta sesión; no garantiza reproducción desde Paraguay ni disponibilidad permanente. No se verificó de forma independiente la identidad editorial de las retransmisiones de terceros.

Los estados finales HTTPS y HEADERS de L1 Max y TyC Sports pueden reflejar la última alternativa descartada tras fallar una URL HTTPS; no prueban la causa de la primera conexión fallida. NETWORK no permite atribuir CORS, geobloqueo o caída del proveedor sin evidencia adicional. ESPN 3 tuvo una espera intermedia y volvió a reproducir.

## Inventario completo

| Canal | País | URLs | Resultado |
| --- | --- | ---: | --- |
| America Sports | AR | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Best Cable Sports Peru | PE | 0 | Sin URL en el respaldo; no se intentó reproducir |
| CDF Basico | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| CDO | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| CDO Basico | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| CDO Premium | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| CDR | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| CRTV | CL | 1 | Reprodujo video: 145.9 s; ancho 1280 px |
| Canal Showsport | AR | 1 | Reprodujo video: 146.9 s; ancho 960 px |
| Claro Sports Chile | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| CnAr Deportes | AR | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Conmebol TV 1 | PY | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Conmebol TV 2 | PY | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Conmebol TV 3 | PY | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Conmebol TV 4 | PY | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Contacto Deportivo | PE | 0 | Sin URL en el respaldo; no se intentó reproducir |
| D13 | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| DSports | US | 3 | Solo HTTP o cabeceras obligatorias; sin candidato directo compatible |
| DeporTV | AR | 1 | Solo HTTP o cabeceras obligatorias; sin candidato directo compatible |
| ESPN 2 Latin America | US | 2 | Reprodujo video: 138.3 s; ancho 1920 px |
| ESPN 3 Latin America | US | 2 | Reprodujo video: 133.5 s; ancho 1920 px |
| ESPN 4 Latin America | US | 1 | Reprodujo video: 116.8 s; ancho 1920 px |
| ESPN 5 Latin America | US | 2 | Reprodujo video: 122.1 s; ancho 1920 px |
| ESPN 6 Latin America | US | 2 | Reprodujo video: 120.0 s; ancho 1920 px |
| ESPN 7 Latin America | US | 1 | Reprodujo video: 116.0 s; ancho 1920 px |
| ESPN Extra Latin America | US | 1 | Solo HTTP o cabeceras obligatorias; sin candidato directo compatible |
| ESPN Latin America | US | 2 | Reprodujo video: 117.8 s; ancho 1920 px |
| ESPN Premium | AR | 1 | Solo HTTP o cabeceras obligatorias; sin candidato directo compatible |
| ESPN Premium | CL | 1 | Solo HTTP o cabeceras obligatorias; sin candidato directo compatible |
| FIFA+ | UK | 1 | Reprodujo video: 112.1 s; ancho 1280 px |
| Fox Sports | AR | 2 | Solo HTTP o cabeceras obligatorias; sin candidato directo compatible |
| Fox Sports 1 | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Fox Sports 2 | AR | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Fox Sports 3 | AR | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Gol Peru | PE | 0 | Sin URL en el respaldo; no se intentó reproducir |
| HAPSATV | AR | 0 | Sin URL en el respaldo; no se intentó reproducir |
| L1 | PE | 1 | Solo HTTP o cabeceras obligatorias; sin candidato directo compatible |
| L1 Max | PE | 2 | Falló al reproducir; estado final HTTPS |
| La Tribu Deport 1120 AM | PY | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Monterrico TV | PE | 1 | Reprodujo video: 109.1 s; ancho 1920 px |
| Movistar Deportes | PE | 3 | Solo HTTP o cabeceras obligatorias; sin candidato directo compatible |
| Movistar Eventos | PE | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Ovacion TV | PE | 1 | Solo HTTP o cabeceras obligatorias; sin candidato directo compatible |
| Red Bull Batalla de los Gallos | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Sqala TV | PE | 1 | Falló al reproducir; estado final NETWORK |
| TNT Sports | AR | 0 | Sin URL en el respaldo; no se intentó reproducir |
| TNT Sports | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| TNT Sports 2 | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| TNT Sports 3 | CL | 0 | Sin URL en el respaldo; no se intentó reproducir |
| Teletrak TV | CL | 1 | Falló al reproducir; estado final NETWORK |
| Tigo Sports | PY | 1 | Solo HTTP o cabeceras obligatorias; sin candidato directo compatible |
| Tigo Sports+ | PY | 2 | Falló al reproducir; estado final NETWORK |
| Turf Movil | CL | 1 | Falló al reproducir; estado final NETWORK |
| TyC Sports | AR | 2 | Falló al reproducir; estado final HEADERS |
| TyC Sports 2 | AR | 0 | Sin URL en el respaldo; no se intentó reproducir |
| TyC Sports 3 | AR | 0 | Sin URL en el respaldo; no se intentó reproducir |
| TyC Sports 4 | AR | 0 | Sin URL en el respaldo; no se intentó reproducir |
| TyC Sports Latin America | AR | 0 | Sin URL en el respaldo; no se intentó reproducir |
| TyC Sports USA | AR | 1 | Solo HTTP o cabeceras obligatorias; sin candidato directo compatible |
| Universitario TV | PE | 0 | Sin URL en el respaldo; no se intentó reproducir |

## Contraste con fuentes oficiales

- ESPN: Disney+ Paraguay indica canales básicos de ESPN en el plan Premium: https://www.disneyplus.com/es-py . Las URLs de terceros que reprodujeron en esta prueba no garantizan acceso permanente.
- Tigo Sports: https://www.tigosports.com.py/ presenta acceso por suscripción/proveedor.
- TyC Sports: https://play.tycsports.com/ayuda.html requiere usuario de cableoperador y ubicación en Argentina para la señal lineal de 24 horas.
- TNT Sports Chile: https://help.hbomax.com/cl/Answer/Detail/000002560 explica la suscripción al contenido TNT Sports.
- L1 Max: https://intercom.help/l1max/es/articles/7153827-suscribete-a-un-plan explica el acceso por plan.
- DeporTV: https://deportv.gob.ar/vivo se abrió en el navegador de Work; su reproductor oficial mostró «Stream Offline» durante esta revisión. No se encontró una sustitución directa verificada en ese reproductor.
- FIFA+: https://www.fifa.com/es/dazn indica su plataforma oficial actual. Su candidato de canal FAST en el catálogo reprodujo durante la prueba.

## Corrección de presentación

La tarjeta deja de afirmar «Señal disponible» por la mera existencia de una URL. Distingue «Fuente por comprobar», «Fuente no compatible» y «Sin fuente de reproducción». En el detalle sin URL se indica que reintentar no conecta una señal sin fuente. Se preservan el reproductor, sus límites de acceso, las 941 URLs y el catálogo completo. Esto aclara la disponibilidad; no repara los servidores externos ni crea señales que faltan.
