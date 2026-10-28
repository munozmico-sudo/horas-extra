# Mis Horas Extra

App para contar las horas extra del trabajo y lo que se gana con ellas.

- **Fichar**: apunta la entrada y la salida a mano o con "Fichar ahora".
- **Foto**: haz una foto al reloj y la app lee la hora de entrada o de salida.
- **Resumen**: horas trabajadas, horas extra y ganancias de cada mes.
- **PDF**: crea un PDF del mes con solo las horas extra o con el horario completo, para imprimir o compartir.
- **Ajustes**: horario de cada día, precio de la hora extra, precio en día libre, descanso no pagado y copia de seguridad.

Los datos se guardan en el propio teléfono. Usa la copia de seguridad de Ajustes para no perderlos.

## Lectura de la foto

- **Sin clave**: reconocimiento de texto gratuito (Tesseract). Va bien con relojes digitales y máquinas de fichar y necesita internet.
- **Con clave de la API de Claude** (Ajustes → Lectura de fotos): también lee relojes de agujas. Cada lectura gasta un poco de saldo de la API.

## Subirla a GitHub

1. Crea un repositorio nuevo en GitHub, por ejemplo `horas-extra`.
2. Sube **todo** el contenido de esta carpeta, incluida la carpeta oculta `.github`.
   Si la subes desde la web de GitHub ("Add file → Upload files"), arrastra la carpeta entera para que no se quede fuera `.github`.
3. La rama debe llamarse `main`.

## Conseguir el APK para Android

1. En el repositorio, entra en la pestaña **Actions**. El flujo **Compilar APK** arranca solo con cada subida y tarda unos 5 minutos.
2. Cuando termine con la marca verde, ve a **Releases** (a la derecha en la portada del repositorio).
3. Descarga `MisHorasExtra.apk` desde el móvil e instálalo. Android pedirá permitir la instalación de apps de origen desconocido.

Cada vez que subas un cambio se crea un APK nuevo. Al instalarlo encima se conservan los datos.

## Usarla como web (opcional)

1. En el repositorio: **Settings → Pages → Source: GitHub Actions**.
2. Vuelve a lanzar el flujo **Publicar web** en Actions ("Run workflow").
3. La app queda en `https://TU-USUARIO.github.io/horas-extra/` y se puede añadir a la pantalla de inicio.

La web y el APK guardan los datos por separado. Para pasar los datos de una a otra, usa la copia de seguridad.

## Estructura

```
www/                 la app (index.html, manifest, icono, service worker)
capacitor.config.json  configuración para convertirla en app Android
package.json           dependencias de Capacitor
.github/workflows/     compilación del APK y publicación de la web
```
