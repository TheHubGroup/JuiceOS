# JuiceOS: cómo publicar una versión

## Una sola vez
1. **Clave de TMDB que irá dentro de la app.** En `local.properties` (esta carpeta) añade una línea:
   `TMDB_KEY=tu_clave_aquí`
   Sin ella la app compila igual, pero sin buscador ni tendencias hasta que el usuario ponga su propia clave.
   Ojo: una clave dentro del APK se puede extraer. Si la quieres proteger, pon un servidor propio entre la app y TMDB.
2. **Clave de firma.** `keystore/juiceos-release.jks` y `keystore.properties` se crearon la primera vez.
   **Haz una copia de seguridad de las dos y no las pierdas:** cada actualización tiene que firmarse con esa misma clave
   o nadie podrá actualizar encima de lo instalado. No las subas a ningún repositorio público.

## Cada versión
1. Sube `versionCode` (siempre +1) y `versionName` en `app/build.gradle.kts`.
2. `gradle assembleRelease`
3. Salen dos APK en `app/build/outputs/apk/release/`:
   - `app-armeabi-v7a-release.apk` (~46 MB): Mi Box S y la mayoría de cajas de 32 bits.
   - `app-arm64-v8a-release.apk` (~50 MB): Google TV y Android TV modernos (Chromecast con Google TV, Hisense, Sony, Shield).
4. Súbelos a un sitio con enlace fijo (por ejemplo GitHub Releases).
5. En Downloader se puede escribir la URL o un código numérico; esos códigos los da el acortador de AFTVnews (aftv.news).
   Comprueba allí cómo pedir uno para cada APK.

## Antes de publicar, probar
- Instalar en una caja y en una Google TV, abrir con el mando, entrar a Ajustes › Restaurar y desinstalar.
- Que "Abrir el inicio original" y "Desinstalar JuiceOS" funcionan.
- Que con la clave de TMDB puesta salen tendencias y el buscador.
