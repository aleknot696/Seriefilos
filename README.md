# Seriéfilos

App de Android para pagar solo las plataformas de streaming que usás: rotación, lista "Para ver", series en espera de temporada nueva, promos y avisos.

## Estructura

- `www/` — la app (HTML/CSS/JS en un solo archivo, sin dependencias).
- `android/` — proyecto Android generado con Capacitor 8.
- `docs/` — se publica con GitHub Pages: `catalogo.json` (precios y promos que leen todas las apps), `privacidad.html`.
- `store/` — ícono, imagen destacada, capturas y textos para Google Play.
- `.github/workflows/android.yml` — arma el APK de prueba y el AAB firmado en cada cambio.

## Puesta en marcha (una sola vez)

1. Crear el repositorio **seriefilos** (público) en github.com/aleknot696 y subir todo este contenido.
2. **Settings → Pages**: "Deploy from a branch", rama `main`, carpeta `/docs`. Queda en https://aleknot696.github.io/Seriefilos/
3. **Settings → Secrets and variables → Actions**: cargar los 4 secretos del archivo `LEEME-firma.txt` (KEYSTORE_BASE64, KEYSTORE_PASSWORD, KEY_ALIAS, KEY_PASSWORD).
4. **Actions → Armar app Android → Run workflow**. Al terminar, en el resumen de la ejecución aparecen:
   - `seriefilos-prueba-apk`: para instalar directo en el celular.
   - `seriefilos-google-play-aab`: el archivo que se sube a Google Play.

## Actualizar precios y promos

Editar `docs/catalogo.json` (cambiar `mes`, `actualizado` y los precios). Las apps lo descargan al abrirse; no hace falta publicar una versión nueva.

## Probar en la compu

```
cd www && python3 -m http.server 8000
```
y abrir http://localhost:8000 (las notificaciones solo funcionan en Android).

Datos de series: TVmaze (CC BY-SA). Búsquedas: JustWatch.
