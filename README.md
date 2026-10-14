# 📻 Retro Radio Tuner — Radio online de todo el mundo

Radio por Internet con aspecto de transistor retro: miles de emisoras de más de 200 países, buscador, favoritas y controles en la pantalla de bloqueo del móvil. Es una sola página HTML, sin backend y sin claves de API.

🌐 **Web:** https://jpm70.github.io/RadioWorld/

---

## ✨ Funciones

- **Emisoras por país**, ordenadas por popularidad, con su logo, formato y calidad (MP3/AAC, kbps).
- **🔍 Buscador** por nombre, estilo o ciudad, en todo el mundo o solo en el país elegido.
- **★ Favoritas** guardadas en el navegador.
- **⏮ ⏭ Anterior / siguiente**, como el dial de una radio de verdad. También con las flechas del teclado, y la barra espaciadora para pausar.
- **Controles en la pantalla de bloqueo** del móvil (Media Session): nombre, logo, pausa y cambio de emisora.
- **Reconexión automática** si se corta la conexión, por ejemplo al pasar de 4G a WiFi. Si la red se cae del todo, vuelve a sonar sola cuando regresa.
- **Mensajes claros** cuando una emisora no funciona, con un botón para probar la siguiente.
- Recuerda el país, la última emisora, la pestaña y el volumen.

## 🛠️ Cómo funciona

| Parte | Detalle |
|---|---|
| Directorio de emisoras | [Radio Browser](https://www.radio-browser.info), API pública y gratuita. Si un servidor no responde, se prueba el siguiente |
| Streams HLS (`.m3u8`) | Nativos en Safari y Chrome; en el resto se carga [hls.js](https://github.com/video-dev/hls.js) solo cuando hace falta |
| Nombres de países | `Intl.DisplayNames` del navegador, en español |

### Emisoras marcadas con 🔓

La web se sirve por HTTPS, y los navegadores bloquean el audio sin cifrar (HTTP) en páginas seguras. Muchas emisoras que en el directorio solo anuncian `http://` también emiten por `https://` (SER, COPE, Cadena 100, Rock FM…), así que la app las prueba así. Las que no lo admiten no pueden sonar desde aquí, y la app lo explica en lugar de quedarse en silencio.

## 🚀 Ejecutar en local

No hace falta instalar nada. Basta con servir la carpeta:

```bash
python -m http.server 8000
```

y abrir http://localhost:8000.

## 📁 Estructura

```
RadioWorld/
├── index.html        # Toda la app (HTML + CSS + JS)
├── assets/logo.png   # Logo de Un Fantasma en el Sistema
├── .nojekyll         # GitHub Pages sirve los archivos tal cual
└── LICENSE
```

## 📄 Licencia

[MIT](LICENSE). Directorio de emisoras: © colaboradores de [radio-browser.info](https://www.radio-browser.info). Cada emisora pertenece a sus titulares.

---

Hecho por [Un Fantasma en el Sistema](https://www.unfantasmaenelsistema.com).
