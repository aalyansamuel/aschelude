# ASchelude

Organizador semanal minimalista. Cada día te pregunta qué tienes, entiende lo que escribes y lo coloca en tu semana:

- «Dentista jueves a las 10»
- «Práctica Docker: Dockerfile, compose y memoria antes del viernes 6h» → 3 subtareas, repartida en bloques hasta el viernes
- «Estudiar examen 6h antes del viernes en bloques de 2h» / «Proyecto 4 horas en 4 sesiones» / «Leer 3h sin dividir»
- «Gimnasio los lunes y miércoles a las 19»
- «Clases de 6 a 15:30» · «Gym 16:30 a 19» · «Estudiar 20 a 22» (formato 24 h estricto: «de 1 a 3» es de madrugada, «de 13 a 15» es por la tarde; si pegas varias líneas, se crea un evento por línea)

Funciona en ordenador, iPhone y Android, **con o sin conexión**. Tus datos se guardan solo en el dispositivo.

## Novedades de la versión 2

- **Arrastrar para mover:** en el ordenador, arrastra una tarjeta a otra columna. En el móvil, mantén pulsado un evento y suéltalo sobre un día de la tira de arriba. Si lo dejas encima de las flechas, cambia de semana.
- **Tareas largas en bloques:** lo que dura más de 2 h y no tiene hora se reparte en bloques de 1–2 h hasta la fecha límite. Puedes elegir el tamaño o «No dividir» en la ficha del evento.
- **Reorganizar el día:** si algo se pasó sin marcar o no cabe, toca «Reorganizar» junto a la fecha de hoy y vuelve a buscar hueco a partir de ahora.
- **Subtareas:** escribe «Título: una, otra y otra» o añádelas en la ficha. Al marcar la última, el evento se completa.
- **Resumen y cierre de semana:** al final de la agenda verás las horas por categoría en una barra. El domingo por la tarde aparece el cierre: porcentaje completado, lo que hiciste y lo que pasa a la semana siguiente.

## Publicarla (GitHub Pages)

1. Sube **todos los archivos de este zip a la raíz** del repositorio (`index.html`, `sw.js`, `manifest.webmanifest`, `icons/`), sustituyendo los anteriores.
2. Settings → Pages → Deploy from a branch → `main` / `(root)` → Save.
3. Espera 1–3 minutos y abre `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`.
4. **iPhone (Safari):** Compartir → Añadir a pantalla de inicio. **Android (Chrome):** ⋮ → Instalar aplicación. **PC (Chrome o Edge):** icono de instalar en la barra de direcciones.

Si ya tenías instalada la versión anterior, tus datos se conservan: abre la app dos veces con conexión y se actualiza sola. El nombre bajo el icono del iPhone no cambia hasta que lo vuelvas a añadir; antes de borrar el icono, copia tus datos en **Ajustes → Copiar copia de seguridad**, porque al borrarlo el iPhone puede borrar también sus datos.

## Atajos de iPhone

ASchelude entiende dos enlaces:

- `https://TU-USUARIO.github.io/REPO/?add=dentista jueves a las 10` añade el evento (varios a la vez separados por `;`).
- `https://TU-USUARIO.github.io/REPO/?revision` abre la revisión del día.

**Importante:** en el iPhone, la app de la pantalla de inicio guarda sus datos aparte de Safari, y los Atajos abren los enlaces en Safari. Para que los Atajos escriban en tus datos, usa ASchelude en Safari: al añadirla a la pantalla de inicio, desactiva «Abrir como app web».

Atajo «Añadir a ASchelude»: Dictar texto → Codificar URL → URL (`https://…/?add=` + texto codificado) → Abrir URL. Puedes lanzarlo con Siri o asignarlo al botón de acción.

## Probarla con Docker

```sh
docker build -t aschelude .
docker run -d --name aschelude -p 8080:80 aschelude
```

Abre `http://localhost:8080`. El iPhone solo activa el modo sin conexión por HTTPS, así que para el móvil usa GitHub Pages.

## Pasar tus datos a otro dispositivo

**Ajustes → Copiar copia de seguridad** (o Descargar copia) en uno, y **Ajustes → Importar** en el otro.

## Atajos de teclado (ordenador)

`/` o `N` escribir un evento · `←` `→` cambiar de semana · `T` volver a hoy · `Esc` cerrar o cancelar un arrastre.

## Actualizar

Si cambias `index.html`, cambia también en `sw.js` el nombre de la caché (`aschelude-v4` → `aschelude-v5`) para que los dispositivos descarguen la versión nueva.
