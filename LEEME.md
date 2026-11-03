# Semana

Organizador semanal minimalista. Cada día te pregunta qué tienes, entiende lo que escribes («Dentista jueves a las 10», «Entregar práctica antes del viernes 2h», «Gimnasio los lunes y miércoles a las 19») y lo coloca en tu semana. Lo que no tiene hora va al primer hueco libre de tu jornada, respetando prioridad y fecha límite.

Funciona en ordenador, iPhone y Android, **con o sin conexión**. Tus datos se guardan solo en el dispositivo.

## Instalarla en el móvil (recomendado: GitHub Pages)

El modo sin conexión necesita que la app se sirva por **HTTPS** una vez. Después ya no hace falta internet.

1. Crea un repositorio en GitHub (por ejemplo `semana`) y sube **el contenido** de esta carpeta (`index.html`, `sw.js`, `manifest.webmanifest`, `icons/`).
2. En el repositorio: **Settings → Pages → Deploy from a branch → main / (root) → Save**.
3. En un minuto tendrás la URL: `https://TU-USUARIO.github.io/semana/`.
4. Ábrela una vez con conexión:
   - **iPhone (Safari):** Compartir → **Añadir a pantalla de inicio**.
   - **Android (Chrome):** menú ⋮ → **Instalar aplicación**.
   - **PC (Chrome o Edge):** icono de instalar en la barra de direcciones.

Alternativa sin cuenta de GitHub: arrastra esta carpeta a <https://app.netlify.com/drop>.

## Probarla con Docker

```sh
docker build -t semana .
docker run -d --name semana -p 8080:80 semana
```

Abre `http://localhost:8080`. Ojo: el iPhone solo activa el modo sin conexión por HTTPS (o en `localhost`), así que para el móvil usa GitHub Pages o Netlify.

## Usarla en el PC sin instalar nada

Doble clic en `index.html`. Funciona sin conexión porque es un archivo local; los datos quedan guardados en ese navegador.

## Pasar tus datos a otro dispositivo

Cada dispositivo guarda sus propios datos. Para moverlos: **Ajustes → Copiar copia de seguridad** (o Descargar copia) en uno, y **Ajustes → Importar** en el otro.

## Que te pregunte cada mañana

La revisión del día aparece sola la primera vez que abres Semana cada día. Para no olvidarte de abrirla, crea una alarma o recordatorio diario (por ejemplo, en Atajos de iPhone: Automatización → Hora del día → Mostrar notificación).

## Atajos de teclado (ordenador)

`/` o `N` escribir un evento · `←` `→` cambiar de semana · `T` volver a hoy · `Esc` cerrar.

## Actualizar

Si cambias `index.html`, sube también `sw.js` cambiando `semana-v1` por `semana-v2` para que los dispositivos descarguen la versión nueva.
