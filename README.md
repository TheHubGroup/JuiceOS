# JuiceOS

Un inicio (launcher) para Android TV y Google TV: tendencias de cada plataforma, búsqueda de películas y series
con "dónde verlo", y tu IPTV (servidor/usuario/clave o portal MAC) integrado, con "Continuar viendo" de Stremio.

JuiceOS **no incluye canales ni contenido**: tu IPTV y tu cuenta de Stremio son tuyos.

## Instalar (Downloader)
Descarga el APK de la última versión en **Releases** y ábrelo con Downloader en la TV:

- `app-armeabi-v7a-release.apk`: Mi Box S y cajas de 32 bits.
- `app-arm64-v8a-release.apk`: Google TV y Android TV modernos.

Después: Ajustes › Restaurar y desinstalar permite volver al inicio original en cualquier momento.

## Compilar
Requiere JDK 17 y el Android SDK (plataforma 34).

1. En `local.properties`: `TMDB_KEY=tu_clave_de_tmdb` (opcional; sin ella cada usuario pone la suya en Ajustes).
2. Para firmar con tu clave, crea `keystore.properties` (ver `RELEASE.md`); sin ella firma con la clave de depuración.
3. `gradle assembleRelease`

## Créditos
Este producto usa la API de TMDB pero no está respaldado ni certificado por TMDB.
Reproducción: Media3 / ExoPlayer (Apache 2.0) y libVLC (LGPL 2.1). Imágenes: Coil. Tipografía: Inter (SIL OFL).
Netflix, HBO, Disney+, Paramount+, Apple TV, Prime Video, YouTube y Stremio son marcas de sus dueños.
